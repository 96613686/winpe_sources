# Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UserName

- ea: `0x3770`
- end: `0x37d3`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_UserName`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x2430`
- `0x3870`

## callees

- `0x3770`
- `0x3810`

## pseudocode

```c

```

## disassembly

```asm
0x3770  ldarg.1
0x3771  brfalse.s loc_37C4
0x3773  ldarg.1
0x3774  ldstr    asc_55E6// "\\"
0x3779  ldc.i4.4
0x377a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x377f  stloc.0
0x3780  ldloc.0
0x3781  ldc.i4.0
0x3782  blt.s    loc_37B5
0x3784  ldarg.0
0x3785  ldarg.1
0x3786  ldc.i4.0
0x3787  ldloc.0
0x3788  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x378d  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_Domain(string value)
0x3792  ldarg.1
0x3793  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3798  ldloc.0
0x3799  ldc.i4.1
0x379a  add
0x379b  ble.s    loc_37AD
0x379d  ldarg.0
0x379e  ldarg.1
0x379f  ldloc.0
0x37a0  ldc.i4.1
0x37a1  add
0x37a2  callvirt instance string [mscorlib]System.String::Substring(int32)
0x37a7  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x37ac  ret
0x37ad  ldarg.0
0x37ae  ldnull
0x37af  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x37b4  ret
0x37b5  ldarg.0
0x37b6  ldarg.1
0x37b7  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x37bc  ldarg.0
0x37bd  ldnull
0x37be  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_Domain(string value)
0x37c3  ret
0x37c4  ldarg.0
0x37c5  ldnull
0x37c6  call     instance void Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::set_Domain(string value)
0x37cb  ldarg.0
0x37cc  ldnull
0x37cd  stfld    string Microsoft.ReportingServices.FileShareDeliveryProvider.SubscriptionData::m_UserName
0x37d2  ret
```
