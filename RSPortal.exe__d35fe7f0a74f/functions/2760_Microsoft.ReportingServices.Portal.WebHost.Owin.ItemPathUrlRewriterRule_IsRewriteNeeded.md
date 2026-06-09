# Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::IsRewriteNeeded

- ea: `0x2760`
- end: `0x27c8`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::IsRewriteNeeded`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x2760`

## pseudocode

```c

```

## disassembly

```asm
0x2760  ldarg.1
0x2761  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x2766  ldarg.0
0x2767  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_assetUrls
0x276c  ldc.i4.5
0x276d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2772  brtrue.s loc_27C6
0x2774  ldarg.1
0x2775  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x277a  ldarg.0
0x277b  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_apiUrls
0x2780  ldc.i4.5
0x2781  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2786  brtrue.s loc_27C6
0x2788  ldarg.1
0x2789  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x278e  ldarg.0
0x278f  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_faviconUrl
0x2794  ldc.i4.5
0x2795  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x279a  brtrue.s loc_27C6
0x279c  ldarg.1
0x279d  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x27a2  ldarg.0
0x27a3  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_mapExtension
0x27a8  ldc.i4.5
0x27a9  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x27ae  brtrue.s loc_27C6
0x27b0  ldarg.1
0x27b1  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x27b6  ldarg.0
0x27b7  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRewriterRule::_tsExtension
0x27bc  ldc.i4.5
0x27bd  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x27c2  ldc.i4.0
0x27c3  ceq
0x27c5  ret
0x27c6  ldc.i4.0
0x27c7  ret
```
