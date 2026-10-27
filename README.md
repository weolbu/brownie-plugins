# brownie 플러그인

Claude Code 와 Codex 에서 brownie 콘솔을 쓰게 해 주는 플러그인 모음이다.

`brownie` 플러그인을 설치하면 AI 에게 말로 brownie 콘솔의 캠페인 · 캔버스 · 세그먼트 · 프로필을 찾아보고 바꾸게 할 수 있다. 모든 요청은 **로그인한 내 운영자 권한**으로 처리된다. 콘솔 화면에서 못 하는 일은 여기서도 못 하고, 여기서 바꾼 것은 화면에서 바꾼 것과 똑같이 기록된다.

플러그인에는 두 가지가 들어 있다.

- **brownie MCP 서버** — `https://console-api.brownie.im/mcp` 에 연결한다.
- **brownie 스킬** — AI 가 API 를 추측하지 않고, 바꾸기 전에 꼭 확인받도록 하는 사용 지침이다.

## Claude Code 에 설치

Claude Code 안에서 차례로 입력한다.

```text
/plugin marketplace add weolbu/brownie-plugins
/plugin install brownie@brownie-plugins
```

터미널에서 하려면 같은 내용을 이렇게 쓴다.

```bash
claude plugin marketplace add weolbu/brownie-plugins
claude plugin install brownie@brownie-plugins
```

## Codex 에 설치

```bash
codex plugin marketplace add weolbu/brownie-plugins
codex plugin add brownie@brownie-plugins
```

Codex 화면에서는 `/plugins` 를 열고 `brownie` 마켓플레이스에서 설치해도 된다. 설치한 뒤에는 새 세션을 연다.

## 플러그인 없이 연결만 하기

스킬 없이 MCP 서버만 붙이고 싶다면 아래 명령 하나로 된다.

Claude Code:

```bash
claude mcp add --transport http brownie https://console-api.brownie.im/mcp
```

Codex:

```bash
codex mcp add brownie --url https://console-api.brownie.im/mcp
```

추가하면 바로 브라우저가 열려 로그인한다.

## 로그인

처음 쓸 때 브라우저가 열리면 **월부 Google 계정**으로 로그인한다. 그 계정이 brownie 콘솔 운영자로 등록돼 있어야 한다.

- Claude Code: 로그인 창이 뜨지 않으면 `/mcp` 에서 `brownie` 를 골라 인증한다.
- Codex: 로그인 창이 뜨지 않으면 `codex mcp login brownie` 를 실행한다.

## 안전 수칙

- 이 서버는 실제 운영 환경이다. 발송 실행 · 테스트 발송은 실제 문자 · 알림톡 · 푸시를 보낸다.
- AI 가 무언가를 바꾸겠다고 하면 대상과 바뀌는 값을 읽고 나서 승인한다. 실제 발송 전에는 내 번호로 테스트 발송부터 한다.
- 권한이 없다는 답(403)이 오면 우회하지 말고 brownie 콘솔 관리자에게 권한을 요청한다.

## 더 보기

자세한 사용법: <https://brownie.im/docs/mcp/>
