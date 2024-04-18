# web 실습 기록

- Lorem : 더미문자열 생성

### css last-child, first-child 에러 메모

```html
<div>
  <div class="holiday">5월은 빨간날이 많다</div>
  <div class="holiday">5월 1일</div>
  <div class="holiday">5월 6일</div>
  <div class="holiday">5월 15일</div>
  <div class="holiday">5월 15일</div>
  <div class="holiday">더 많았으면 좋겠다.</div>
  <div class="please">
    쉬는 날은 좋은 게 더 많다 우리는 주4일제로 나아가야한다. 라고 생각한다고.
    말하고 싶다.
  </div>
</div>
<style>
  .holiday:first-child::before {
    content: "✅";
  }
  .holiday:last-child {
    content: "이에요";
    color: red;
  }

  .holiday:last-child::after {
    content: "이말이에요";
    color: rgb(0, 162, 255);
  }
</style>
```

.holiday:last-child 의 속성은 먹히지 않음.  
last-child는 형제노드들 중 마지막 형제를 가리키는건데 여기서 마지막형제는 .please 이기 때문에 적용되지않는다.  
역으로 .please:first-child 를 해도 얘기 첫번째형제가 아니라서 적용안됨!
