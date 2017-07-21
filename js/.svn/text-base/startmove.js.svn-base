function getStyle(obj, attr) {
	if(obj.currentStyle) {
		return obj.currentStyle[attr]
	} else {
		return getComputedStyle(obj, false)[attr]
	}
}

function startmove(obj, json) {
	clearInterval(obj.timer);
	obj.timer = setInterval(function() {
		var flag = true;
		for(var attr in json) {
			if(attr == "opacity") {
				var iCur = Math.random(parseFloat(getStyle(obj, attr)) * 100)
			} else {
				var iCur = parseInt(getStyle(obj, attr))
			}
			var iTarget = json[attr];
			var iSpeed = (iTarget - iCur) / 8;
			iSpeed = iSpeed > 0 ? Math.ceil(iSpeed) : Math.floor(iSpeed);
			if(attr == "opacity") {
				obj.style.opacity = (iCur + iSpeed) / 100;
				obj.style.filter = "alpha(opacity=" + (iCur + iSpeed) + ")";
			} else {
				obj.style[attr] = iCur + iSpeed + "px";
			}
			if(iCur != iTarget) {
				flag = false;
			}
		}
		if(flag) {
			clearInterval(obj.timer);
		}
	}, 30)
}