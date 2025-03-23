개인 홈페이지 프로젝트
직장 다니면서 시간 날 때마다 함... (그냥 개발하는게 재밌음)
근데 난 BackEnd, DevOps가 주스택인데 왜 Nextjs를 하고있는가...
하다보니 재밌음
근데 이거 어려움
생산성때문에 AI 너무 많이쓰는거같음
근데 덕분에 가성비 있긴한거같음
이거 한 지 벌써 3개월 됨
너무 오랫동안 붙잡고 있나..?
근데 SEO 최적화는 시도도 못 했는뎅...
아무튼 재밌음
사실 취미가 없어서 이거 함
분명 TODO 리스트 엄청 많았던 거 같은데 기억 잘 안남 (아래에 써있는게 커밋 내역보고 적은 한계?)
회고가 참 중요할 거 같음
뭔가 요즘 문서화 잘 안하는 거 같음

### TODO

- ~~Interceptor로 라우팅 벗어나는거 캐치~~
- ~~filter, sort 다시 구현~~
- ~~posts 우측 탭 구현~~
- ~~posts 목차 탭 맨 위, 만 아래 버그 수정~~
- ~~recommend.tsx 해결 - 서버컴포넌트와 클라이언트컴포넌트 분리~~
- ~~import 경로 @로 수정~~
- ~~캐싱 다시 한번~~
- ~~폴더 구조 변경~~
- ~~MySQL에서 MongoDB로 변경~~
- RESTful API로 수정 (경로 지금 뭔가 좀 애매함)
- 메타데이터 제네레이터 수정 (이게 SEO의 꽃인거같은데 어렵다)
- baseUrl 수정 및 배포 (이건 뭐.. 금방할듯 Vercel말고 AWS라 CloudFlare 생각 중)
- 댓글 github auth (깃헙 auth로 댓글 달수있게)
- 게시글 플랫폼 공유 (위하고 비슷)
- 다크모드 수정 (이거 싱크 안 맞는 부분 있음 /w 하조은쌤)
- Type, Interface 정의 제대로
- 핸드폰으로 볼 때 반응형 적용 (적응형인듯?)
- css 공통화 (퍼블리싱...이런1)
- UIUX 생각 (퍼블리싱...이런2)
- 폴더 구조 md 다시
- favicon 수정 (급하지 않음)
- Light House 성능 개선 (최후의 보루)

### MongoDB Command

```sh
docker container exec -it MONGODB_CONTAINER bash
mongosh
show dbs
use DATABASE_NAME
show collections
db.COLLECTION_NAME.find() (.pretty())
db.COLLECTION_NAME.find(OBJECT)
```

### Directory Structure (미완)

```PlainText
project-root/
├── app/                               - App Router의 기본 디렉터리
│   ├── (main)/                        - 라우팅 그룹화
│   │   ├── career/
│   │   │   └── page.tsx               - career 페이지
│   │   │── contact/
│   │   │   └── page.tsx               - contact 페이지
│   │   ├── posts/
│   │   │   ├── [slug]/
│   │   │   │   └── page.tsx           - posts 상세 페이지
│   │   │   └── page.tsx               - posts 목록 페이지
│   │   ├── projects/
│   │   │   ├── [projectId]/
│   │   │   │   └── page.tsx           - projects 상세 페이지
│   │   │   └── page.tsx               - projects 목록 페이지
│   │   ├── layout.tsx                 - main 서비스 레이아웃
│   │   └── page.tsx                   - main 페이지
│   ├── api/
│   │   ├── og/
│   │   │   └── route.tsx              - OG API 라우트
│   │   ├── posts/
│   │   │   └── [postId]/              - [미완]
│   │   └── rss/
│   │       └── route.tsx              - RSS API 라우트
│   ├── favicon.ico
│   ├── layout.tsx                     - 루트 레이아웃
│   └── not-found.tsx                  - 404 페이지
├── components/             
│   ├── layouts/               
│   ├── markdown/           
│   ├── posts/              
│   ├── providers/             
│   └── ui/                
├── config/                
├── content/                
├── database/            
├── lib/                 
├── public/              
│   ├── fonts/
│   └── images/
├── styles/              
│   └── globals.css
├── utils/              
│   └── globals.css
├── next.config.js        
├── tailwind.config.js     
├── tsconfig.json          
└── package.json
```