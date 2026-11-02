# 시험 개발 하네스

사용자가 읽는 문서와 AI가 개발에 쓰는 문서를 나눈 시험용 지침·프롬프트·양식이다.

**처음 준비는 [START](START.md), 요청 복사는 [PROMPTS](PROMPTS.md), 전체 순서는 [QUICKSTART](QUICKSTART.md).** 시작 프롬프트는 PROMPTS 1번 한 곳에만 있다.

## 내가 읽고 입력할 곳

| 실제 프로젝트 문서 | 용도 |
| --- | --- |
| **PROGRESS.md** | 쉬운 문제·자료 설명, 현재 상태, 직접 테스트, 구현 이해·인지 대비, 다음 행동 |
| **PLAN.md의 질문 입력란** | 담당자에게 받은 답변·출처를 직접 입력하고 저장 |
| **하네스의 PROMPTS.md** | 현재 단계의 기본 프롬프트와 필요한 작업용 보충을 복사 |

PROGRESS에는 담당자에게 보낼 질문과 PLAN의 답변 입력 위치를 안내한다. 답변 원문은 PLAN에만 남긴다. 답변을 저장한 뒤 PROMPTS의 답변 반영 또는 2번 요청을 보내면 AI가 다시 읽고 개발에 반영한다.

PRD·PLAN 전체·Phase별 개발 기록은 AI의 작업 문서다. 사용자는 PROGRESS에서 만들 결과·범위·선택 사항을 판단할 수 있다. 기술 문서 전체를 읽거나 AI 검증을 직접 수행했다고 말할 필요는 없다.

## 개발 문서와 기록 위치

| 실제 프로젝트 문서 | AI가 관리할 내용 |
| --- | --- |
| PRD.md | 전체 요구·제외 범위·관찰 가능한 완료 기준·원문/질문 근거 |
| PLAN.md | 공통 질문/답변 원문·AI 검토, 전체 Phase 순서·의존 관계·상태·통합 검증 담당 |
| plans/의 Phase 파일 | 해당 Phase의 작업표·구현 위치·검증 증거·책임/실패 상태·변경 기록 |

**1 문제 파악 → 2 PRD·계획 확인 → 3 Phase 구현·AI 검증 → 4 직접 테스트 → 5 구현 설명 확인 → 6 제출 점검**

1단계에는 PROGRESS와 질문 입력용 PLAN만 필요한 만큼 작성한다. 2단계부터 PRD와 실제 Phase별 계획을 만든다. 3→4는 Phase마다 반복하며, 한 Phase 안의 여러 기능·수정·재검증은 이어간다. Phase 수나 P1~P4의 구성을 고정하지 않는다.

사용자 확인은 보고된 주체·판본·범위만 기록한다. 변경에 영향받는 검증은 재확인 필요로 남긴다. 담당자 답변은 PLAN의 질문 ID로 PRD·Phase에 연결하고 다른 곳에 원문을 복제하지 않는다.

구현 때부터 PROGRESS에 입력 예시·처리 흐름과 책임·선택 이유와 손실·실패/복구·독립 검증·한계를 쉽게 설명한다. 인지 대비 정보는 실제 코드와 수행 근거로 갱신한다. 기술 로그와 긴 코드 설명은 Phase 문서에서 연결한다.

## 하네스 파일 안내

아래는 하네스 안의 **빈 양식과 지침**이다. 실제 과제 문서는 과제 프로젝트의 허용된 위치에 작성한다.

| 하네스 파일 | 역할 |
| --- | --- |
| [AGENTS](AGENTS.md) | AI의 핵심 규칙·문서 소유권·진행/검증 원칙 |
| [START](START.md) · [QUICKSTART](QUICKSTART.md) | 설치·배치 안내와 단계별 링크 |
| [PROMPTS](PROMPTS.md) | 단계별 기본 요청·작업별 보충 문구의 유일한 위치 |
| [PROGRESS 양식](PROGRESS.template.md) | 사용자용 설명·직접 테스트·인지 대비·다음 행동 |
| [PLAN 양식](PLAN.template.md) | 질문 입력과 개발 전체 목차 |
| [PRD 양식](templates/PRD.md) | 요구·범위·완료 기준 |
| [Phase 계획 양식](templates/PHASE_PLAN.md) | Phase별 작업·검증·책임·변경 기록 |
| [테스트 지침](templates/USER_TEST.md) · [구현 설명 지침](templates/IMPLEMENTATION.md) | AI가 PROGRESS의 안내·설명을 작성할 때 확인할 기술 항목 |
| [FINISH](FINISH.md) | 정상/중간 종료 제출 점검 |
| [.gitignore](.gitignore) | 비밀 설정·임시 파일 제외 |

기존/지정 문서를 우선 재사용하고 없는 역할만 만든다. 테스트·구현 설명 양식은 별도 사용자 문서를 반드시 만들라는 뜻이 아니다. 지정 실행·협업·제출 문서는 실제 수행 근거로 채우고 PROGRESS나 계획으로 대체하지 않는다.

실제 과제 수행 중 PROMPTS의 기본 문구는 보존한다. 상황별 수정이 필요하면 해당 블록 바로 아래에 적용 Phase/판본과 차이만 보충한다. PROGRESS에는 다음 단계 링크와 기본만/보충도 함께 복사할지를 안내하며 프롬프트 전문을 다시 만들지 않는다. 과제별 보충은 그 과제의 로컬 하네스 사본에만 기록한다.

## 유지할 확인 기준

- 생성기와 독립적인 기대값·최종 제약 검사, 다른 유효 결과 수용, 고의 오류 검출을 확인한다.
- 정상 A → 오류 B 거절 → 변경 C 적용 → 재계산·저장·조회·내보내기의 판본/조건/내용과 중단·재시작 상태를 연결한다.
- 단일 건·하루와 전체 기간·공유 자원 검증을 구분한다. 규칙 준수와 품질·실행 비용을 나누고 같은 입력의 기준 방법과 비교한다.
- 직접 검사/다른 계층 위임/미구현과 진행 중/임시/최종 상태의 책임·확정·실패 결과를 실제 코드로 기록한다.
- AI 검증·사용자 직접 확인·설명 제공·사용자 이해·실제 제출은 다른 상태다. 미실행과 남은 문제를 공개한다.

실제 시험의 요구·양식·허용 도구가 우선이다. 원문·원본 자료·기존 사용자 변경을 보존하고 변경 검사는 복사본으로 한다. 시험 자료·완성 답안·채운 기록·비밀값을 공개 하네스 저장소에 섞지 않는다. AI 금지 단계의 후속 답변 작성·첨삭은 수행하지 않는다.

공개 배포 주소는 [stagnes307/exam](https://github.com/stagnes307/exam)이다. 설치 명령과 실제 폴더 구조는 START에서 관리한다. 별도 자동 초기화·ZIP 생성은 필요하지 않다.

## 참고한 공개 레포

- [CLM-BONNY/cofa-exam-harness](https://github.com/CLM-BONNY/cofa-exam-harness): 계획·구현·직접 테스트·설명·제출 흐름.
- [GitHub Spec Kit](https://github.com/github/spec-kit/blob/main/templates/spec-template.md): 사용자 흐름과 관찰 가능한 완료 기준.
- [Superpowers](https://github.com/obra/superpowers/blob/main/skills/verification-before-completion/SKILL.md): 현재 변경의 실행 증거와 검사별 입증 범위.
- [AI Ready](https://github.com/johnpapa/ai-ready/blob/main/skills/ai-ready/SKILL.md): 지침 중복·분산과 경로·명령 점검.
