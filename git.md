### 20221228 수업 정리 

# GIT

## git?

- git은 분산버전관리시스템(DVCS)으로 코드 버전을 관리하는 도구
- 2005년 리눅스 개발자인 리누스 토르발스가 개발
- 컴퓨터 파일의 변경사항을 추적하고 여러 명의 사용자들 간에 파일 작업을 조율  


분산버전관리시스템은 원격 저장소(remote repository)를 통해 협업하고, 모든 히스토리를 클라이언트들이 공유
 
중앙집중식버전관리시스템은 중앙에서 버전을 관리하고 파일을 받아서 사용.

## git 기본 흐름

    1) 작업하면
    2) 변경된 파일을 모아 (add)
    3) 버전으로 남긴다 (commit)
   
        Git 파일은 modified, staged, committed로 관리
        - modified : 파일이 수정된 상태 (add 명령어를 통하여 staging area로) 1통
        - staged: 수정한 파일을 곧 커밋할 것이라고 표시한 상태 (commit 명령어로 저장소) 2통
        - committed : 커밋이 된 상태 3통

## $ git init

    특정 폴더를 git 저장소(repository)로 만들어 git으로 관리
    폴더에 .git 폴더가 생성되며 
    git bash에서는(master) 표기를 확인 할 수있음

## 변경 사항이 생겼을시 버전을 저장하고싶을때 사용!

## $ git add

    - 처음 파일 저장시 사용 버전 업데이트를 위한 초기 저장
    - Working Directory상의 변경 내용을  Staging area에 추가하기 위해 사용
    - untracked / modified 상태의 파일을 staged로 변경

        $ git add . 는 하나씩 add하기 귀찮으니깐 현재 디렉토리에 잇는 파일을 모두  넣어둠

## $ git commit

    - staged 상태의 파일들을 커밋을 통해서 **버전으로 기록함** (add 한번만 하고 그 이후에는 git commit만 해주기!)
    - 커밋 메시지는 변경 사항을 나타낼 수 있도록 명확하게 작성
    - 변경된 부분만 저장하기에 크기가 매우 작다
    - 파일이 달라지지 않으면 성능을 위해 파일을 새로 저장하지 않는다.

    $ git commit -m '<커밋메시지>'
                -m (message를 의미함)

## 현재 상태를 알고 싶어요! 

## $ git status

    git 저장소에 있는 파일의 상태를 확인하기 위해서 활용함 (add 후 파일 확인을 위해 사용)
        Tracked : 이전부터 버전으로 관리되고 있는 파일
            Unmodified _ git status에 나타나지 않음
            Modified _ Changed not staged for commit
            Staged _ Changes to be committed
        Untracked : 버전으로 관리된 적 없는 파일 (파일을 새로 만든경우 )
    (상황)----------------------------------
    Changes to be committed add한 파일 (2통)
    Untracked files 파일은 만들었지만, add를 하지않음 (1통)
    ---------------------------------


## $ git log

   git log (현재 저장소에 기록된 커밋을 조회 기록 볼 수있음)

       $ git log -1 (최근 1개)
       $ git log --oneline (한 줄)
       $ git log -2 --oneline (최근 2개 한 줄)


## 사용자 정보 (commit author) 커밋을 하기 위해 반드시 필요함

    이름/메일 정보 설정 방법
    $ git config --global user.email "메일 "
    $ git config --global user.name "이름"
    $ git config --global -l (저장한 메일,유저 이름 기록 확인시 사용)

    이름/메일 정보 삭제 방법 
    $ git config --global --unset user.name
    $ git config --global --unset user.email
    
    개별 저장소의 설정을 삭제
    $ git config --unset user.name
    $ git config --unset user.email


## 기타 코드 분석

    nothing to commit, working tree clean (*commit 할것 없고 작업 트리가 깨끗하다_ 지난번 저장 이후 작업한것이 없다.) 1,2통 비어있음
    
    Changes not staged for commit:(상황) 커밋된적 있는 보고서 .txt파일을 수정한 상태! 








