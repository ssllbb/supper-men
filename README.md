# supper-men
轮播
<!DOCTYPE <html>
<html>
	<head>
		<meta charset="utf-8">
		<title>document</title>
		<style>
			*{margin:0;padding:0;}
			.warp{
				width:500px;
				height:200px;
				background:red;
				margin:0 auto;
				position:relative;
				overflow:hidden;
			}
			.box{
				width:2000px;
				height:200px;
				position:absolute;
				left:0;
				top:0;
			}
			.list{
				width:500px;
				height:200px;
				float:left;
			}
			.picture{
				width:100%;
				height:100%;
			}
			.control{
				width:30px;
				height:50px;
				line-height:50px;
				text-align:center;
				font-size:25px;
				display:none;
			}
			#left{
				position:absolute;
				left:0;
				top:50%;
				margin-top:-25px;
			}
			#right{
				position:absolute;
				right:0;
				top:50%;
				margin-top:-25px;
			}
			.outside{
				width:250px;
				height:20px;
				border:1px solid black;
				border-radius:20px;
				display:box;
				box-align:center;
				box-pack:center;
				display:-webkit-box;
				-webkit-box-align:center;
				-webkit-box-pack:center;
				position:absolute;
				left:25%;
				bottom:20px;


			}
			.out{
				width:20px;
				height:20px;
				-webkit-box-flex:1;
				border-radius:20px;
				box-align:center;
				box-pack:center;
				display:-webkit-box;
				-webkit-box-align:center;
				-webkit-box-pack:center;

			}
			.ins{
				width:10px;
				height:10px;
				background:#f8f8f8;
				border-radius:10px;
			}
		</style>
	</head>
	<body>
		<div class="warp"id="warp">
			<div class="box"id="box">
				<p class="list"><img class="picture"src="1.jpg"></p>
				<p class="list"><img class="picture"src="2.jpg"></p>
				<p class="list"><img class="picture"src="3.jpg"></p>
				<p class="list"><img class="picture"src="4.jpg"></p>
			</div>
			<div class="outside">
				<div class="out">
					<p class="ins"></p>
				</div>
				<div class="out">
					<p class="ins"></p>
				</div>
				<div class="out">
					<p class="ins"></p>
				</div>
				<div class="out">
					<p class="ins"></p>
				</div>
				
			</div>
			<p>
				<button class="control"id="left"><</button>
				<button class="control"id="right">></button>
			</p>
			<script>
				var warp=document.getElementById("warp")
				warp.onmouseenter=function(){
					left.style.display="block"
					right.style.display="block"
				}
				warp.onmouseleave=function(){
					left.style.display="none"
					right.style.display="none"
				}
				var box=document.getElementById("box");
				var left=document.getElementById("left");
				var right=document.getElementById("right");
				var ins=document.getElementsByClassName("ins");
				console.log(ins.length);
				var a=0;
				left.onclick=function(){
					a--;
					if(a<0){
						a=3;
					}
					box.style.left=a*-500+"px";
					for(var b=0;b<4;b++){
						ins[b].style.background="#f8f8f8"
					}
					ins[a].style.background="red"
				}





				for(var y=0;y<ins.length;y++){
					ins[y].onmousemove=function(){

						for(var d = 0 ; d < ins.length ; d ++){
							ins[d].style.background="#f8f8f8"
						}
		
						
						this.style.background="red";
					}
				}





				right.onclick=function(){
					a++;
					if(a>3){
						a=0
					}
					box.style.left=a*-500+"px";
					for(var c=0;c<4;c++){
						ins[c].style.background="#f8f8f8"
					}
					ins[a].style.background="red"
				}
			</script>
		</div>
	</body>
</html>
