<!DOCTYPE html>
<html>
	<head>
		<meta charset="UTF-8">
		<title></title>
		<style type="text/css">
			.box{
				width:300px;
				height:400px;
				border:1px solid cadetblue;
				margin:0 auto;
			}
			.inTer{
				width:280px;
				height:280px;
				border:1px solid deeppink;
				margin:0 auto;
				margin-top:10px;
				overflow-y:auto 
			}
			textarea{
				display:block;
				width:276px;
				height:65px;
				margin:0 auto;
				margin-top:5px;
			}
		</style>
	</head>
	<body>
		<div class="box">
		<div class="inTer" id="father">
		<p>你好</p></br>
		<p>你好</p></br>
		<p>你好</p></br>
		<p>hello</p></br>
		</div>
		<textarea style="resize:none;" id="txt"></textarea>
		<input type="button" id="btn" value="发送" />
		</div>
		<script>
			var btn = document.getElementById("btn");
			var txt =document.getElementById("txt");
			var father = document.getElementById("father");
			var p = document.getElementById("p");
			btn.onclick=function(){
				if(txt.value==""){
					alert("请勿发送空内容");
				}
				else{
					var son = document.getElementById("p");
					son.style.backgroundColor="yellowgreen";
					son.style.clear="both";
					son.style.float="right";
					son.style.marginRight="5px";
					son.innerText=txt.value;
					father.appendChild(son);
					txt.value="";
					son.scrollIntoView();
				}
			}
			document.onkeydown=function(evt){
				var e = evt || event;
				e.keyCode=e.which=e.charCode;
				if(e.keyCode==13 || e.keyCode==10){
					if(txt.value==""){
						alert("请勿发送空内容");
					}
					else{
						var son = document.createElement("p");
						son.style.backgroundColor="yellowgreen";
                        son.style.clear="both";
                        son.style.float="right";
                        son.style.marginRight="5px";
                        son.innerText=txt.value;
                        father.appendChild(son);
                        txt.value="";
                        son.scrollIntoView();
					}
				}
			}
		</script>
	</body>
</html>
