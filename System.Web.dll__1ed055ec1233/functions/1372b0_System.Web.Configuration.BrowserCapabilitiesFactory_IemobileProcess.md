# System.Web.Configuration.BrowserCapabilitiesFactory::IemobileProcess

- ea: `0x1372b0`
- end: `0x13745d`
- name: `System.Web.Configuration.BrowserCapabilitiesFactory::IemobileProcess`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update`

## callers

- `0x136df0`

## callees

- `0x137290`
- `0x1372a0`
- `0x1372b0`
- `0x137480`
- `0x137510`
- `0x1375c0`
- `0x137670`
- `0x1376f0`
- `0x137770`
- `0x145560`
- `0x145890`
- `0x147670`
- `0x153ff0`
- `0x154100`
- `0x154110`

## string_xrefs

- `0x1373a2`: `supportsAccesskeyAttribute`
- `0x1372e8`: `MSIE (?'msieMajorVersion'\d+)`
- `0x137346`: `IEMobile${msieMajorVersion}`

## pseudocode

```c

```

## disassembly

```asm
0x1372b0  ldarg.2
0x1372b1  callvirt instance class [mscorlib]System.Collections.IDictionary System.Web.Configuration.HttpCapabilitiesBase::get_Capabilities()
0x1372b6  stloc.0
0x1372b7  ldarg.2
0x1372b8  ldsfld   string [mscorlib]System.String::Empty
0x1372bd  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x1372c2  stloc.1
0x1372c3  ldarg.2
0x1372c4  newobj   instance void System.Web.Configuration.RegexWorker::.ctor(class System.Web.HttpBrowserCapabilities browserCaps)
0x1372c9  stloc.3
0x1372ca  ldloc.3
0x1372cb  ldloc.1
0x1372cc  ldstr    aIemobileVersio// "IEMobile.(?'version'(?'major'\\d+)(\\.("...
0x1372d1  callvirt instance bool System.Web.Configuration.RegexWorker::ProcessRegex(string target, string regexExpression)
0x1372d6  stloc.2
0x1372d7  ldloc.2
0x1372d8  brtrue.s loc_1372DC
0x1372da  ldc.i4.0
0x1372db  ret
0x1372dc  ldloc.3
0x1372dd  ldarg.2
0x1372de  ldsfld   string [mscorlib]System.String::Empty
0x1372e3  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x1372e8  ldstr    aMsieMsiemajorv// "MSIE (?'msieMajorVersion'\\d+)"
0x1372ed  callvirt instance bool System.Web.Configuration.RegexWorker::ProcessRegex(string target, string regexExpression)
0x1372f2  pop
0x1372f3  ldloc.0
0x1372f4  ldstr    aLayoutengine// "layoutEngine"
0x1372f9  ldstr    aTrident// "Trident"
0x1372fe  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137303  ldloc.0
0x137304  ldstr    aBrowser// "browser"
0x137309  ldstr    aIemobile// "IEMobile"
0x13730e  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137313  ldloc.0
0x137314  ldstr    aMajorversion// "majorversion"
0x137319  ldloc.3
0x13731a  ldstr    aMajor// "${major}"
0x13731f  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137324  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137329  ldloc.0
0x13732a  ldstr    aMinorversion// "minorversion"
0x13732f  ldloc.3
0x137330  ldstr    aMinor// "${minor}"
0x137335  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x13733a  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13733f  ldloc.0
0x137340  ldstr    aType// "type"
0x137345  ldloc.3
0x137346  ldstr    aIemobileMsiema// "IEMobile${msieMajorVersion}"
0x13734b  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137350  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137355  ldloc.0
0x137356  ldstr    aIsmobiledevice// "isMobileDevice"
0x13735b  ldstr    aTrue// "true"
0x137360  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137365  ldloc.0
0x137366  ldstr    aVersion// "version"
0x13736b  ldloc.3
0x13736c  ldstr    aVersion_1// "${version}"
0x137371  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x137376  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13737b  ldloc.0
0x13737c  ldstr    aJscriptversion// "jscriptversion"
0x137381  ldstr    a56// "5.6"
0x137386  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x13738b  ldloc.0
0x13738c  ldstr    aMsdomversion// "msdomversion"
0x137391  ldloc.3
0x137392  ldstr    aMajorversionMi// "${majorversion}.${minorversion}"
0x137397  callvirt instance string System.Web.Configuration.RegexWorker::get_Item(string key)
0x13739c  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373a1  ldloc.0
0x1373a2  ldstr    aSupportsaccess_0// "supportsAccesskeyAttribute"
0x1373a7  ldstr    aTrue// "true"
0x1373ac  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373b1  ldloc.0
0x1373b2  ldstr    aJavaapplets// "javaapplets"
0x1373b7  ldstr    aTrue// "true"
0x1373bc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373c1  ldloc.0
0x1373c2  ldstr    aSupportsdivnow// "supportsDivNoWrap"
0x1373c7  ldstr    aFalse// "false"
0x1373cc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373d1  ldloc.0
0x1373d2  ldstr    aVbscript// "vbscript"
0x1373d7  ldstr    aTrue// "true"
0x1373dc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373e1  ldloc.0
0x1373e2  ldstr    aInputtype// "inputType"
0x1373e7  ldstr    aVirtualkeyboar// "virtualKeyboard"
0x1373ec  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x1373f1  ldloc.0
0x1373f2  ldstr    aNumberofsoftke// "numberOfSoftkeys"
0x1373f7  ldstr    a2// "2"
0x1373fc  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x137401  ldarg.2
0x137402  ldstr    aIemobile// "IEMobile"
0x137407  callvirt instance void System.Web.Configuration.HttpCapabilitiesBase::AddBrowser(string browserName)
0x13740c  ldarg.0
0x13740d  ldarg.1
0x13740e  ldarg.2
0x13740f  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::IemobileProcessGateways(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137414  ldarg.0
0x137415  ldarg.1
0x137416  ldarg.2
0x137417  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::MonoProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x13741c  pop
0x13741d  ldarg.0
0x13741e  ldarg.1
0x13741f  ldarg.2
0x137420  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::PixelsProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137425  pop
0x137426  ldarg.0
0x137427  ldarg.1
0x137428  ldarg.2
0x137429  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::OsProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x13742e  pop
0x13742f  ldarg.0
0x137430  ldarg.1
0x137431  ldarg.2
0x137432  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::CpuProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137437  pop
0x137438  ldarg.0
0x137439  ldarg.1
0x13743a  ldarg.2
0x13743b  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::VoiceProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x137440  pop
0x137441  ldc.i4.1
0x137442  stloc.s  4
0x137444  ldarg.0
0x137445  ldarg.1
0x137446  ldarg.2
0x137447  call     instance bool System.Web.Configuration.BrowserCapabilitiesFactory::WindowsphoneProcess(class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x13744c  brtrue.s loc_137451
0x13744e  ldc.i4.0
0x13744f  stloc.s  4
0x137451  ldarg.0
0x137452  ldloc.s  4
0x137454  ldarg.1
0x137455  ldarg.2
0x137456  callvirt instance void System.Web.Configuration.BrowserCapabilitiesFactory::IemobileProcessBrowsers(bool ignoreApplicationBrowsers, class [System]System.Collections.Specialized.NameValueCollection headers, class System.Web.HttpBrowserCapabilities browserCaps)
0x13745b  ldc.i4.1
0x13745c  ret
```
