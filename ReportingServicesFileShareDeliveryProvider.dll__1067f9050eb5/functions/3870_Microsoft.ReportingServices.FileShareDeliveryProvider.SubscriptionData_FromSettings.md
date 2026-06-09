# Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::FromSettings

- ea: `0x3870`
- end: `0x390f`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::FromSettings`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x8c0`
- `0x3730`
- `0x3750`
- `0x3770`
- `0x37f0`
- `0x3870`

## pseudocode

```c

```

## disassembly

```asm
0x3870  ldarg.0
0x3871  ldarg.1
0x3872  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x3877  ldarg.1
0x3878  stloc.0
0x3879  ldc.i4.0
0x387a  stloc.1
0x387b  br       loc_3905
0x3880  ldloc.0
0x3881  ldloc.1
0x3882  ldelem.ref
0x3883  stloc.2
0x3884  ldloc.2
0x3885  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x388a  stloc.3
0x388b  ldloc.3
0x388c  ldstr    aFileextn// "FILEEXTN"
0x3891  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3896  brtrue.s loc_38C1
0x3898  ldloc.3
0x3899  ldstr    aUsername// "USERNAME"
0x389e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38a3  brtrue.s loc_38D4
0x38a5  ldloc.3
0x38a6  ldstr    aPassword// "PASSWORD"
0x38ab  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38b0  brtrue.s loc_38E2
0x38b2  ldloc.3
0x38b3  ldstr    aDefaultcredent// "DEFAULTCREDENTIALS"
0x38b8  call     bool [mscorlib]System.String::op_Equality(string, string)
0x38bd  brtrue.s loc_38F0
0x38bf  br.s     loc_3901
0x38c1  ldarg.0
0x38c2  ldloc.2
0x38c3  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x38c8  call     bool [mscorlib]System.Boolean::Parse(string)
0x38cd  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_FileExtn(bool value)
0x38d2  br.s     loc_3901
0x38d4  ldarg.0
0x38d5  ldloc.2
0x38d6  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x38db  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UserName(string value)
0x38e0  br.s     loc_3901
0x38e2  ldarg.0
0x38e3  ldloc.2
0x38e4  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x38e9  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_PassWord(string value)
0x38ee  br.s     loc_3901
0x38f0  ldarg.0
0x38f1  ldloc.2
0x38f2  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x38f7  call     bool [mscorlib]System.Boolean::Parse(string)
0x38fc  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UsingDefaultCreds(bool value)
0x3901  ldloc.1
0x3902  ldc.i4.1
0x3903  add
0x3904  stloc.1
0x3905  ldloc.1
0x3906  ldloc.0
0x3907  ldlen
0x3908  conv.i4
0x3909  blt      loc_3880
0x390e  ret
```
