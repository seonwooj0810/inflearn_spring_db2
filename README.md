# inflearn_spring_db2

인프런 **김영한의 스프링 DB 2편 - 데이터 접근 활용 기술** 중 **스프링 트랜잭션** 파트 학습 저장소입니다.

> 참고: 이 저장소에는 DB 2편 전체가 아니라 `springtx` 패키지의 **트랜잭션 이해 / 트랜잭션 전파** 부분만 담겨 있습니다. (JdbcTemplate, MyBatis, JPA, Querydsl 등 데이터 접근 기술 코드는 포함되어 있지 않습니다.)

## 강의 / 학습 정보

- 강의: 스프링 DB 2편 - 데이터 접근 활용 기술 (김영한) — 트랜잭션 섹션
- 플랫폼: 인프런

## 사용 기술

- Java 17
- Spring Boot 3.3.2
- Spring Data JPA
- H2 Database
- Lombok
- JUnit 5
- Gradle (Kotlin DSL)

## 학습한 내용 (코드 근거)

- 트랜잭션 적용 원리: `@Transactional` 적용 확인, 프록시 동작 (`apply/TxBasicTest`)
- 트랜잭션 AOP 주의사항: 내부 호출 문제(self-invocation)와 해결 (`apply/InternalCallV1Test`, `InternalCallV2Test`)
- 초기화 시점과 트랜잭션 (`apply/InitTxTest`)
- 트랜잭션 전파(Propagation): 물리/논리 트랜잭션, 커밋·롤백, REQUIRES_NEW 등 (`propagation/BasicTxTest`)
- 전파 활용 예제: 회원/로그 저장 시나리오로 전파 옵션별 동작 검증 (`propagation/MemberService`, `LogRepository`, `MemberServiceTest`)

## 프로젝트 구조

```
inflearn_spring_db2/
└── src/
    ├── main/java/hello/springtx/
    │   └── propagation/    # Member, Log, Repository, Service (전파 예제)
    └── test/java/hello/springtx/
        ├── apply/          # 트랜잭션 적용/내부호출/초기화 테스트
        └── propagation/    # 트랜잭션 전파 테스트
```
