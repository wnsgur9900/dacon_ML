# 기업 성공 가능성 예측 - Dacon AI 경진대회

이 프로젝트는 [Dacon 기업 성공 가능성 예측 AI 경진대회](https://dacon.io/competitions/official/236475/leaderboard)에 참가하여 진행한 머신러닝 모델 개발 프로젝트입니다.  
기업의 재무 및 운영 관련 데이터를 바탕으로, 향후 성공 가능성을 예측하는 회귀 모델을 구축했습니다.

---

## 대회 개요

- **대회명**: 기업 성공 가능성 예측 AI 경진대회
- **주최**: Dacon
- **문제 유형**: 회귀 (Success Probability 예측)
- **데이터 구성**: 약 3천 개 기업의 다양한 속성 (재무, 투자단계, 사업유형 등)
- **참가 아이디**: `human_박준혁`
- **최고 순위**: 62위 진입 (약 788명 중) 2025년 05월 12일 기준

---

## 기술 스택 및 도구

- **언어**: Python 3.11
- **라이브러리**: Pandas, NumPy, Scikit-learn, LightGBM, XGBoost, CatBoost
- **모델링 전략**: Gradient Boosting 기반 모델 앙상블
- **앙상블 가중치**: `XGBoost(0.85) + LGBM(0.05) + CatBoost(0.1)`

---

## 주요 작업 내용

### 데이터 전처리

- `기업나이` = 2025 - 설립연도
- `매출/투자비`, `고객당 매출` 등 파생 변수 생성
- Label Encoding 및 One-hot Encoding 수행
- 이상값 및 결측치 처리

### 모델링

- 초기: RandomForestRegressor로 베이스라인 설정
- 최종: XGBoost + LGBM + CatBoost 앙상블 모델
- 성능 기준: RMSE (Root Mean Squared Error)
