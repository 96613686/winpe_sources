# System.Web.Configuration.BrowserCapabilitiesFactory::Safari3plusProcess

- ea: `0x137af0`
- end: `0x137ca3`
- name: `System.Web.Configuration.BrowserCapabilitiesFactory::Safari3plusProcess`
- size: `435`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1379f0`

## callees

- `0x137ad0`
- `0x137ae0`
- `0x137af0`
- `0x137cd0`
- `0x145560`
- `0x145890`
- `0x147670`
- `0x153ff0`
- `0x154100`
- `0x154110`

## string_xrefs

- `0x137bb5`: `tagwriter`
- `0x137bf5`: `supportsAccesskeyAttribute`
- `0x137bba`: `System.Web.UI.HtmlTextWriter`
- `0x137c55`: `supportsXmlHttp`

## pseudocode

```c

```

## disassembly

```asm
0x137af0  ldarg.2
0x137af1  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Configuration.HttpCapabilitiesBase::get_Capabilities()
0x137af6  stloc.0
0x137af7  ldarg.2
0x137af8  ldsfld   string [mscorlib]System.String::Empty
0x137afd  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x137b02  stloc.1
0x137b03  ldarg.2
0x137b04  newobj   instance void System.Web.Configuration.RegexWorker::.ctor(class System.Web.HttpBrowserCapabilities browserCaps)
0x137b09  stloc.3
0x137b0a  ldloc.3
0x137b0b  ldloc.1
0x137b0c  ldstr    aVersionVersion// "Version/(?'version'(?'major'[3-9]|\\d{2"...
0x137b11  callvirt instance bool System.Web.Configuration.RegexWorker::ProcessRegex(string target, string regexExpression)
0x137b16  stloc.2
0x137b17  ldloc.2
0x137b18  brtrue.s loc_137B1C
0x137b1a  ldc.i4.0
0x137b1b  ret
0x137b1c  ldloc.0
0x137b1d  ldstr    aVersion// "version"
0x137b22  ldloc.3
0x137b23  ldstr    aVersion_1// "${version}"
0x137b28  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137b2d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b32  ldloc.0
0x137b33  ldstr    aMajorversion// "majorversion"
0x137b38  ldloc.3
0x137b39  ldstr    aMajor// "${major}"
0x137b3e  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137b43  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b48  ldloc.0
0x137b49  ldstr    aMinorversion// "minorversion"
0x137b4e  ldloc.3
0x137b4f  ldstr    aMinor// "${minor}"
0x137b54  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137b59  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b5e  ldloc.0
0x137b5f  ldstr    aType// "type"
0x137b64  ldloc.3
0x137b65  ldstr    aSafariMajor// "Safari${major}"
0x137b6a  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137b6f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b74  ldloc.0
0x137b75  ldstr    aEcmascriptvers// "ecmascriptversion"
0x137b7a  ldstr    a30// "3.0"
0x137b7f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b84  ldloc.0
0x137b85  ldstr    aJavascript_0// "javascript"
0x137b8a  ldstr    aTrue// "true"
0x137b8f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137b94  ldloc.0
0x137b95  ldstr    aJavascriptvers// "javascriptversion"
0x137b9a  ldstr    a16_2// "1.6"
0x137b9f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137ba4  ldloc.0
0x137ba5  ldstr    aW3cdomversion// "w3cdomversion"
0x137baa  ldstr    a10_0// "1.0"
0x137baf  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137bb4  ldloc.0
0x137bb5  ldstr    aTagwriter// "tagwriter"
0x137bba  ldstr    aSystemWebUiHtm// "System.Web.UI.HtmlTextWriter"
0x137bbf  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137bc4  ldloc.0
0x137bc5  ldstr    aCookies// "cookies"
0x137bca  ldstr    aTrue// "true"
0x137bcf  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137bd4  ldloc.0
0x137bd5  ldstr    aFrames// "frames"
0x137bda  ldstr    aTrue// "true"
0x137bdf  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137be4  ldloc.0
0x137be5  ldstr    aJavaapplets// "javaapplets"
0x137bea  ldstr    aTrue// "true"
0x137bef  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137bf4  ldloc.0
0x137bf5  ldstr    aSupportsaccess_0// "supportsAccesskeyAttribute"
0x137bfa  ldstr    aTrue// "true"
0x137bff  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c04  ldloc.0
0x137c05  ldstr    aSupportscallba// "supportsCallback"
0x137c0a  ldstr    aTrue// "true"
0x137c0f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c14  ldloc.0
0x137c15  ldstr    aSupportsdivnow// "supportsDivNoWrap"
0x137c1a  ldstr    aFalse// "false"
0x137c1f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c24  ldloc.0
0x137c25  ldstr    aSupportsfileup// "supportsFileUpload"
0x137c2a  ldstr    aTrue// "true"
0x137c2f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c34  ldloc.0
0x137c35  ldstr    aSupportsmainta// "supportsMaintainScrollPositionOnPostbac"...
0x137c3a  ldstr    aTrue// "true"
0x137c3f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c44  ldloc.0
0x137c45  ldstr    aSupportsmultil// "supportsMultilineTextBoxDisplay"
0x137c4a  ldstr    aTrue// "true"
0x137c4f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c54  ldloc.0
0x137c55  ldstr    aSupportsxmlhtt// "supportsXmlHttp"
0x137c5a  ldstr    aTrue// "true"
0x137c5f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c64  ldloc.0
0x137c65  ldstr    aTables// "tables"
0x137c6a  ldstr    aTrue// "true"
0x137c6f  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137c74  ldarg.2
0x137c75  ldstr    aSafari3plus// "Safari3Plus"
0x137c7a  callvirt instance void System.Web.Configuration.HttpCapabilitiesBase::AddBrowser(string browserName)
0x137c7f  ldarg.0
0x137c80  ldarg.1
0x137c81  ldarg.2
0x137c82  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::Safari3plusProcessGateways(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137c87  ldc.i4.1
0x137c88  stloc.s  4
0x137c8a  ldarg.0
0x137c8b  ldarg.1
0x137c8c  ldarg.2
0x137c8d  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::Safari3to4Process(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137c92  brtrue.s loc_137C97
0x137c94  ldc.i4.0
0x137c95  stloc.s  4
0x137c97  ldarg.0
0x137c98  ldloc.s  4
0x137c9a  ldarg.1
0x137c9b  ldarg.2
0x137c9c  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::Safari3plusProcessBrowsers(bool ignoreApplicationBrowsers, class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137ca1  ldc.i4.1
0x137ca2  ret
```
