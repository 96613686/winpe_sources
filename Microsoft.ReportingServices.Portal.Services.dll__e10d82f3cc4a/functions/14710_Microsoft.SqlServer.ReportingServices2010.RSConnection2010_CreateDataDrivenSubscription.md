# Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateDataDrivenSubscription

- ea: `0x14710`
- end: `0x1476f`
- name: `Microsoft.SqlServer.ReportingServices2010.RSConnection2010::CreateDataDrivenSubscription`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x21160`

## callees

- `0x22de0`

## string_xrefs

- `0x14753`: `CreateDataDrivenSubscription`

## pseudocode

```c

```

## disassembly

```asm
0x14710  newobj   instance void <>c__DisplayClass60_0::.ctor()
0x14715  stloc.0
0x14716  ldloc.0
0x14717  ldarg.0
0x14718  stfld    class Microsoft.SqlServer.ReportingServices2010.RSConnection2010 <>c__DisplayClass60_0::<>4__this
0x1471d  ldloc.0
0x1471e  ldarg.1
0x1471f  stfld    string <>c__DisplayClass60_0::itemPath
0x14724  ldloc.0
0x14725  ldarg.2
0x14726  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ExtensionSettings <>c__DisplayClass60_0::extensionSettings
0x1472b  ldloc.0
0x1472c  ldarg.3
0x1472d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.DataRetrievalPlan <>c__DisplayClass60_0::dataRetrievalPlan
0x14732  ldloc.0
0x14733  ldarg.s  4
0x14735  stfld    string <>c__DisplayClass60_0::description
0x1473a  ldloc.0
0x1473b  ldarg.s  5
0x1473d  stfld    string <>c__DisplayClass60_0::eventType
0x14742  ldloc.0
0x14743  ldarg.s  6
0x14745  stfld    string <>c__DisplayClass60_0::matchData
0x1474a  ldloc.0
0x1474b  ldarg.s  7
0x1474d  stfld    class [Microsoft.ReportingServices.Soap]Microsoft.SqlServer.ReportingServices2010.ParameterValueOrFieldReference[] <>c__DisplayClass60_0::parameters
0x14752  ldarg.0
0x14753  ldstr    aCreatedatadriv// "CreateDataDrivenSubscription"
0x14758  ldloc.0
0x14759  ldftn    instance string <>c__DisplayClass60_0::<CreateDataDrivenSubscription>b__0()
0x1475f  newobj   instance void class SoapMethod<string>::.ctor(object, native int)
0x14764  newobj   instance void class SoapMethodWrapper`1<string>::.ctor(class Microsoft.SqlServer.ReportingServices2010.RSConnection2010, string, class SoapMethod<var<u1>>)
0x14769  callvirt instance var<u1> class SoapMethodWrapper`1<string>::ExecuteMethod()
0x1476e  ret
```
