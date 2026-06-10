## 🔹 Python with GIt and GitHub
파이썬 코드로 배우는 Git & GitHub 실습

## 📦 내용 정리

Git Command

사용자 정보 설정
- git config user.name “[사용자 이름]”
- git config user.email “[이메일 계정]”
- git config --list, user.name, user.email
- git config --global user.name “[사용자 이름]”
- git config --global user.email “[이메일 계정]”

진행 이력 설정
- git status -s, --short
	?? : Untracked
	M : modified
	MM : 파일이 스테이징된 후, 다시 Modified
	A : 경로가 스테이징된 후, 경로 내로 Untracked  파일 발생
- git commit -am “[메세지]” : add + commit

로그 확인
- git log -[출력할 커밋 수]
- git log - p, --patch -[출력할 커밋 수]
- git log --pretty=oneline
- git log --oneline --graph

커밋 상세 정보
- git show, [커밋 해시], HEAD
- git show HEAD^^^, ~n : 몇 단계 이전의 커밋 정보 출력

 내용 비교
- git diff, git diff --statged
- git diff HEAD^ HEAD

스테이징 되돌리기
- git reset, [파일 이름(또는 경로)], --hard, --mixed, --soft
- git result HEAD^, HEAD~n

커밋 수정, 되돌리기, 취소
- git commit --amend, -m”[메세지]”
- git checkout [커밋 해시], master, HEAD~n
- git checkout [태그 이름]

푸쉬된 커밋 되돌리기
- git revert [되돌릴 커밋 해시]
- git revert -n [커밋 해시] : 커밋x, 파일만 되돌리기

참조 이력 확인
- git reblog

업로드 및 업스트림 설정
- git push -u [원격저장소 이름] [로컬저장소 브랜치 이름]
- git push --tags

원격 저장소 연결
- git remote add [원격저장소 이름] [Github URL]
- git remote rm origin

부가 정보 추가
- git tag [태그 이름] [커밋 해시]
	Lightweight 태그 : 태그 이름만 기록
- git tag -a [태그 이름] [커밋 해시]
	Annotated 태그 : 태그 이름, 설명, 서명, 작성자 정보, 날짜 등 포함
- git tag -l, --list
- git -l “[텍스트 필터]” : 특정 조건 만족
- git show [태그 이름] : 태그 부여된 커밋 상세 정보
- git tag -d [태그 이름]

충돌 해결
- git merge --abort : 병합 작업 종

가져오기
- git fetch [브랜치 이름]
- git merge [브랜치 이름]

코드 수정 내역 확인
- git blame [파일 이름]
- git blame [커밋 해시] [파일 이름]
- git blame -L [시작 라인], [끝 라인] [파일 이름]
- git blame -e [파일 이름] : 이메일 정보 표시
- git blame -s [파일 이름] : 커밋 해시만 표시

임시 저장
- git stash : 인덱스 영역 트래킹 파일 임시 저장
- git stash -u : 새롭게 추가된 파일 함께 저장
- git stash save [저장 이름]
- git stash -m “[메시지]”
- git list
- git stash apply, [stash 인덱스]
- git stash drop, [stash 인덱스]
- git stash pop, [stash 인덱스]
- git stash clear

브랜치 관리
- git branch : 브랜치 리스트업
- git branch [브랜치 이름] : 브랜치 생성
- git checkout [브랜치 이름] : 브랜치 전환, -b : 생성 및 전환
- git branch -m [브랜치 이름] [새로운 브랜치 이름] : 브랜치 이름 변경
- git branch -d [브랜치 이름] : 삭제
- git merge [브랜치 이름] : 브랜치 병합

병합
- fast-forward merge : 현재 브랜치에서 base 커밋에 위치해서 단순히 참조 커밋을 이동
- 3-way merge : base 기준 두 븐래치의 변경 사항이 생겨 새로운 커밋이 생기면서 병합
- git merge --ff [브랜치 이름] : fast-forward 관계, 커밋 생성x, 현재 브랜치 참조만 변경
- git merge --no-ff [브랜치 이름] : ff 관계여도 머지 커밋 생성
- git merge --squash [브랜치 이름] : 병합할 프랜치 내용을 하나의 커밋에 합침, 브랜치 정보 생략

브랜치 재배치
- git rebase [브랜치 이름] : 현재 브랜치가 해당 브랜치부터 분기하도록 재배치
- git regase --continue : 충돌 수정 후 재배치 진행
- git rebase --abort : rebase 취소

다른 브랜치 커밋 적용
- git cherry-pick [커밋 해시] : 해당 커밋의 내용 현재 브랜치에 추가
- git cherry-pick [시작] ... [끝] : 구간 commit 추가
- git cherry-pick --abort : 충돌 상황에서 cherry-pick 취소
- git cherry-pick --continue : 충돌 상황 해결 후 진행
