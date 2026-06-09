# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemPolicies

- ea: `0x143b0`
- end: `0x143cd`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetSystemPolicies`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## string_xrefs

- `0x143b1`: `GetSystemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x143b0  ldarg.0
0x143b1  ldstr    aGetsystempolic// "GetSystemPolicies"
0x143b6  ldarg.0
0x143b7  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[] Microsoft.SqlServer.ReportingServices2010.RSConnection2010::<GetSystemPolicies>b__46_0()
0x143bd  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::.ctor(object, native int)
0x143c2  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x143c7  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::ExecuteMethod()
0x143cc  ret
```
