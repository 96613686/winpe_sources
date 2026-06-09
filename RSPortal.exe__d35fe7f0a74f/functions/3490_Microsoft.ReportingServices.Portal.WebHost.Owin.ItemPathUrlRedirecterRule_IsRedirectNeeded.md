# Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::IsRedirectNeeded

- ea: `0x3490`
- end: `0x34be`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::IsRedirectNeeded`
- size: `46`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x3490`

## string_xrefs

- `0x3499`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x3490  ldarg.0
0x3491  ldfld    bool Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_appendItemPath
0x3496  brfalse.s loc_34AC
0x3498  ldarg.2
0x3499  ldstr    aItempath// "ItemPath"
0x349e  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection::Get(string)
0x34a3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x34a8  brfalse.s loc_34AC
0x34aa  ldc.i4.0
0x34ab  ret
0x34ac  ldarg.0
0x34ad  ldfld    class [System]System.Text.RegularExpressions.Regex Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_matchClassicPath
0x34b2  ldarg.1
0x34b3  callvirt instance string [System]System.Uri::get_AbsolutePath()
0x34b8  callvirt instance bool [System]System.Text.RegularExpressions.Regex::IsMatch(string)
0x34bd  ret
```
