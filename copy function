// 复制按钮
$("#copy").on("click", function(){
  var copyContent = document.getElementById("copyContent");
if(!copyContent.value){
  return false;
}

// 判断是否为ios
/*if(navigator.userAgent.indexOf('iPhone') > -1){
  logisticCode.setSelectionRange(0, 9999); // ios
}else{
  logisticCode.select(); // 选择对象
}*/

// 兼容安卓和IOS的复制文本到剪切板 2018-5-8 mdy by lry 
copyContent.select();
      copyContent.setSelectionRange(0, copyContent.value.length);
      if(document.execCommand("Copy")){
        document.execCommand("Copy"); // 执行浏览器复制命令
        notify.tipToast("复制成功");
      }
});


/**
 document.execCommand()方法
可以允许运行命令来操作可编辑区域的内容，注意，是可编辑区域。
定义：bool = document.execCommand(aCommandName, aShowDefaultUI, aValueArgument);
方法返回一个 Boolean 值，表示操作是否成功。
这个方法在之前的兼容性其实是不太好的，但是好在现在已经基本兼容所有主流浏览器了，在移动端也可以使用。

它只能操作可编辑区域，也就是意味着除了 <input>、<textarea> 这样的输入域以外，是无法使用这个方法的。

遇到的坑:
在Chrome下调试的时候，这个方法时完美运行的。
然后到了移动端调试的时候，ios出现：
1.白屏抖动，仔细看是拉起键盘又瞬间收起；
2.无法复制。
解决：
在代码中添加 input.setAttribute('readonly', 'readonly'); 使这个 <input> 是只读的，就不会拉起键盘了。
由于 input.select() 在ios下并没有选中全部内容，我们需要使用另一个方法来选中内容，
这个方法就是 input.setSelectionRange(0, input.value.length);。
*/
