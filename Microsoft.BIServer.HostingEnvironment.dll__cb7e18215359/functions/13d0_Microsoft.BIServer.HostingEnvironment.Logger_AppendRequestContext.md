# Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext

- ea: `0x13d0`
- end: `0x13fc`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::AppendRequestContext`
- size: `44`
- prototype: ``
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1410`
- `0x1430`
- `0x1450`
- `0x1470`
- `0x1490`
- `0x1550`
- `0x1570`
- `0x1590`
- `0x15b0`
- `0x15d0`
- `0x15f0`
- `0x1610`
- `0x1630`

## callees

- `0x13d0`
- `0x3250`

## pseudocode

```c

```

## disassembly

```asm
0x13d0  ldsfld   class [NLog]NLog.Logger Microsoft.BIServer.HostingEnvironment.Logger::Log
0x13d5  ldarg.1
0x13d6  callvirt instance bool [NLog]NLog.Logger::IsEnabled(class [NLog]NLog.LogLevel)
0x13db  brtrue.s loc_13DF
0x13dd  ldarg.0
0x13de  ret
0x13df  call     class Microsoft.BIServer.HostingEnvironment.Request.RequestContext Microsoft.BIServer.HostingEnvironment.Request.RequestContext::GetFromCallContext()
0x13e4  stloc.0
0x13e5  ldloc.0
0x13e6  brtrue.s loc_13EA
0x13e8  ldarg.0
0x13e9  ret
0x13ea  ldarg.0
0x13eb  ldstr    asc_7F7C// "| "
0x13f0  ldloc.0
0x13f1  callvirt instance string [mscorlib]System.Object::ToString()
0x13f6  call     string [mscorlib]System.String::Concat(string, string, string)
0x13fb  ret
```
