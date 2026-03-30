# Claude Code 도입 가이드
## 포맷한 PC부터 시작하는 완전 가이드

---

## 목차
1. [Claude Code란?](#claude-code란)
2. [설치 가이드](#설치-가이드)
   - [1단계: Git 설치](#1단계-git-설치-10분)
   - [2단계: VSCode 설치](#2단계-vscode-설치-5분)
   - [3단계: Claude Code 확장 프로그램 설치](#3단계-claude-code-확장-프로그램-설치-3분)
   - [4단계: Claude 인증 설정](#4단계-claude-인증-설정)
     - [옵션 A: Claude Pro 구독](#옵션-a-claude-pro-구독-개인-사용자-권장)
     - [옵션 B: Google Cloud Vertex AI](#옵션-b-google-cloud-vertex-ai-팀기업-사용자-권장)
   - [5단계: 프로젝트 폴더 열기](#5단계-프로젝트-폴더-열기-1분)

---

## Claude Code란?

**Claude Code for VS Code**는 VSCode 에디터 안에서 코드를 읽고, 작성하고, 수정하는 AI 코딩 어시스턴트입니다.

**간단 요약**: VSCode에서 AI한테 "이 코드 고쳐줘", "버그 찾아줘", "새 기능 만들어줘" 하면 알아서 해줍니다.

**확장 프로그램 이름**: "Claude Code for VS Code" (제작자: Anthropic)

---

## 설치 가이드

**총 소요 시간**: 약 20~30분

**필요한 것**:
- 인터넷 연결
- **옵션 A 선택 시**: 신용카드 (월 $20)
- **옵션 B 선택 시**: Gmail 계정 + 담당자에게 권한 요청 (무료)

---

### 1단계: Git 설치 (10분)

Git은 코드 버전 관리 도구입니다. Claude Code와 Unity 프로젝트 개발에 필수입니다.

#### 설치 방법
1. https://git-scm.com/download/win 접속
2. **"64-bit Git for Windows Setup"** 다운로드
3. 설치파일 실행 → 모든 옵션 기본값으로 두고 **"Next"** 계속 클릭 → **"Install"**

#### 설치 확인
1. 키보드 **Windows 키** 누르기 → **"cmd"** 입력 → **Enter**
2. 검은 창(명령 프롬프트)이 열리면 아래를 입력하고 **Enter**:
   ```
   git --version
   ```
3. `git version 2.x.x` 같은 숫자가 나오면 성공

---

### 2단계: VSCode 설치 (5분)

#### 다운로드 및 설치
1. https://code.visualstudio.com/ 접속
2. 파란색 **"Download for Windows"** 버튼 클릭
3. 다운로드된 파일 실행
4. 라이선스 동의 → **"다음"**
5. **중요**: 아래 항목들 **반드시 체크**:
   - ☑ **PATH에 추가** (필수!)
   - ☑ Code(으)로 열기 - 파일 상황에 맞는 메뉴에 추가
   - ☑ Code(으)로 열기 - 디렉터리 상황에 맞는 메뉴에 추가
   - ☑ 지원되는 파일 형식의 편집기로 Code 등록
6. **"설치"** 클릭 → 완료 후 **"마침"**

---

### 3단계: Claude Code 확장 프로그램 설치 (3분)

1. VSCode 실행
2. 왼쪽 사이드바에서 **네모 4개 아이콘** 클릭 (또는 `Ctrl + Shift + X`)
3. 상단 검색창에 **`Claude Code for VS Code`** 입력
4. 검색 결과에서 **제작자: Anthropic** 인 것 선택
5. **"Install"** 클릭

> ⚠️ 비슷한 이름의 다른 확장이 있으니 반드시 **제작자: Anthropic** 인지 확인하세요!

---

### 4단계: Claude 인증 설정

**두 가지 방법 중 선택하세요:**

| 구분 | 옵션 A: Claude Pro 구독 | 옵션 B: Google Cloud |
|------|---------------------|-------------------------|
| **추천 대상** | 개인 사용자 | 팀/기업 사용자 |
| **월 비용** | $20 고정 | **무료** (회사 크레딧) |
| **준비물** | 신용카드 | Google 계정 |
| **설정 난이도** | ⭐ 매우 쉬움 | ⭐⭐ 쉬움 |

- 💳 **개인 비용으로 사용한다** → 옵션 A
- 🏢 **회사 크레딧으로 무료 사용한다** → 옵션 B

---

## 옵션 A: Claude Pro 구독 (개인 사용자 권장)

**월 $20, 설정 가장 간단**

#### A-1. 계정 생성
1. https://claude.ai 접속 → **"Sign Up"** 클릭
2. Google 계정으로 가입 (추천) 또는 이메일로 가입

#### A-2. Pro 구독
1. 로그인 후 우측 상단 **"Upgrade"** 클릭
2. **Pro ($20/월)** 선택 → 카드 정보 입력 → **"Subscribe"**
3. 월 $20, 매달 자동 결제 (언제든 취소 가능)

#### A-3. VSCode에 로그인
1. VSCode에서 `Ctrl + I` 누르기
2. `/login` 입력 후 **Enter**
3. 브라우저가 열리면 **"Authorize"** 클릭
4. VSCode 하단에 계정 이름이 표시되면 성공!

---

## 옵션 B: Google Cloud Vertex AI (팀/기업 사용자 권장)

**회사 크레딧으로 무료 사용**

### 전체 순서 요약
1. 담당자에게 Google 계정 이메일 전달 → 권한 받기
2. Node.js 설치
3. Google Cloud SDK 설치
4. 명령 프롬프트에서 Google 계정 인증 (명령어 2개)
5. VSCode 설정 파일에 3줄 추가
6. VSCode 재시작 → 완료!

---

#### B-1. 담당자에게 권한 요청

**API 담당자에게 연락하여 아래 정보를 전달하세요:**
- 내 **Google 계정 이메일 주소**
- 요청 내용: "Claude Code 사용을 위한 Vertex AI 권한 요청"

담당자가 권한을 추가해줍니다. 완료되면 알림이 옵니다.

> ⚠️ 권한 처리에 **최대 1~2일**이 걸릴 수 있으니 미리 요청해두세요!

---

#### B-2. Node.js 설치 (3분)

명령 프롬프트에서 명령어를 실행하려면 Node.js가 필요합니다.

1. https://nodejs.org 접속
2. **"LTS"** 버전 다운로드 버튼 클릭
3. 다운로드된 파일 실행 → 모든 옵션 기본값으로 두고 **"Next"** 계속 → **"Install"**

**설치 확인:**
1. **Windows 키** → **"cmd"** 입력 → **Enter** (검은 창이 열림)
2. 아래를 입력하고 **Enter**:
   ```
   node --version
   ```
3. `v24.0.0` 같은 숫자가 나오면 성공!

---

#### B-3. Google Cloud SDK 설치 (5분)

Google 계정 인증에 필요한 프로그램입니다.

1. https://cloud.google.com/sdk/docs/install 접속
2. **"Download the Google Cloud CLI installer"** 버튼 클릭
3. 다운로드된 파일 실행 → 모든 옵션 기본값으로 두고 **"다음"** 계속 → **"설치"**
4. 설치 완료까지 약 3분 대기

**설치 확인:**
1. **Windows 키** → **"cmd"** 입력 → **Enter**
2. 아래를 입력하고 **Enter**:
   ```
   gcloud --version
   ```
3. 버전 정보가 나오면 성공! 안 나오면 명령 프롬프트를 닫고 다시 열어서 시도

---

#### B-4. Claude Code 설치 (1분)

1. **Windows 키** → **"cmd"** 입력 → **Enter**
2. 아래를 **그대로 복사해서 붙여넣고** (Ctrl+V) **Enter**:
   ```
   npm install -g @anthropic-ai/claude-code
   ```
3. 설치가 완료될 때까지 기다리기 (1~2분)
4. 아래를 입력하고 **Enter**:
   ```
   claude --version
   ```
5. 버전 숫자가 나오면 성공!

---

#### B-5. Google 계정 인증 (3분) ⭐

**명령어 2개를 순서대로 실행해야 합니다. 둘 다 해야 합니다!**

1. **Windows 키** → **"cmd"** 입력 → **Enter**

2. 아래를 **복사 → 붙여넣기 (Ctrl+V) → Enter**:
   ```
   gcloud auth login
   ```
   - 브라우저가 자동으로 열립니다
   - **담당자에게 권한을 받은 Google 계정** 선택
   - **"허용"** 클릭 → 브라우저 닫기 → 명령 프롬프트로 돌아오기

3. 이어서 아래를 **복사 → 붙여넣기 (Ctrl+V) → Enter**:
   ```
   gcloud auth application-default login
   ```
   - 브라우저가 다시 열립니다
   - **동일한 Google 계정** 선택 → **"허용"** 클릭 → 브라우저 닫기

> ⚠️ **두 번째 명령어(`application-default login`)를 빠뜨리면 Claude가 작동하지 않습니다!**

---

#### B-6. CMD (명령 프롬프트)에서도 사용하려면? (2분)

VSCode Extension만 사용할 경우 이 단계는 **건너뛰어도** 됩니다.
CMD에서 `claude` 명령어를 사용하려면 Windows 환경 변수 설정이 필요합니다.

**1. CMD 열기**

- **Windows 키** → **"cmd"** 입력 → **관리자 권한으로 실행**

**2. 아래 3줄을 순서대로 실행**:

```cmd
setx CLAUDE_CODE_USE_VERTEX 1
setx CLOUD_ML_REGION global
setx ANTHROPIC_VERTEX_PROJECT_ID 여기에_프로젝트ID_입력
```

> 💡 **중요**: `여기에_프로젝트ID_입력` 부분을 실제 프로젝트 ID로 변경한 후 실행하세요.
> (예: `setx ANTHROPIC_VERTEX_PROJECT_ID my-project-123`)

**3. CMD 재시작**

- 현재 CMD 창을 **완전히 닫고** 새로운 CMD 창을 열어야 적용됩니다.

**4. 확인**

새 CMD 창에서 아래 명령어로 확인:
```cmd
echo %CLAUDE_CODE_USE_VERTEX%
echo %ANTHROPIC_VERTEX_PROJECT_ID%
```

> ⚠️ **중요**: VSCode Extension 설정만으로는 CMD에서 작동하지 않습니다. CMD 사용 시 이 단계는 필수입니다!

---

#### B-7. VSCode 설정 파일 수정 (3분)

마지막 단계입니다! VSCode에 "Google Cloud를 사용해라"고 알려주는 설정을 추가합니다.

**1. 설정 파일 열기**

- VSCode에서 `Ctrl + Shift + P` 누르기
- 검색창에 아래를 입력 후 **Enter**:
  ```
  Preferences: Open User Settings (JSON)
  ```

**2. 설정 내용 추가**

파일이 열리면 기존 내용을 **전부 지우고** 아래 내용을 **통째로 붙여넣기**:

```json
{
  "env": {
    "CLAUDE_CODE_USE_VERTEX": "1",
    "CLOUD_ML_REGION": "global",
    "ANTHROPIC_VERTEX_PROJECT_ID": "여기에_프로젝트ID_입력",
    "ANTHROPIC_DEFAULT_SONNET_MODEL": "claude-sonnet-4-6",
    "ANTHROPIC_DEFAULT_HAIKU_MODEL": "claude-haiku-4-5@20251001"
  }
}
```

> 💡 이미 다른 설정 내용이 있다면 전체를 지우지 말고, 담당자에게 문의하세요.

> 🔒 **보안 주의**: `ANTHROPIC_VERTEX_PROJECT_ID`에 실제 프로젝트 ID를 입력한 뒤, 이 settings.json 파일을 GitHub 등 외부에 절대 커밋하지 마세요.

**3. 저장 후 재시작**

- `Ctrl + S` 눌러서 저장
- VSCode 완전히 종료 후 다시 실행

**4. 테스트**

- `Ctrl + I` 눌러 Claude 채팅 열기
- 아래처럼 입력해보기:
  ```
  안녕? 잘 연동됐니?
  ```
- 답변이 오면 **성공!** ✅

---

#### B-8. 잘 안 된다면?

| 이런 증상이라면 | 이렇게 해보세요 |
|------|------|
| Claude가 계속 뭔가를 물어봄 | B-5의 두 번째 명령어(`application-default login`) 다시 실행 |
| "명령어를 찾을 수 없음" 오류 | 명령 프롬프트를 닫고 다시 열어서 재시도 |
| "권한이 없음" 오류 | API 담당자에게 Google 계정 이메일이 전달되었는지 확인 요청 |
| VSCode에서 응답이 없음 | 설정 파일 내용이 제대로 붙여넣어졌는지 확인 후 VSCode 재시작 |
| 그 외 오류 | 오류 메시지 캡처해서 API 담당자에게 문의 |

---

### 5단계: 프로젝트 폴더 열기 (1분)

1. VSCode 상단 메뉴 **File → Open Folder...** 클릭
2. 작업할 프로젝트 폴더 선택 → **"폴더 선택"**
3. "이 폴더의 작성자를 신뢰하십니까?" 메시지가 나오면 **"예, 신뢰합니다"** 클릭

---

## 설치 완료!

이제 Claude Code를 사용할 준비가 끝났습니다.

`Ctrl + I` 로 Claude 채팅을 열고 자유롭게 질문해보세요!

---

**작성일**: 2026-03-27
**버전**: 6.0
**작성자**: younglife2123
