# Claude Code Skill 목록

> 기준일: 2026-11-09
> Claude Code에서 쓸 수 있는 스킬을 출처별로 정리한 목록입니다.
> 스킬은 요청 내용에 맞으면 자동으로 쓰이고, `/스킬이름`으로 직접 부를 수도 있습니다. (플러그인 스킬은 `/플러그인:스킬이름`)

## 한눈에 보기

| 구분 | 개수 | 위치 |
|---|---|---|
| 1. 직접 만든 스킬 | 2 | `~/.claude/skills/<이름>/SKILL.md` |
| 2. claude.ai 동기화 스킬 (anthropic-skills) | 9 | claude.ai 계정에서 동기화 |
| 3. 플러그인 스킬 | 16 | 설치한 플러그인 (productivity, data, cowork-plugin-management) |
| 4. 기본 제공 스킬 | 16 | Claude Code 내장 |

---

## 1. 직접 만든 스킬

| 스킬 | 언제 쓰나 | 결과물 |
|---|---|---|
| `ipynb-explain` | `.ipynb` 노트북의 설명자료·해설·정리 문서를 만들 때 | 노트북과 같은 폴더에 `<노트북이름>_설명.md` |
| `lecture-outline` | 강의자료(PDF·PPTX·DOCX)를 목차·흐름·개념·내용으로 정리할 때 | 원본과 같은 폴더에 `<원본명>_목차.md` |

### 1.1 ipynb-explain
- **요청 예시**: "이 노트북 설명자료 만들어줘", `/ipynb-explain 실습3.ipynb`
- **문서 구성**: 0. 목적 → 1. 전체 흐름 → 2. 핵심개념 → 3. 데이터 소개 → 4. 과정별 코드 설명 → 5. 전체 결과 요약 → 6. 최종 결과 해석 → 7. 추가로 알아야 할 내용 → 8. 복습 질문 → 9. 한 장 요약 → 10. 참고자료
- **원칙**: 실제 코드와 실제 출력값에 근거하고, 출력이 없는 셀은 "출력 없음(미실행)"으로 적음

### 1.2 lecture-outline
- **요청 예시**: "3. Deep Neural Network.pdf 목차 정리해줘", `/lecture-outline 강의자료.pdf`
- **문서 구성**: Part 1. 층위별 세부 목차 → Part 2. 목차별 흐름 → Part 3. 목차별 핵심 개념 → Part 4. 목차별 내용 → (부록) 한 장 요약표
- **원칙**: 원본 구조를 유지하고, 원본의 오류를 바로잡거나 내용을 보충하면 `※`·`(보충)`으로 표시함

---

## 2. claude.ai 동기화 스킬 (`anthropic-skills:`)

| 스킬 | 용도 |
|---|---|
| `docs` | 공유·댓글이 가능한 Claude Docs 문서 만들기 (보고서, 제안서, 가이드 등). Word·PDF·Markdown으로 내보내기 가능 |
| `docx` | Word 파일(.docx/.dotx) 만들기·읽기·편집, 변경 내용 추적 |
| `pdf` | PDF 읽기·텍스트/표 추출, 합치기·나누기·회전, 워터마크, 양식 채우기, OCR |
| `pptx` | PowerPoint 파일(.pptx/.potx) 만들기·읽기·편집 |
| `xlsx` | 엑셀·CSV 파일 만들기·편집·정리, 수식·차트 |
| `google-workspace` | Google Docs·Sheets·Slides 파일 만들기·수정 |
| `import-memory` | 다른 AI 비서의 메모리 내보내기 파일을 Claude 메모리로 가져오기 |
| `morning` | 아침 브리핑을 HTML 페이지로 만들거나 평일 반복 작업으로 설정 |
| `skill-creator` | 새 스킬 만들기·개선, 스킬 성능 평가 |

---

## 3. 플러그인 스킬

### 3.1 productivity (업무 관리)
| 스킬 | 용도 |
|---|---|
| `productivity:start` | 생산성 시스템 초기 설정, 대시보드 열기 |
| `productivity:task-management` | `TASKS.md` 파일로 할 일 관리 |
| `productivity:memory-management` | 약어·별명·사내 용어를 기억하는 2단계 메모리 시스템 |
| `productivity:update` | 할 일 동기화, 오래된 할 일 정리, 메모리 갱신 |

