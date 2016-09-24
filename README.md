# wjw
A library that contains require module,dom operated and event module,ajax and ajaxFile module,type judgement and some data process functions.
> 
###require:
> 
> 1,html:'\<script src="../lib/wjw.js" data-main="../lib/main.js" data-js="../js/r1.js"\>\</script\>';
> 
> 2,main.js:
> 
    wjw.config([{
      basePath:'../js/',
      paths:{
       m1:'m1.js',
       m2:'m2.js',
       m3:'m3.js'
      },
      deps:{
      m2:['m1'],
      m3:['m1','m2']
     }
     },
     {
      paths:{jquery:'../lib/jquery.js'}
     }
    ]);
> 
> 3,r1.js:
> 
> > require(['m1','m3','lib'],function(m11,m33,$){});
> 
> > or define(['m1','m3','lib'],function(m11,m33,$){});
> 
> 4,define:
> 
> > m1:define('m1',function(){});
> 
> > m3:define('m3',['m1','m2'],function(m1,m2){});
> 
###sDom:
> 
> query:s('#id'),s('.class'),s('tag');
> 
> methods(s(selector).method()):
>
    1,eq(i);first();last();prev();next();siblings();parent();closest(selector);children();find(selector);
    2,attr('data')/attr('data','1');removeAttr('data');
    3,hasClass('class');addClass('class');removeClass('class');
    4,css('color')/css('color','#000')/css({'color':'#000','font-size':'12px'});
    5,clone();remove();
    6,append(htmlString/dom/sDom);prepend(htmlString/dom/sDom);before(htmlString/dom/sDom);after(htmlString/dom/sDom);
    7,text()/text('text');html()/html(htmlString/dom/sDom);
> 
###event:
> 
> 1,on('type',handle);on('type1,type2',handle);
> 
> 2,off('type',handle);off('type1,type2',handle);
> 
###ajax:
> 
> 1,GET/POST:
> 
    wjw.ajax({
    > type:'GET/POST',
    > url:'',
    > data:jsonObj,
    > success:function(response){},
    > error:function(response){}
    });
> 
> 2,jsonp:
> 
    wjw.jsonp({
    > url:'',
    > data:jsonObj,
    > overTime:100,
    > success:function(response){},
    > error:function(response){}
    });
    jsonp-php:$jsonpCallback=$_GET['jsonpCallback'];if($jsonpCallback){echo $jsonpCallback.'('.response.')';}
> 
> 3,simple file upload:
> 
    wjw.ajaxFileUpload({
    > inputId:'inputFile',
    > url:'',
    > success:function(response){},
    > error:function(response){}
    });
> 
###typeJudgement:
> 
    (wjw.method(value)):isNull,isUndefined,isNot,isBlank,isNumeric,isNaN,isArrayLike,isString,isBoolean,isNumber,isDate,isArray,isFunction,isCN
    other:isDecimal(value,decimalDigits),isElement(element)
> 
###dataProcess:
> 
    (wjw.method(value)):trim,makeArray,addArray,toHump,error,
    other:random(min,max),inArray(string,string)/inArray(array[i],array),each(array,function(i,obj){})/each(objs,function(key,obj){}),addScript(url);
