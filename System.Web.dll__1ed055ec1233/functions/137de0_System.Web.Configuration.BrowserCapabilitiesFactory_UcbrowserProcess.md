# System.Web.Configuration.BrowserCapabilitiesFactory::UcbrowserProcess

- ea: `0x137de0`
- end: `0x137f40`
- name: `System.Web.Configuration.BrowserCapabilitiesFactory::UcbrowserProcess`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x135a20`

## callees

- `0x137dc0`
- `0x137dd0`
- `0x137de0`
- `0x145560`
- `0x145890`
- `0x147670`
- `0x153ff0`
- `0x154100`
- `0x154110`

## string_xrefs

- `0x137e9f`: `tagwriter`
- `0x137ea4`: `System.Web.UI.HtmlTextWriter`
- `0x137eff`: `supportsXmlHttp`

## pseudocode

```c

```

## disassembly

```asm
0x137de0  ldarg.2
0x137de1  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Configuration.HttpCapabilitiesBase::get_Capabilities()
0x137de6  stloc.0
0x137de7  ldarg.2
0x137de8  ldsfld   string [mscorlib]System.String::Empty
0x137ded  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x137df2  stloc.1
0x137df3  ldarg.2
0x137df4  newobj   instance void System.Web.Configuration.RegexWorker::.ctor(class System.Web.HttpBrowserCapabilities browserCaps)
0x137df9  stloc.3
0x137dfa  ldloc.3
0x137dfb  ldloc.1
0x137dfc  ldstr    aUcBrowserUcweb// "(UC Browser |UCWEB)(?'version'(?'major'"...
0x137e01  callvirt instance bool System.Web.Configuration.RegexWorker::ProcessRegex(string target, string regexExpression)
0x137e06  stloc.2
0x137e07  ldloc.2
0x137e08  brtrue.s loc_137E0C
0x137e0a  ldc.i4.0
0x137e0b  ret
0x137e0c  ldloc.0
0x137e0d  ldstr    aBrowser// "browser"
0x137e12  ldstr    aUcbrowser// "UCBrowser"
0x137e17  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e1c  ldloc.0
0x137e1d  ldstr    aMajorversion// "majorversion"
0x137e22  ldloc.3
0x137e23  ldstr    aMajor// "${major}"
0x137e28  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137e2d  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e32  ldloc.0
0x137e33  ldstr    aMinorversion// "minorversion"
0x137e38  ldloc.3
0x137e39  ldstr    aMinor// "${minor}"
0x137e3e  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137e43  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e48  ldloc.0
0x137e49  ldstr    aIsmobiledevice// "isMobileDevice"
0x137e4e  ldstr    aTrue// "true"
0x137e53  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e58  ldloc.0
0x137e59  ldstr    aVersion// "version"
0x137e5e  ldloc.3
0x137e5f  ldstr    aVersion_1// "${version}"
0x137e64  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137e69  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e6e  ldloc.0
0x137e6f  ldstr    aEcmascriptvers// "ecmascriptversion"
0x137e74  ldstr    a30// "3.0"
0x137e79  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e7e  ldloc.0
0x137e7f  ldstr    aJavascript_0// "javascript"
0x137e84  ldstr    aTrue// "true"
0x137e89  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e8e  ldloc.0
0x137e8f  ldstr    aJavascriptvers// "javascriptversion"
0x137e94  ldstr    a15_2// "1.5"
0x137e99  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137e9e  ldloc.0
0x137e9f  ldstr    aTagwriter// "tagwriter"
0x137ea4  ldstr    aSystemWebUiHtm// "System.Web.UI.HtmlTextWriter"
0x137ea9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137eae  ldloc.0
0x137eaf  ldstr    aCookies// "cookies"
0x137eb4  ldstr    aTrue// "true"
0x137eb9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137ebe  ldloc.0
0x137ebf  ldstr    aFrames// "frames"
0x137ec4  ldstr    aTrue// "true"
0x137ec9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137ece  ldloc.0
0x137ecf  ldstr    aSupportscallba// "supportsCallback"
0x137ed4  ldstr    aTrue// "true"
0x137ed9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137ede  ldloc.0
0x137edf  ldstr    aSupportsfileup// "supportsFileUpload"
0x137ee4  ldstr    aTrue// "true"
0x137ee9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137eee  ldloc.0
0x137eef  ldstr    aSupportsmultil// "supportsMultilineTextBoxDisplay"
0x137ef4  ldstr    aTrue// "true"
0x137ef9  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137efe  ldloc.0
0x137eff  ldstr    aSupportsxmlhtt// "supportsXmlHttp"
0x137f04  ldstr    aTrue// "true"
0x137f09  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137f0e  ldloc.0
0x137f0f  ldstr    aTables// "tables"
0x137f14  ldstr    aTrue// "true"
0x137f19  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137f1e  ldarg.2
0x137f1f  ldstr    aUcbrowser// "UCBrowser"
0x137f24  callvirt instance void System.Web.Configuration.HttpCapabilitiesBase::AddBrowser(string browserName)
0x137f29  ldarg.0
0x137f2a  ldarg.1
0x137f2b  ldarg.2
0x137f2c  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::UcbrowserProcessGateways(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137f31  ldc.i4.0
0x137f32  stloc.s  4
0x137f34  ldarg.0
0x137f35  ldloc.s  4
0x137f37  ldarg.1
0x137f38  ldarg.2
0x137f39  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::UcbrowserProcessBrowsers(bool ignoreApplicationBrowsers, class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137f3e  ldc.i4.1
0x137f3f  ret
```
