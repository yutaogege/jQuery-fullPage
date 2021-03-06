<h2>简介</h2>
<p>如今我们经常能见到全屏网站，尤其是国外网站。这些网站用几幅很大的图片或色块做背景，再添加一些简单的内容，显得格外的高端大气上档次。比如 iPhone 5C 的介绍页面（<a href="http://www.apple.com/cn/iphone-5c/" target="_blank">查看</a>），QQ浏览器的官网站。如果你也希望你的网站能设计成全屏的，显得更上档次，你可以试试 fullPage.js。</p>
<p>fullPage.js 是一个基于 jQuery 的插件，它能够很方便、很轻松的制作出全屏网站，主要功能有：</p>
<ul>
<li>支持鼠标滚动</li>
<li>支持前进后退和键盘控制</li>
<li>多个回调函数</li>
<li>支持手机、平板触摸事件</li>
<li>支持 CSS3 动画</li>
<li>支持窗口缩放</li>
<li>窗口缩放时自动调整</li>
<li>可设置滚动宽度、背景颜色、滚动速度、循环选项、回调、文本对齐方式等等</li>
</ul>
<h2>兼容性</h2>
<h3>jQuery 兼容</h3>
<p>兼容 jQuery 1.7+。</p>
<h3>浏览器兼容</h3>
<table>
<thead>
<tr>
<th><img title="IE" src="http://cdn.dowebok.com/global/ie.png" alt="IE"></th>
<th><img title="Chrome" src="http://cdn.dowebok.com/global/chrome.png" alt="Chrome"></th>
<th><img title="Firefox" src="http://cdn.dowebok.com/global/firefox.png" alt="Firefox"></th>
<th><img title="Opera" src="http://cdn.dowebok.com/global/opera.png" alt="Opera"></th>
<th><img title="Safari" src="http://cdn.dowebok.com/global/safari.png" alt="Safari"></th>
</tr>
</thead>
<tbody>
<tr>
<td>IE8+ ✔</td>
<td>Chrome ✔</td>
<td>Firefox ✔</td>
<td>Opera ✔</td>
<td>Safari ✔</td>
</tr>
</tbody>
</table>
<h2>使用方法</h2>
<h3>1、引入文件</h3>
<pre class="brush:xml">&lt;link rel="stylesheet" href="css/jquery.fullPage.css"&gt;
&lt;script src="js/jquery.min.js"&gt;&lt;/script&gt;

&lt;!-- jquery.easings.min.js 用于 easing 参数，也可以使用完整的 jQuery UI 代替，如果不需要设置 easing 参数，可去掉改文件 --&gt;
&lt;script src="js/jquery.easings.min.js"&gt;&lt;/script&gt;

&lt;!-- 如果 scrollOverflow 设置为 true，则需要引入 jquery.slimscroll.min.js，一般情况下不需要 --&gt;
&lt;script src="js/jquery.slimscroll.min.js"&gt;&lt;/script&gt;

