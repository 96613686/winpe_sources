# Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::ToSettingArray

- ea: `0x950`
- end: `0x9ca`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::ToSettingArray`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x2430`

## callees

- `0x850`
- `0x870`
- `0x890`
- `0x8b0`
- `0x9d0`

## string_xrefs

- `0x99f`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0x950  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x955  dup
0x956  ldarg.0
0x957  ldstr    aPath// "PATH"
0x95c  ldarg.0
0x95d  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x962  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x967  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x96c  pop
0x96d  dup
0x96e  ldarg.0
0x96f  ldstr    aFilename// "FILENAME"
0x974  ldarg.0
0x975  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x97a  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x97f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x984  pop
0x985  dup
0x986  ldarg.0
0x987  ldstr    aRenderFormat// "RENDER_FORMAT"
0x98c  ldarg.0
0x98d  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_RenderFormat()
0x992  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x997  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x99c  pop
0x99d  dup
0x99e  ldarg.0
0x99f  ldstr    aWritemode// "WRITEMODE"
0x9a4  ldarg.0
0x9a5  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x9aa  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x9af  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x9b4  pop
0x9b5  ldtoken  [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting
0x9ba  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9bf  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x9c4  isinst   class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[]
0x9c9  ret
```
