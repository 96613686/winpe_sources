# System.Xml.Xsl.XsltOld.NavigatorInput::.ctor

- ea: `0xa9f0`
- end: `0xaa70`
- name: `System.Xml.Xsl.XsltOld.NavigatorInput::.ctor`
- size: `128`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x62c0`
- `0xaa70`

## callees

- `0xa3f0`
- `0xa930`
- `0xa9f0`
- `0x14c50`

## string_xrefs

- `0xaa07`: `baseUri`

## pseudocode

```c

```

## disassembly

```asm
0xa9f0  ldarg.0
0xa9f1  call     instance void [mscorlib]System.Object::.ctor()
0xa9f6  ldarg.1
0xa9f7  brtrue.s loc_AA04
0xa9f9  ldstr    aNavigator// "navigator"
0xa9fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa03  throw
0xaa04  ldarg.2
0xaa05  brtrue.s loc_AA12
0xaa07  ldstr    aBaseuri// "baseUri"
0xaa0c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xaa11  throw
0xaa12  ldarg.0
0xaa13  ldnull
0xaa14  stfld    class System.Xml.Xsl.XsltOld.NavigatorInput System.Xml.Xsl.XsltOld.NavigatorInput::_Next
0xaa19  ldarg.0
0xaa1a  ldarg.2
0xaa1b  stfld    string System.Xml.Xsl.XsltOld.NavigatorInput::_Href
0xaa20  ldarg.0
0xaa21  ldarg.1
0xaa22  callvirt instance class [System.Xml]System.Xml.XmlNameTable [System.Xml]System.Xml.XPath.XPathNavigator::get_NameTable()
0xaa27  newobj   instance void System.Xml.Xsl.Xslt.KeywordsTable::.ctor(class [System.Xml]System.Xml.XmlNameTable nt)
0xaa2c  stfld    class System.Xml.Xsl.Xslt.KeywordsTable System.Xml.Xsl.XsltOld.NavigatorInput::_Atoms
0xaa31  ldarg.0
0xaa32  ldarg.1
0xaa33  stfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.NavigatorInput::_Navigator
0xaa38  ldarg.0
0xaa39  ldarg.0
0xaa3a  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.NavigatorInput::_Navigator
0xaa3f  ldarg.3
0xaa40  newobj   instance void System.Xml.Xsl.XsltOld.InputScopeManager::.ctor(class [System.Xml]System.Xml.XPath.XPathNavigator navigator, class System.Xml.Xsl.XsltOld.InputScope rootScope)
0xaa45  stfld    class System.Xml.Xsl.XsltOld.InputScopeManager System.Xml.Xsl.XsltOld.NavigatorInput::_Manager
0xaa4a  ldarg.0
0xaa4b  ldarg.0
0xaa4c  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.NavigatorInput::_Navigator
0xaa51  call     class [System.Xml]System.Xml.PositionInfo [System.Xml]System.Xml.PositionInfo::GetPositionInfo(object)
0xaa56  stfld    class [System.Xml]System.Xml.PositionInfo System.Xml.Xsl.XsltOld.NavigatorInput::_PositionInfo
0xaa5b  ldarg.0
0xaa5c  call     instance valuetype [System.Xml]System.Xml.XPath.XPathNodeType System.Xml.Xsl.XsltOld.NavigatorInput::get_NodeType()
0xaa61  brtrue.s loc_AA6F
0xaa63  ldarg.0
0xaa64  ldfld    class [System.Xml]System.Xml.XPath.XPathNavigator System.Xml.Xsl.XsltOld.NavigatorInput::_Navigator
0xaa69  callvirt instance bool [System.Xml]System.Xml.XPath.XPathNavigator::MoveToFirstChild()
0xaa6e  pop
0xaa6f  ret
```
