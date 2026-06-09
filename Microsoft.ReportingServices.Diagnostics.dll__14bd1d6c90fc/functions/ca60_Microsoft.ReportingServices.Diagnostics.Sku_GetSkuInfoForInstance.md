# Microsoft.ReportingServices.Diagnostics.Sku::GetSkuInfoForInstance

- ea: `0xca60`
- end: `0xcacb`
- name: `Microsoft.ReportingServices.Diagnostics.Sku::GetSkuInfoForInstance`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xcad0`

## callees

- `0xa960`
- `0xca60`
- `0xce90`
- `0x10d70`

## pseudocode

```c

```

## disassembly

```asm
0xca60  newobj   instance void <>c__DisplayClass14_0::.ctor()
0xca65  stloc.0
0xca66  ldloc.0
0xca67  ldarg.0
0xca68  stfld    string <>c__DisplayClass14_0::instanceId
0xca6d  ldloc.0
0xca6e  ldfld    string <>c__DisplayClass14_0::instanceId
0xca73  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xca78  brtrue.s loc_CA91
0xca7a  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xca7f  brfalse.s loc_CA9A
0xca81  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xca86  ldc.i4.1
0xca87  beq.s    loc_CA9A
0xca89  call     valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.Globals::get_CurrentApplication()
0xca8e  ldc.i4.3
0xca8f  beq.s    loc_CA9A
0xca91  ldc.i4.s 0x15
0xca93  ldc.i4.0
0xca94  newobj   instance void Microsoft.ReportingServices.Diagnostics.SkuInfo::.ctor(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, bool isExpired)
0xca99  ret
0xca9a  ldloc.0
0xca9b  ldc.i4.0
0xca9c  stfld    bool <>c__DisplayClass14_0::isExpired
0xcaa1  ldloc.0
0xcaa2  ldc.i4.0
0xcaa3  stfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType <>c__DisplayClass14_0::skuType
0xcaa8  ldloc.0
0xcaa9  ldftn    instance void <>c__DisplayClass14_0::<GetSkuInfoForInstance>b__0()
0xcaaf  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0xcab4  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0xcab9  ldloc.0
0xcaba  ldfld    valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType <>c__DisplayClass14_0::skuType
0xcabf  ldloc.0
0xcac0  ldfld    bool <>c__DisplayClass14_0::isExpired
0xcac5  newobj   instance void Microsoft.ReportingServices.Diagnostics.SkuInfo::.ctor(valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Editions.SkuType sku, bool isExpired)
0xcaca  ret
```
