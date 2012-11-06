BetterDOMDocument is a handy PHP utility class for working with XML. It's a wrapper for PHP's built in DOMDocument that provides a bunch of nice little shortcuts. 

```php
<?php

// We can load a new BetterDOMDocument from either a string or a DOMNode object
$dom = new BetterDOMDocument($xmlstring, $auto_detect_namespaces = TRUE);

// It's easy to output the entire document as an array, which is sometimes easier to work with in PHP
$array = dom->getArray();

// It's easy to query too!
$node_list = $dom->query('//xpath/to/node', $optional_context_node);

// If you know you're only going to find a single DOMNode, you can use a querySingle
$dom_node = $dom->querySingle('//xpath/to/node');

// If you need to register a namespace, thats a snap.
// Note that it can auto-detect them if you pass TRUE as a second parameter to the constructor.
$dom->registerNamespace('kml','http://www.opengis.net/kml/2.2');

// Swapping out DOMNodes is really easy
$dom->replace($DomNode, $replacementNode);

// It's easy to output the XML
$xml = $dom->out();

// Or just output a single DOMNode
$xml = $dom->out($DOMNode);