&lt;script src="js/jquery.fullPage.js"&gt;&lt;/script&gt;</pre>
<h3>2、HTML</h3>
<pre>&lt;div id="dowebok"&gt;
&nbsp;&nbsp;&nbsp; &lt;div class="section"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;h3&gt;第一屏&lt;/h3&gt;
&nbsp;&nbsp;&nbsp; &lt;/div&gt;
&nbsp;&nbsp;&nbsp; &lt;div class="section"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;h3&gt;第二屏&lt;/h3&gt;
&nbsp;&nbsp;&nbsp; &lt;/div&gt;
&nbsp;&nbsp;&nbsp; &lt;div class="section"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;h3&gt;第三屏&lt;/h3&gt;
&nbsp;&nbsp;&nbsp; &lt;/div&gt;
&nbsp;&nbsp;&nbsp; &lt;div class="section"&gt;
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &lt;h3&gt;第四屏&lt;/h3&gt;
&nbsp;&nbsp;&nbsp; &lt;/div&gt;
&lt;/div&gt;</pre>
<p>每个 section 代表一屏，默认显示“第一屏”，如果要指定加载页面时显示的“屏幕”，可以在对应的 section 加上 class=”active”，如：</p>
<pre>&lt;div class="section active"&gt;第三屏&lt;/div&gt;</pre>
<p>同时，可以在 section 内加入 slide，如：</p>
<pre class="brush:xml">&lt;div id="dowebok"&gt;
&nbsp;&nbsp; &nbsp;&lt;div class="section"&gt;第一屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&lt;div class="section"&gt;第二屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&lt;div class="section"&gt;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&lt;div class="slide"&gt;第三屏的第一屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&lt;div class="slide"&gt;第三屏的第二屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&lt;div class="slide"&gt;第三屏的第三屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&nbsp;&nbsp; &nbsp;&lt;div class="slide"&gt;第三屏的第四屏&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&lt;/div&gt;
&nbsp;&nbsp; &nbsp;&lt;div class="section"&gt;第四屏&lt;/div&gt;
&lt;/div&gt;</pre>
<h3>3、JavaScript</h3>
<pre class="brush:js">$(function(){
&nbsp;&nbsp; &nbsp;$('#dowebok').fullpage();
});</pre>
<h2>配置</h2>
<h3>1、选项</h3>
<table class="table">
<thead>
<tr>
<th>选项</th>
<th width="50px">类型</th>
<th>默认值</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>verticalCentered</td>
<td>字符串</td>
<td>true</td>
<td>内容是否垂直居中</td>
</tr>
<tr>
<td>resize</td>
<td>布尔值</td>
<td>false</td>
<td>字体是否随着窗口缩放而缩放</td>
</tr>
<tr>
<td>slidesColor</td>
<td>函数</td>
<td>无</td>
<td>设置背景颜色</td>
</tr>
<tr>
<td>anchors</td>
<td>数组</td>
<td>无</td>
<td>定义锚链接</td>
</tr>
<tr>
<td>scrollingSpeed</td>
<td>整数</td>
<td>700</td>
<td>滚动速度，单位为毫秒</td>
</tr>
<tr>
<td>easing</td>
<td>字符串</td>
<td>easeInQuart</td>
<td>滚动动画方式</td>
</tr>
<tr>
<td>menu</td>
<td>布尔值</td>
<td>false</td>
<td>绑定菜单，设定的相关属性与 anchors 的值对应后，菜单可以控制滚动</td>
</tr>
<tr>
<td>navigation</td>
<td>布尔值</td>
<td>false</td>
<td>是否显示项目导航</td>
</tr>
<tr>
<td>navigationPosition</td>
<td>字符串</td>
<td>right</td>
<td>项目导航的位置，可选 left 或 right</td>
</tr>
<tr>
<td>navigationColor</td>
<td>字符串</td>
<td>#000</td>
<td>项目导航的颜色</td>
</tr>
<tr>
<td>navigationTooltips</td>
<td>数组</td>
<td>空</td>
<td>项目导航的 tip</td>
</tr>
<tr>
<td>slidesNavigation</td>
<td>布尔值</td>
<td>false</td>
<td>是否显示左右滑块的项目导航</td>
</tr>
<tr>
<td>slidesNavPosition</td>
<td>字符串</td>
<td>bottom</td>
<td>左右滑块的项目导航的位置，可选 top 或 bottom</td>
</tr>
<tr>
<td>controlArrowColor</td>
<td>字符串</td>
<td>#fff</td>
<td>左右滑块的箭头的背景颜色</td>
</tr>
<tr>
<td>loopBottom</td>
<td>布尔值</td>
<td>false</td>
<td>滚动到最底部后是否滚回顶部</td>
</tr>
<tr>
<td>loopTop</td>
<td>布尔值</td>
<td>false</td>
<td>滚动到最顶部后是否滚底部</td>
</tr>
<tr>
<td>loopHorizontal</td>
<td>布尔值</td>
<td>true</td>
<td>左右滑块是否循环滑动</td>
</tr>
<tr>
<td>autoScrolling</td>
<td>布尔值</td>
<td>true</td>
<td>是否使用插件的滚动方式，如果选择 false，则会出现浏览器自带的滚动条</td>
</tr>
<tr>
<td>scrollOverflow</td>
<td>布尔值</td>
<td>false</td>
<td>内容超过满屏后是否显示滚动条</td>
</tr>
<tr>
<td>css3</td>
<td>布尔值</td>
<td>false</td>
<td>是否使用 CSS3 transforms 滚动</td>
</tr>
<tr>
<td>paddingTop</td>
<td>字符串</td>
<td>0</td>
<td>与顶部的距离</td>
</tr>
<tr>
<td>paddingBottom</td>
<td>字符串</td>
<td>0</td>
<td>与底部距离</td>
</tr>
<tr>
<td>fixedElements</td>
<td>字符串</td>
<td>无</td>
<td></td>
</tr>
<tr>
<td>normalScrollElements</td>
<td></td>
<td>无</td>
<td></td>
</tr>
<tr>
<td>keyboardScrolling</td>
<td>布尔值</td>
<td>true</td>
<td>是否使用键盘方向键导航</td>
</tr>
<tr>
<td>touchSensitivity</td>
<td>整数</td>
<td>5</td>
<td></td>
</tr>
<tr>
<td>continuousVertical</td>
<td>布尔值</td>
<td>false</td>
<td>是否循环滚动，与 loopTop 及 loopBottom 不兼容</td>
</tr>
<tr>
<td>animateAnchor</td>
<td>布尔值</td>
<td>true</td>
<td></td>
</tr>
<tr>
<td>normalScrollElementTouchThreshold</td>
<td>整数</td>
<td>5</td>
<td></td>
</tr>
</tbody>
</table>
<h3>2、方法</h3>
<table class="table">
<thead>
<tr>
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>moveSectionUp()</td>
<td>向上滚动</td>
</tr>
<tr>
<td>moveSectionDown()</td>
<td>向下滚动</td>
</tr>
<tr>
<td>moveTo(section, slide)</td>
<td>滚动到</td>
</tr>
<tr>
<td>moveSlideRight()</td>
<td>slide 向右滚动</td>
</tr>
<tr>
<td>moveSlideLeft()</td>
<td>slide 向左滚动</td>
</tr>
<tr>
<td>setAutoScrolling()</td>
<td>设置页面滚动方式，设置为 true 时自动滚动</td>
</tr>
<tr>
<td>setAllowScrolling()</td>
<td>添加或删除鼠标滚轮/触控板控制</td>
</tr>
<tr>
<td>setKeyboardScrolling()</td>
<td>添加或删除键盘方向键控制</td>
</tr>
<tr>
<td>setScrollingSpeed()</td>
<td>定义以毫秒为单位的滚动速度</td>
</tr>
</tbody>
</table>
<h3>3、回调函数</h3>
<table class="table">
<thead>
<tr>
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr>
<td>afterLoad</td>
<td>滚动到某一屏后的回调函数，接收 anchorLink 和 index 两个参数，anchorLink 是锚链接的名称，index 是序号，从1开始计算</td>
</tr>
<tr>
<td>onLeave</td>
<td>滚动前的回调函数，接收 index、nextIndex 和 direction 3个参数：index 是离开的“页面”的序号，从1开始计算；<p></p>
<p>nextIndex 是滚动到的“页面”的序号，从1开始计算；</p>
<p>direction 判断往上滚动还是往下滚动，值是 up 或 down。</p></td>
</tr>
<tr>
<td>afterRender</td>
<td>页面结构生成后的回调函数，或者说页面初始化完成后的回调函数</td>
</tr>
<tr>
<td>afterSlideLoad</td>
<td>滚动到某一水平滑块后的回调函数，与 afterLoad 类似，接收 anchorLink、index、slideIndex、direction 4个参数</td>
</tr>
<tr>
<td>onSlideLeave</td>
<td>某一水平滑块滚动前的回调函数，与 onLeave 类似，接收 anchorLink、index、slideIndex、direction 4个参数</td>
</tr>
</tbody>
</table>
