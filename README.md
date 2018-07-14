# javascript-index-functions
I figured I'd make some functions that can help one traverse the DOM

```
function getParentElementByClass(element, className, boundingId) {
	var contNu, refElement, match;
  refElement = element;
  contNu = true;
  match = false;
  do {
  	if (refElement.parentNode) {
    	refElement = refElement.parentNode;
    } else {
    	contNu = false;
    }

    if (refElement.classList.contains(className)) {
    	match = true;
      contNu = false;
    }

    if (boundingId) {
      if (refElement.id === boundingId) {
      contNu = false;
      }
    }
  } while (contNu);

  if (match) {
  	return refElement;
  } else {
  	return false;
  }
}

function getParentElementByID(element, IDName, boundingId) {
	var contNu, refElement, match;
  refElement = element;
  contNu = true;
  match = false;
  do {
  	if (refElement.parentNode) {
    	refElement = refElement.parentNode;
    } else {
    	contNu = false;
    }

    if (refElement.id === IDName) {
    	match = true;
      contNu = false;
    }

    if (boundingId) {
      if (refElement.id === boundingId) {
      contNu = false;
      }
    }
  } while (contNu);

  if (match) {
  	return refElement;
  } else {
  	return false;
  }
}

function getParentElementByAttribute(element, attributeName, attributeValue, boundingId) {
	var contNu, refElement, match;
  refElement = element;
  contNu = true;
  match = false;
  do {
  	if (refElement.parentNode) {
    	refElement = refElement.parentNode;
    } else {
    	contNu = false;
    }

    if (refElement.attributes.getNamedItem(attributeName)) {
      if (attributeValue) {
        if (refElement.attributes.getNamedItem(attributeName).value === attributeValue) {
          match = true;
        }
      } else {
        match = true;
      }
      contNu = false;
    }

    if (boundingId) {
      if (refElement.id === boundingId) {
      contNu = false;
      }
    }
  } while (contNu);

  if (match) {
  	return refElement;
  } else {
  	return false;
  }
}
```
