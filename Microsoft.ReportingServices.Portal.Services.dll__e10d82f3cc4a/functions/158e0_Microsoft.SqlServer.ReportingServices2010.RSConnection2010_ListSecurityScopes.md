# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListSecurityScopes

- ea: `0x158e0`
- end: `0x158fd`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::ListSecurityScopes`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x158e1`: `ListSecurityScopes`

## pseudocode

```c

```

## disassembly

```asm
0x158e0  ldarg.0
0x158e1  ldstr    aListsecuritysc// "ListSecurityScopes"
0x158e6  ldarg.0
0x158e7  ldftn    instance string[] Microsoft.SqlServer.ReportingServices2010.RSConnection2010::<ListSecurityScopes>b__125_0()
0x158ed  newobj   instance void class SoapMethod<string[]>::.ctor(object, native int)
0x158f2  newobj   instance void class SoapMethodWrapper`1<string[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x158f7  callvirt instance var<u1> class SoapMethodWrapper`1<string[]>::ExecuteMethod()
0x158fc  ret
```
