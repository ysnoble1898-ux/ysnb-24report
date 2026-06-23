# 연세노블병원 24시간 보고서 시스템

## 파일 구성
```
index.html      ← 메인 앱
manifest.json   ← PWA 설정
sw.js           ← 서비스워커 (오프라인 지원)
icon-192.png    ← 앱 아이콘 (소)
icon-512.png    ← 앱 아이콘 (대)
```

## GitHub Pages 배포 순서

1. GitHub.com 로그인
2. 새 저장소(Repository) 생성
   - 이름: `ynb-24report`
   - Public 선택
3. 위 5개 파일 모두 업로드
4. Settings → Pages → Branch: main → Save
5. 주소: `https://[계정명].github.io/ynb-24report/`

## 초기 로그인
- ID: admin
- PW: noble2024!

## Firebase Firestore 보안 규칙 설정 (30일 후 필수)
Firebase Console → Firestore → 규칙 탭:

```
rules_version = '2';
service cloud.firestore {
  match /databases/{database}/documents {
    match /{document=**} {
      allow read, write: if true;
    }
  }
}
```

## PWA 설치 방법

### 안드로이드 (Chrome)
1. 위 URL 접속
2. 브라우저 메뉴 (⋮) → "홈 화면에 추가"
3. 설치 후 앱처럼 실행 (주소창 없음)

### PC (Chrome/Edge)
1. 위 URL 접속
2. 주소창 오른쪽 ⊕ 아이콘 클릭 → 설치
3. 바탕화면 아이콘으로 실행
