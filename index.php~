<?php
      session_start();
      $data = $_SESSION["user"];
      $albums = $_SESSION["album"];
      $pathArr = Array();	
	$jsonData = json_decode($albums);
	/*foreach($jsonData as $obj) {
		if($_REQUEST["albumid"] == $obj->id) {
			$diffArr = array_diff(scandir(trim("../".$obj->albumpath)), Array( ".", ".." ) ); 
			$files = json_encode($diffArr);
			$j=1;	
			$pathArr[0] = trim($obj->albumpath)."cover.jpg";		
			 for($i=2; $i<sizeof($diffArr); $i++) {
				$pathArr[$j] = trim($obj->albumpath).$diffArr[$i];
				$j = $j+1;
			 }

			$pathArr[sizeOf($pathArr)] = trim($obj->albumpath)."back.jpg";
			
		}
	}*/
 ?>
<!doctype html>

<!-- paulirish.com/2008/conditional-stylesheets-vs-css-hacks-answer-neither/ -->
<!--[if lt IE 7 ]> <html lang="en" class="no-js ie6"> <![endif]-->
<!--[if IE 7 ]>    <html lang="en" class="no-js ie7"> <![endif]-->
<!--[if IE 8 ]>    <html lang="en" class="no-js ie8"> <![endif]-->
<!--[if IE 9 ]>    <html lang="en" class="no-js ie9"> <![endif]-->
<!--[if (gt IE 9)|!(IE)]><!--> <html lang="en" class="no-js"> <!--<![endif]-->
<head>
	<script>(function(H){H.className=H.className.replace(/\bno-js\b/,'js')})(document.documentElement)</script>
	<meta charset="utf-8">
	<style>
	.js #features {
	margin-left: -12000px; width: 100%;
}
</style>
	<!-- Always force latest IE rendering engine (even in intranet) & Chrome Frame
	   Remove this if you use the .htaccess -->
	<meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1">

	<title></title>
	<meta name="description" content="">
	<meta name="author" content="Marcio Aguiar">

	<!--  Mobile viewport optimized: j.mp/bplateviewport -->
	<meta name="viewport" content="width=device-width, initial-scale=1.0">

	<!-- CSS : implied media="all" -->
	<link rel="stylesheet" href="css/style.css?v=2">
	<link rel="stylesheet" href="css/wow_book.css" type="text/css" />
	<link rel="stylesheet" type="text/css" href="css/preview.css"><!-- Uncomment if you are specifically targeting less enabled mobile browsers
	<link rel="stylesheet" media="handheld" href="css/handheld.css?v=2">  -->

	<link href='//fonts.googleapis.com/css?family=News+Cycle' rel='stylesheet' type='text/css'>
	<!-- All JavaScript at the bottom, except for Modernizr which enables HTML5 elements & feature detects -->
	<script src="js/modernizr-1.6.min.js"></script>

</head>
<body onContextMenu="alert('This function is disabled'); return false;">
  		<div class='companylogo'><img src="../logo2.png" height="80px"></div>
		<div class='couplename'></div>
		

	<div id="container">
		<nav>
			<ul>
				<li><a id='first'     href="#" title='goto first page'   >First page</a></li>
				<li><a id='back'      href="#" title='go back one page'  >Back</a></li>
				<li><a id='next'      href="#" title='go foward one page'>Next</a></li>
				<li><a id='last'      href="#" title='goto last page'    >last page</a></li>
				<li><a id='zoomin'    href="#" title='zoom in'           >Zoom In</a></li>
				<li><a id='zoomout'   href="#" title='zoom out'          >Zoom Out</a></li>
				<li><a id='slideshow' href="#" title='start slideshow'   >Slide Show</a></li>
				<li><a id='flipsound' href="#" title='flip sound on/off' >Flip sound</a></li>
				<li><a id='fullscreen' href="#" title='fullscreen on/off' >Fullscreen</a></li>
				<li><a id='thumbs'    href="#" title='thumbnails on/off' >Thumbs</a></li>
		        	<li><a id='backtolocation' href="viewAlbums.php" title='Back to Albums'>Back</a></li>
			</ul>
		</nav>
	<div id="main">
		<img id='click_to_open' src="images/click_to_open.png" alt='click to open' />
		<div id='features'>
			 <?php
			      $jsonData = json_decode($albums);

			      foreach($jsonData as $obj) {
				 if($_REQUEST["albumid"] == $obj->id) {
				     $cn = $obj->couplename;	
				     $diffArr = array_diff( scandir(trim($obj->albumpath)), Array( ".", ".." ) ); 
				     $files = json_encode($diffArr);
				     
		
				    echo "<div id='cover' style='background:#ffffff url(".trim($obj->albumpath)."cover.jpg) no-repeat;'>"."</div>";

				     for($i=2; $i<sizeof($diffArr); $i++) {
				        echo "<div data-double='true' >".
				        "<img src='".trim($obj->albumpath).$diffArr[$i]."' class='albumimg' />".
				        "</div>";
				     }
				     
				     echo "<div class='last_cover'>".
				     "<img src='".trim($obj->albumpath)."back.jpg' width='100%' height='100%' />".
				     "</div>";           
				  }
			      }
			?>  			
		</div> <!-- features -->

	</div>
	<div id='thumbs_holder'>
	</div>
	<footer>

	</footer>
	</div> <!--! end of #container -->
