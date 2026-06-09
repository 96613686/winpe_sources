# System.Web.Configuration.BrowserCapabilitiesFactory::MozillaProcess

- ea: `0x136df0`
- end: `0x137023`
- name: `System.Web.Configuration.BrowserCapabilitiesFactory::MozillaProcess`
- size: `563`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x135a20`

## callees

- `0x134910`
- `0x134f30`
- `0x136160`
- `0x136dd0`
- `0x136de0`
- `0x136df0`
- `0x137050`
- `0x1372b0`
- `0x145560`
- `0x145890`
- `0x147670`
- `0x153ff0`
- `0x154110`

## string_xrefs

- `0x136f9d`: `tagwriter`
- `0x136fa2`: `System.Web.UI.HtmlTextWriter`
- `0x136f7d`: `supportsXmlHttp`

## pseudocode

```c

```

## disassembly

```asm
0x136df0  ldarg.2
0x136df1  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Configuration.HttpCapabilitiesBase::get_Capabilities()
0x136df6  stloc.0
0x136df7  ldarg.2
0x136df8  ldsfld   string [mscorlib]System.String::Empty
0x136dfd  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x136e02  stloc.1
0x136e03  ldarg.2
0x136e04  newobj   instance void System.Web.Configuration.RegexWorker::.ctor(class System.Web.HttpBrowserCapabilities browserCaps)
0x136e09  stloc.3
0x136e0a  ldloc.3
0x136e0b  ldloc.1
0x136e0c  ldstr    aMozilla// "Mozilla"
0x136e11  callvirt instance bool System.Web.Configuration.RegexWorker::ProcessRegex(string target, string regexExpression)
0x136e16  stloc.2
0x136e17  ldloc.2
0x136e18  brtrue.s loc_136E1C
0x136e1a  ldc.i4.0
0x136e1b  ret
0x136e1c  ldloc.0
0x136e1d  ldstr    aBrowser// "browser"
0x136e22  ldstr    aMozilla// "Mozilla"
0x136e27  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e2c  ldloc.0
0x136e2d  ldstr    aCookies// "cookies"
0x136e32  ldstr    aTrue// "true"
0x136e37  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e3c  ldloc.0
0x136e3d  ldstr    aEcmascriptvers// "ecmascriptversion"
0x136e42  ldstr    a30// "3.0"
0x136e47  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e4c  ldloc.0
0x136e4d  ldstr    aFrames// "frames"
0x136e52  ldstr    aTrue// "true"
0x136e57  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e5c  ldloc.0
0x136e5d  ldstr    aInputtype// "inputType"
0x136e62  ldstr    aKeyboard// "keyboard"
0x136e67  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e6c  ldloc.0
0x136e6d  ldstr    aIscolor// "isColor"
0x136e72  ldstr    aTrue// "true"
0x136e77  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e7c  ldloc.0
0x136e7d  ldstr    aIsmobiledevice// "isMobileDevice"
0x136e82  ldstr    aFalse// "false"
0x136e87  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e8c  ldloc.0
0x136e8d  ldstr    aJavascript_0// "javascript"
0x136e92  ldstr    aTrue// "true"
0x136e97  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136e9c  ldloc.0
0x136e9d  ldstr    aJavascriptvers// "javascriptversion"
0x136ea2  ldstr    a15_2// "1.5"
0x136ea7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136eac  ldloc.0
0x136ead  ldstr    aMaximumrendere// "maximumRenderedPageSize"
0x136eb2  ldstr    a300000// "300000"
0x136eb7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136ebc  ldloc.0
0x136ebd  ldstr    aScreenbitdepth// "screenBitDepth"
0x136ec2  ldstr    a8// "8"
0x136ec7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136ecc  ldloc.0
0x136ecd  ldstr    aSupportsbold// "supportsBold"
0x136ed2  ldstr    aTrue// "true"
0x136ed7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136edc  ldloc.0
0x136edd  ldstr    aSupportscallba// "supportsCallback"
0x136ee2  ldstr    aTrue// "true"
0x136ee7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136eec  ldloc.0
0x136eed  ldstr    aSupportscss// "supportsCss"
0x136ef2  ldstr    aTrue// "true"
0x136ef7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136efc  ldloc.0
0x136efd  ldstr    aSupportsdivnow// "supportsDivNoWrap"
0x136f02  ldstr    aTrue// "true"
0x136f07  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f0c  ldloc.0
0x136f0d  ldstr    aSupportsfileup// "supportsFileUpload"
0x136f12  ldstr    aTrue// "true"
0x136f17  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f1c  ldloc.0
0x136f1d  ldstr    aSupportsfontna// "supportsFontName"
0x136f22  ldstr    aTrue// "true"
0x136f27  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f2c  ldloc.0
0x136f2d  ldstr    aSupportsfontsi// "supportsFontSize"
0x136f32  ldstr    aTrue// "true"
0x136f37  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f3c  ldloc.0
0x136f3d  ldstr    aSupportsimages// "supportsImageSubmit"
0x136f42  ldstr    aTrue// "true"
0x136f47  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f4c  ldloc.0
0x136f4d  ldstr    aSupportsitalic// "supportsItalic"
0x136f52  ldstr    aTrue// "true"
0x136f57  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f5c  ldloc.0
0x136f5d  ldstr    aSupportsmainta// "supportsMaintainScrollPositionOnPostbac"...
0x136f62  ldstr    aTrue// "true"
0x136f67  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f6c  ldloc.0
0x136f6d  ldstr    aSupportsmultil// "supportsMultilineTextBoxDisplay"
0x136f72  ldstr    aTrue// "true"
0x136f77  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f7c  ldloc.0
0x136f7d  ldstr    aSupportsxmlhtt// "supportsXmlHttp"
0x136f82  ldstr    aTrue// "true"
0x136f87  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f8c  ldloc.0
0x136f8d  ldstr    aTables// "tables"
0x136f92  ldstr    aTrue// "true"
0x136f97  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136f9c  ldloc.0
0x136f9d  ldstr    aTagwriter// "tagwriter"
0x136fa2  ldstr    aSystemWebUiHtm// "System.Web.UI.HtmlTextWriter"
0x136fa7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136fac  ldloc.0
0x136fad  ldstr    aType// "type"
0x136fb2  ldstr    aMozilla// "Mozilla"
0x136fb7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136fbc  ldloc.0
0x136fbd  ldstr    aW3cdomversion// "w3cdomversion"
0x136fc2  ldstr    a10_0// "1.0"
0x136fc7  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x136fcc  ldarg.2
0x136fcd  ldstr    aMozilla// "Mozilla"
0x136fd2  callvirt instance void System.Web.Configuration.HttpCapabilitiesBase::AddBrowser(string browserName)
0x136fd7  ldarg.0
0x136fd8  ldarg.1
0x136fd9  ldarg.2
0x136fda  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::MozillaProcessGateways(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x136fdf  ldc.i4.1
0x136fe0  stloc.s  4
0x136fe2  ldarg.0
0x136fe3  ldarg.1
0x136fe4  ldarg.2
0x136fe5  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::IeProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x136fea  brtrue.s loc_137017
0x136fec  ldarg.0
0x136fed  ldarg.1
0x136fee  ldarg.2
0x136fef  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::InternetexplorerProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x136ff4  brtrue.s loc_137017
0x136ff6  ldarg.0
0x136ff7  ldarg.1
0x136ff8  ldarg.2
0x136ff9  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::FirefoxProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x136ffe  brtrue.s loc_137017
0x137000  ldarg.0
0x137001  ldarg.1
0x137002  ldarg.2
0x137003  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::WebkitProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137008  brtrue.s loc_137017
0x13700a  ldarg.0
0x13700b  ldarg.1
0x13700c  ldarg.2
0x13700d  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::IemobileProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137012  brtrue.s loc_137017
0x137014  ldc.i4.0
0x137015  stloc.s  4
0x137017  ldarg.0
0x137018  ldloc.s  4
0x13701a  ldarg.1
0x13701b  ldarg.2
0x13701c  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::MozillaProcessBrowsers(bool ignoreApplicationBrowsers, class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137021  ldc.i4.1
0x137022  ret
```
