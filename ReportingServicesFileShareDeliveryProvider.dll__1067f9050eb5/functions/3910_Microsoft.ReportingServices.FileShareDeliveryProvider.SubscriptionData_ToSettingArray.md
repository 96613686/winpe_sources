# Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::ToSettingArray

- ea: `0x3910`
- end: `0x39fa`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::ToSettingArray`
- size: `234`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x850`
- `0x870`
- `0x890`
- `0x8b0`
- `0x9d0`
- `0x3740`
- `0x3760`
- `0x3800`
- `0x3830`

## string_xrefs

- `0x39af`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0x3910  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x3915  dup
0x3916  ldarg.0
0x3917  ldstr    aPath// "PATH"
0x391c  ldarg.0
0x391d  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x3922  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x3927  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x392c  pop
0x392d  dup
0x392e  ldarg.0
0x392f  ldstr    aFilename// "FILENAME"
0x3934  ldarg.0
0x3935  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x393a  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x393f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3944  pop
0x3945  dup
0x3946  ldarg.0
0x3947  ldstr    aFileextn// "FILEEXTN"
0x394c  ldarg.0
0x394d  call     instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FileExtn()
0x3952  stloc.0
0x3953  ldloca.s 0
0x3955  call     instance string [mscorlib]System.Boolean::ToString()
0x395a  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x395f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3964  pop
0x3965  dup
0x3966  ldarg.0
0x3967  ldstr    aUsername// "USERNAME"
0x396c  ldarg.0
0x396d  call     instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_FullyQualifiedUserName()
0x3972  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x3977  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x397c  pop
0x397d  dup
0x397e  ldarg.0
0x397f  ldstr    aPassword// "PASSWORD"
0x3984  ldarg.0
0x3985  call     instance string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_PassWord()
0x398a  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x398f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x3994  pop
0x3995  dup
0x3996  ldarg.0
0x3997  ldstr    aRenderFormat// "RENDER_FORMAT"
0x399c  ldarg.0
0x399d  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_RenderFormat()
0x39a2  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x39a7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x39ac  pop
0x39ad  dup
0x39ae  ldarg.0
0x39af  ldstr    aWritemode// "WRITEMODE"
0x39b4  ldarg.0
0x39b5  call     instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_WriteMode()
0x39ba  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x39bf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x39c4  pop
0x39c5  dup
0x39c6  ldarg.0
0x39c7  ldstr    aDefaultcredent// "DEFAULTCREDENTIALS"
0x39cc  ldarg.0
0x39cd  call     instance bool Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::get_UsingDefaultCreds()
0x39d2  stloc.0
0x39d3  ldloca.s 0
0x39d5  call     instance string [mscorlib]System.Boolean::ToString()
0x39da  call     instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::CreateSetting(string name, string val)
0x39df  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x39e4  pop
0x39e5  ldtoken  [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting
0x39ea  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39ef  callvirt instance class [mscorlib]System.Array [mscorlib]System.Collections.ArrayList::ToArray(class [mscorlib]System.Type)
0x39f4  isinst   class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[]
0x39f9  ret
```