</div>

	<!-- Javascript at the bottom for fast page loading -->

	<!-- Grab Google CDN's jQuery. fall back to local if necessary -->
	<script src="//ajax.googleapis.com/ajax/libs/jquery/1.9.1/jquery.min.js"></script>
	<script>!window.jQuery && document.write(unescape('%3Cscript src="js/jquery-1.9.1.min.js"%3E%3C/script%3E'))</script>

	<script type="text/javascript" src="js/wow_book.min.js"></script>

	<script type="text/javascript">
		$(document).ready(function() {
			/**** 
				var imgArr = <?php echo json_encode($pathArr); ?>;
			$('#features').html("");			
			$('#features').append("<div id='cover'>"+
			"</div>");			
			$.each(imgArr,function(i,item){
				if(item == "images/albums/21/Couple/cover.jpg"){}else if(item=="images/albums/21/Couple/back.jpg"){
				}else{
					$('#features').append(
						"<div data-double='true' >"+
						"<img src='"+item+"' class='albumimg' ></div>"
					);
				}				
			});	
			
			$('#features').append("<div class='last_cover'>"+
				"<img src='images/albums/21/Couple/back.jpg' width='100%' height='100%' >"+
				"</div>");
			****/

			var img_width  = $('.albumimg:eq(3)').width();
			var img_height = $('.albumimg:eq(3)').height();

			$('#container').find('nav').css('top',$(window).height()-100);
			$('.couplename').text("Couple name : <?php echo $cn ?>");
			$('#features').wowBook({
				 height : img_height
				,width  : img_width
				,centeredWhenClosed : true
				,hardcovers : true
				,turnPageDuration : 1000
				,numberedPages : [1,-2]
				,controls : {
						zoomIn    : '#zoomin',
						zoomOut   : '#zoomout',
						next      : '#next',
						back      : '#back',
						first     : '#first',
						last      : '#last',
						slideShow : '#slideshow',
						flipSound : '#flipsound',
						thumbnails : '#thumbs',
						fullscreen : '#fullscreen'
					}
				,scaleToFit: "#container"
				,thumbnailsPosition : 'bottom'
				,onFullscreenError : function(){
					var msg="Fullscreen failed.";
					if (self!=top) msg="The frame is blocking full screen mode. Click on 'remove frame' button above and try to go full screen again."
					alert(msg);
				}
			}).css({'display':'none', 'margin':'auto'}).fadeIn(1000);

			$("#cover").click(function(){
				$.wowBook("#features").advance();
			});

			var book = $.wowBook("#features");

			function rebuildThumbnails(){
				book.destroyThumbnails()
				book.showThumbnails()
				$("#thumbs_holder").css("marginTop", -$("#thumbs_holder").height()/2)
			}
			$("#thumbs_position button").on("click", function(){
				var position = $(this).text().toLowerCase()
				if ($(this).data("customized")) {
					position = "top"
					book.opts.thumbnailsParent = "#thumbs_holder";
				} else {
					book.opts.thumbnailsParent = "body";
				}
				book.opts.thumbnailsPosition = position
				rebuildThumbnails();
			})
			$("#thumb_automatic").click(function(){
				book.opts.thumbnailsSprite = null
				book.opts.thumbnailWidth = null
				rebuildThumbnails();
			})
			$("#thumb_sprite").click(function(){
				book.opts.thumbnailsSprite = "images/thumbs.jpg"
				book.opts.thumbnailWidth = 136
				rebuildThumbnails();
			})
			$("#thumbs_size button").click(function(){
				var factor = 0.02*( $(this).index() ? -1 : 1 );
				book.opts.thumbnailScale = book.opts.thumbnailScale + factor;
				rebuildThumbnails();
			})

		});
	</script>

	<!-- scripts concatenated and minified via ant build script-->
	<script src="js/plugins.js"></script>
	<script src="js/script.js"></script>
	<!-- end concatenated and minified scripts-->

	<!--[if lt IE 7 ]>
	<script src="js/libs/dd_belatedpng.js"></script>
	<script> DD_belatedPNG.fix('img, .png_bg'); //fix any <img> or .png_bg background-images </script>
	<![endif]-->

</body>
</html>

