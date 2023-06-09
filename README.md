# SQL-Join

### 조인:exclamation:
두 개 이상의 테이블을 서로 연결하여 데이터를 검색할 때 사용하는 방법
두 개의 테이블을 마치 하나의 테이블인 것처럼 보여준다.

### 내부조인:exclamation:
두 테이블을 연결할 때 가장 많이 사용하는  것이 내부 조인입니다. 그냥 조인이라고 부르면 내부 조인을 의미합니다.
![image](https://user-images.githubusercontent.com/123055714/228698886-a087030d-fa83-4c45-97d2-5b6314505731.png)
#### 예제
급여가 2500 이하이고 사원번호가 200이하인 사원의 LAST_NAME, 부서명을 조회하시오.
```java
select E.LAST_NAME, D.DEPARTMENT_NAME from EMPLOYEES E,DEPARTMENTS D //조회할 것과 조회하는 곳
where E.DEPARTMENT_ID = D.DEPARTMENT_ID //조건 EMPLOYEES DEPARTMENT_ID랑 DEPARTMENT DEPARTMENT_ID랑 같다.
and E.SALARY <= 2500 and E.EMPLOYEE_ID <= 200; // SALARY가 2500보다크고 EMPLOYEE_ID가 200보다 작다.
```

### 외부조인:exclamation:
내부 조인은 두 테이블에 모두 데이터가 있어야만 결과가 나오지만, 외부 조인은 한쪽에만 데이터가 있어도 결과가 나옵니다.<br>
외부조인의 종류는<br>
LEFT OUTER JOIN: 왼쪽 테이블의 모든 값이 출력되는 조인<br>
RIGHT OUTER JOIN: 오른쪽 테이블의 모든 값이 출력되는 조인<br>
FULL OUTER JOIN: 왼쪽 또는 오른쪽 테이블의 모든 값이 출력되는 조인<br>
![image](https://user-images.githubusercontent.com/123055714/228698933-1cb7fae9-6a4f-41ed-aa14-6cdbc0700c45.png)

### 셀프조인 :exclamation:
자체 조인은 자기 자신과 조인하므로 1개의 테이블을 사용합니다. 별도의 문법이 있는 것은 아니고 1개로 조인하면 자체 조인이 됩니다.
![image](https://user-images.githubusercontent.com/123055714/228699357-5882d373-7e2c-4871-b102-b9d55ba8122e.png)
#### 예제
자신의 매니저보다 먼저 고용된 사원들의 LAST_NAME 및 고용일을 조회한다.
```java
SELECT E.LAST_NAME, E.HIRE_DATE from EMPLOYEES E, EMPLOYEES M //조회할 것과 조회하는 곳
where E.MANAGER_ID = M.EMPLOYEE_ID and E.HIRE_DATE < M.HIRE_DATE; //조건 EMPLOYEES E MANAGER_ID와 
```

