# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemPermissions

- ea: `0x14490`
- end: `0x144ad`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemPermissions`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x14491`: `GetSystemPermissions`

## pseudocode

```c

```

## disassembly

```asm
0x14490  ldarg.0
0x14491  ldstr    aGetsystempermi// "GetSystemPermissions"
0x14496  ldarg.0
0x14497  ldftn    instance string[] Microsoft.SqlServer.ReportingServices2010.RSConnection2010::<GetSystemPermissions>b__50_0()
0x1449d  newobj   instance void class SoapMethod<string[]>::.ctor(object, native int)
0x144a2  newobj   instance void class SoapMethodWrapper`1<string[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x144a7  callvirt instance var<u1> class SoapMethodWrapper`1<string[]>::ExecuteMethod()
0x144ac  ret
```
