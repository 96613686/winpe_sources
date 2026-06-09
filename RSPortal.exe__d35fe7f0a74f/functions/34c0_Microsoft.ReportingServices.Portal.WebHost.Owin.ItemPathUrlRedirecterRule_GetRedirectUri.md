# Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::GetRedirectUri

- ea: `0x34c0`
- end: `0x3526`
- name: `Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::GetRedirectUri`
- size: `102`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x34c0`

## string_xrefs

- `0x3506`: `ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x34c0  newobj   instance void [System]System.UriBuilder::.ctor()
0x34c5  dup
0x34c6  ldarg.1
0x34c7  callvirt instance string [System]System.Uri::get_DnsSafeHost()
0x34cc  callvirt instance void [System]System.UriBuilder::set_Host(string)
0x34d1  dup
0x34d2  ldarg.1
0x34d3  callvirt instance string [System]System.Uri::get_Scheme()
0x34d8  callvirt instance void [System]System.UriBuilder::set_Scheme(string)
0x34dd  dup
0x34de  ldarg.0
0x34df  ldfld    string Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_newBasePath
0x34e4  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x34e9  dup
0x34ea  ldarg.1
0x34eb  callvirt instance int32 [System]System.Uri::get_Port()
0x34f0  callvirt instance void [System]System.UriBuilder::set_Port(int32)
0x34f5  stloc.0
0x34f6  ldarg.0
0x34f7  ldfld    bool Microsoft.ReportingServices.Portal.WebHost.Owin.ItemPathUrlRedirecterRule::_appendItemPath
0x34fc  brfalse.s loc_351A
0x34fe  ldloc.0
0x34ff  dup
0x3500  callvirt instance string [System]System.UriBuilder::get_Path()
0x3505  ldarg.2
0x3506  ldstr    aItempath// "ItemPath"
0x350b  callvirt instance string [Microsoft.Owin]Microsoft.Owin.IReadableStringCollection::Get(string)
0x3510  call     string [mscorlib]System.String::Concat(string, string)
0x3515  callvirt instance void [System]System.UriBuilder::set_Path(string)
0x351a  ldloc.0
0x351b  callvirt instance class [System]System.Uri [System]System.UriBuilder::get_Uri()
0x3520  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x3525  ret
```
