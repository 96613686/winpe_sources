# Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::.ctor

- ea: `0x26f0`
- end: `0x275f`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::.ctor`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3660`

## callees

- `0x26f0`

## pseudocode

```c

```

## disassembly

```asm
0x26f0  ldarg.0
0x26f1  ldstr    aTs// ".ts"
0x26f6  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_tsExtension
0x26fb  ldarg.0
0x26fc  ldstr    aMap// ".map"
0x2701  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_mapExtension
0x2706  ldarg.0
0x2707  ldstr    aFaviconIco// "favicon.ico"
0x270c  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_faviconFileName
0x2711  ldarg.0
0x2712  call     instance void [mscorlib]System.Object::.ctor()
0x2717  ldarg.1
0x2718  brtrue.s loc_2725
0x271a  ldstr    aVirtualroot// "virtualRoot"
0x271f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2724  throw
0x2725  ldarg.0
0x2726  ldstr    a0Assets// "{0}/assets/"
0x272b  ldarg.1
0x272c  call     string [mscorlib]System.String::Format(string, object)
0x2731  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_assetUrls
0x2736  ldarg.0
0x2737  ldstr    a0Api// "{0}/api/"
0x273c  ldarg.1
0x273d  call     string [mscorlib]System.String::Format(string, object)
0x2742  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_apiUrls
0x2747  ldarg.0
0x2748  ldstr    a01_0// "{0}/{1}"
0x274d  ldarg.1
0x274e  ldarg.0
0x274f  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_faviconFileName
0x2754  call     string [mscorlib]System.String::Format(string, object, object)
0x2759  stfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_faviconUrl
0x275e  ret
```
