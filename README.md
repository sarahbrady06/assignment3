# assignment3
Funtion() { 
var win1 = titanium.ui.createwindow({
title: 'Select Color',
backgroundColor:'3fff'
});
//open window
win.open();
})();


App.js:
Var teas= ['#f5fdc', '#ffe4b5', '#ffe4c4', '#d2b48c',
'c3b091', '#c3b091', '#926f5b', '#804000', '#654321',
'#3d2b1f'];

allrows = []
var the colours =ti.ui.createtableview({});

for(var i=0; i<teas.length; i++) {
therow = ti.ui.createtableviewrow({backgroundcolor:
teas[i], height:50, teacolour;teas[i]});
allrows.push(therows);
)

thecolours.setdata(allrows);
win1.add(thecolours);

function getverdict (colour) {
var indicator = colour.charat (1);
var msg;
//make a crude decision on the strength of the tea based on the second character of the hex color
switch (indicator) {
case 'f': msg = 'milky'; break;
case 'd': msg = 'nice'; break;
case 'c': msg = 'perfect'; break;
case '9': msg = 'a bit strong'; break;
case '8': msg = 'builders tea'; break;
case '6': msg = 'send it back'; break;
case '3': msg = 'no milk here'; break;
}
return msg;
};

function showteaverdict(_args) {
var teaverdict = ti.ui.createwindow({layout: 'vertical'});

teaverdict.backgroundcolor = _args;
teaverdict.msg = getverdict(_args);

var judgement = ti.ui.createlabel
({text: teaverdict.msg, top:'50%'});
var close = ti.ui.createbutton
({title:'choose again', top:'25%'});
close.addeventlistener('click', function(e)
{teaverdict.close();
//release the resources
teaverdict = null;
});

teaverdict.add(judgement);
teaverdict.add(close);
teaverdict.open();
}

var win2 = titanium.ui.createwindow({
backgroundcolor:'#fff'
});

var options = ti.ui.createview({layout: 'vertical'});
var showcamera = ti.ui.createbutton({title: 'show camera'});
var thephoto = ti.ui.createimageview({height: '30%', width: 
'30%'});

options.add(showcamera);
options.add(thephoto);
win2.add(options);

functions showphoto(_args) {
thephoto.setimage(_args.media);
}

showcamera.addeventlistener('click', function (e) {
ti.media.showcamera ({animated: true,
	autohide: true,
	savethephotogallery: true,
	showcontrols: true,
	mediatypes: [ti.media.MEDIA_TYPE_PHOTO],
	success: function(e) {showphoto (e) },
	error: function(e) {alert('there was a problem accessing the camera')}
	)}
});
