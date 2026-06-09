# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetModelItemPolicies

- ea: `0x15470`
- end: `0x154b7`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::GetModelItemPolicies`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x23a10`

## string_xrefs

- `0x15493`: `GetModelItemPolicies`

## pseudocode

```c

```

## disassembly

```asm
0x15470  newobj   instance void <>c__DisplayClass108_0::.ctor()
0x15475  stloc.0
0x15476  ldloc.0
0x15477  ldarg.0
0x15478  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass108_0::<>4__this
0x1547d  ldloc.0
0x1547e  ldarg.1
0x1547f  stfld    string <>c__DisplayClass108_0::model
0x15484  ldloc.0
0x15485  ldarg.2
0x15486  stfld    string <>c__DisplayClass108_0::modelItemId
0x1548b  ldloc.0
0x1548c  ldc.i4.0
0x1548d  stfld    bool <>c__DisplayClass108_0::outInheritParent
0x15492  ldarg.0
0x15493  ldstr    aGetmodelitempo// "GetModelItemPolicies"
0x15498  ldloc.0
0x15499  ldftn    instance class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[] <>c__DisplayClass108_0::<GetModelItemPolicies>b__0()
0x1549f  newobj   instance void class SoapMethod<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::.ctor(object, native int)
0x154a4  newobj   instance void class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x154a9  callvirt instance var<u1> class SoapMethodWrapper`1<class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.Policy[]>::ExecuteMethod()
0x154ae  ldarg.3
0x154af  ldloc.0
0x154b0  ldfld    bool <>c__DisplayClass108_0::outInheritParent
0x154b5  stind.i1
0x154b6  ret
```
