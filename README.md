# 팀명 : A

## 이름 : 김진솔(팀장: Android), 김정민(팀원: Server/ WebFront), 정은수(팀원: Design)

### 졸업작품 소개: URL

### 개인 포트폴리오 소개: URL

작품명: ab씨 
작품소개: 가계부앱

# 개발 일지

## 2022-11-16
- xml 다수 교체
- logo교체
- retrofit의 Get에 QueryMap을 이용하여 list에 data 넣기 완료.
- @Path를 이용하여 현재 날짜를 받아와서 API 요청하기 완료
- list 화면에 달(월) 변경시 그에 맞는 list 데이터를 불러오기 완료.
- 월 변경시 데이터 중복 방지 완료.
- 이전 달에 데이터가 없을 경우 다음 달의 데이터가 들어가 있어 데이터 충돌이 남
  - 해결 : if (response.body()?.result?.isEmpty() == true) { //response.body.result에 데이터가 없을 경우
                    Toast.makeText(context,"데이터 없음", Toast.LENGTH_SHORT).show() //Toast 메시지
                    datas.clear()  //datas = mutaableListOf<ListData>().clear
                    // 어댑터 연결 부분 다시 붙여주기
                    listFragRecylcerAdapter = ListFragRecylcerAdapter(datas)
                    recycler_view.layoutManager = LinearLayoutManager(activity,RecyclerView.VERTICAL,false)
                    recycler_view.setHasFixedSize(true)
                    recycler_view.adapter = listFragRecylcerAdapter
                    listFragRecylcerAdapter.datas = datas
                    listFragRecylcerAdapter.notifyDataSetChanged() //데이터 전체 갱신
- calendar 화면 날짜에 수입|지출 확인 후 +,-를 색깔별로 표시해줘야함 <- 미완

## 2022-11-09
- 회원가입 및 로그인 기능 완성
- 데이터를 받아와서 list에 뿌려주어야함 (미완)

## 2022-09-28
- sigin API 연결 완


## 2022-09-14
- ViewPager2를 이용하여 custom calendar만들기
  - RecyclerView의 GridLayout 사용
  - 캘린더 기능
    - 위 아래로 스크롤 할때 전-현-다음 달 보여주기
    - 날짜 보여주기
    - 현재 달의 날짜가 아니면 회색 처리
    - 일별 데이터를 보여줄 위치 정함
  - 클릭 이벤트 미구현
  - 데이터 받아와야함
- ListView
  - 가상의 데이터 넣어서 완성
- API를 연결하여 데이터를 받아 캘린더와 리스트에 뿌려주어야함
    

## 2022-09-14
- 로그인 개발 
- 거래 생성
- 거래 수정
- 거래 삭제
- 거래 조회
완료

### 2022/09/07
- ERD 설계 완료
- 회원가입 개발 완료
- 회원가입 테스트 코드 추가 완료


### 2022/08/31
- 화면 구조 설정
- 회원 관련 기능 정리
    - 회원 가입
    - 로그인 (네이버 로그인 추가)
    - 로그아웃
- 가계부 관련 기능
    - 수입 추가
    - 수입 삭제
    - 지출 추가
    - 지출 삭제
    - 일별 수입 지출 내역 조회
    - 월별 수입 지출 내역 조회
    - 연도별 수입 지출 내역 조회
    - 통계 (사용 카테고리 별 지출 내역 조회, 수입 내역 조회)
    - 예산 기능 (한달 예산 설정 및 초과 금액 같은거)
    - 고정비 알고리즘 (지출 내역 분석후 고정비를 찾아낸다.)
