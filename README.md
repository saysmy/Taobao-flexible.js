# Taobao-flexible.js
手淘flexible.js插件优化，适应于系统默认字体大小不为16px的手机

    //增加这里: 获取手机系统默认的1rem的大小
    var d = window.document.createElement('div');
    d.style.width = '1rem';
    d.style.display = "none";
    var head = window.document.getElementsByTagName('head')[0];
    head.appendChild(d);
    var defaultFontSize = parseFloat(window.getComputedStyle(d, null).getPropertyValue('width'));
    
    function refreshRem(){
      var width = docEl.getBoundingClientRect().width;
      if (width / dpr > 640) {
        width = 640 * dpr;
      }
      var rem = width / 10;
      //增加这里: 16 为网页自定义的1rem的大小（即htm的font-size）
      rem = rem*16/defaultFontSize;
      docEl.style.fontSize = rem + 'px';
      flexible.rem = win.rem = rem;
    }