### 3.2 data (데이터 분석)
| 스킬 | 용도 |
|---|---|
| `data:analyze` | 데이터 질문에 답하기 (간단한 조회부터 전체 분석까지) |
| `data:explore-data` | 데이터셋 프로파일링: 결측치, 분포, 품질 문제 확인 |
| `data:statistical-analysis` | 기술통계, 추세 분석, 이상치 탐지, 가설검정 |
| `data:validate-data` | 분석 결과 공유 전 방법론·정확도·편향 검토 |
| `data:create-viz` | Python으로 발표·보고서용 그래프 만들기 |
| `data:data-visualization` | 차트 종류 선택, matplotlib·seaborn·plotly 시각화 |
| `data:build-dashboard` | 차트·필터·표가 들어간 HTML 대시보드 만들기 |
| `data:sql-queries` | 여러 DB 문법(Snowflake, BigQuery, PostgreSQL 등)으로 SQL 작성·최적화 |
| `data:write-query` | 자연어 요청을 최적화된 SQL로 바꾸기 |
| `data:data-context-extractor` | 회사 데이터 웨어하우스 지식을 담은 데이터 분석 스킬 만들기 |

### 3.3 cowork-plugin-management (플러그인 관리)
| 스킬 | 용도 |
|---|---|
| `cowork-plugin-management:create-cowork-plugin` | 새 플러그인을 처음부터 만들기 |
| `cowork-plugin-management:cowork-plugin-customizer` | 기존 플러그인을 조직의 도구·업무에 맞게 수정 |

---

## 4. Claude Code 기본 제공 스킬

| 스킬 | 용도 |
|---|---|
| `init` | 프로젝트용 `CLAUDE.md` 파일 만들기 |
| `run` | 프로젝트 앱을 실행해서 변경 사항이 실제로 동작하는지 확인 |
| `code-review` | 변경 사항이나 PR의 버그 리뷰 (low ~ max, ultra 단계) |
| `simplify` | 변경된 코드를 더 간단하고 효율적으로 정리 |
| `security-review` | 현재 브랜치 변경 사항의 보안 검토 |
| `claude-api` | Claude API / Anthropic SDK 참고 자료 (모델, 가격, 도구 사용, 캐싱 등) |
| `update-config` | `settings.json` 설정: 권한, 환경변수, hooks |
| `fewer-permission-prompts` | 자주 쓰는 읽기 전용 명령을 허용 목록에 추가해 권한 확인 줄이기 |
| `keybindings-help` | 단축키 바꾸기 (`keybindings.json`) |
| `loop` | 명령을 일정 간격으로 반복 실행 (예: `/loop 5m /foo`) |
| `schedule` | 클라우드에서 정해진 시간에 에이전트 실행 (cron) |
| `plugin-authoring` | Claude 화면·동작을 바꾸는 mod 만들기 (패널, 상태줄, 슬래시 명령, hook) |
| `dataviz` | 차트·그래프·대시보드 디자인 원칙 (색상, 형태, 상호작용) |
| `artifact-design` | Artifact(웹 페이지) 디자인 기본 원칙 |
| `artifact-diagramming` | Artifact 안에 다이어그램 그리기 |
| `artifact-capabilities` | Artifact 페이지에 데이터 저장·공유 같은 기능 추가 |

---

## 새 스킬 추가하는 방법

1. `~/.claude/skills/<스킬이름>/SKILL.md` 파일을 만든다.
2. 파일 맨 위에 frontmatter를 넣는다.
   ```markdown
   ---
   name: 스킬이름
   description: 언제 이 스킬을 쓰는지. 요청 예시를 넣으면 자동으로 잘 불림.
   ---
   ```
3. 아래에 작업 절차, 출력 형식, 체크리스트를 적는다.
4. 새 세션을 열면 목록에 나타난다. 추가한 뒤에는 이 문서의 **1. 직접 만든 스킬** 표도 갱신한다.
