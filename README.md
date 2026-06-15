# YieldNova DeFi - 핵심 소스코드 패키지

## 파일 구조
```
yieldnova-defi/
├── package.json                    ← 의존성 정의
├── drizzle/
│   └── schema.ts                   ← DB 스키마 (레벨, 외상계정, P2P 등)
├── server/
│   ├── routers.ts                  ← tRPC 백엔드 (Admin 로그인, P2P, 외상계정)
│   └── db.ts                       ← DB 헬퍼 (원라인 수수료 정산 로직)
└── client/src/
    ├── App.tsx                     ← 라우트 설정
    └── pages/
        ├── Home.tsx                ← 대시보드 (거래내역 +/- 부호 수정)
        └── Admin.tsx               ← 관리자 패널 (OTP 제거, 외상계정 설정)
```

## 주요 변경사항
- Admin 로그인: OTP 제거, 패스워드 전용
- 외상 계정 설정: 레벨 1-4 강제 지정 + creditOwed 설정
- P2P 전역 토글: 관리자 p2p_enabled 플래그 제어
- 거래내역 부호: 보너스/입금 → +, 출금/전송 → -
- 원라인 수수료: distributeRewardBonuses() 자동 정산

## 빌드 정보
- 최신 안정 빌드: index-BvkAk4MC.js
- 커밋: 82093ed
- 날짜: 2026-06-15
