# Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings

- ea: `0x8c0`
- end: `0x94b`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::FromSettings`
- size: `139`
- prototype: ``
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x760`
- `0xe00`
- `0x2500`
- `0x3870`

## callees

- `0x840`
- `0x860`
- `0x880`
- `0x8a0`
- `0x8c0`

## string_xrefs

- `0x8f9`: `WRITEMODE`

## pseudocode

```c

```

## disassembly

```asm
0x8c0  ldarg.1
0x8c1  stloc.0
0x8c2  ldc.i4.0
0x8c3  stloc.1
0x8c4  br.s     loc_941
0x8c6  ldloc.0
0x8c7  ldloc.1
0x8c8  ldelem.ref
0x8c9  stloc.2
0x8ca  ldloc.2
0x8cb  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x8d0  stloc.3
0x8d1  ldloc.3
0x8d2  ldstr    aPath// "PATH"
0x8d7  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8dc  brtrue.s loc_907
0x8de  ldloc.3
0x8df  ldstr    aFilename// "FILENAME"
0x8e4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8e9  brtrue.s loc_915
0x8eb  ldloc.3
0x8ec  ldstr    aRenderFormat// "RENDER_FORMAT"
0x8f1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8f6  brtrue.s loc_923
0x8f8  ldloc.3
0x8f9  ldstr    aWritemode// "WRITEMODE"
0x8fe  call     bool [mscorlib]System.String::op_Equality(string, string)
0x903  brtrue.s loc_931
0x905  br.s     loc_93D
0x907  ldarg.0
0x908  ldloc.2
0x909  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x90e  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_Path(string value)
0x913  br.s     loc_93D
0x915  ldarg.0
0x916  ldloc.2
0x917  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x91c  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_FileName(string value)
0x921  br.s     loc_93D
0x923  ldarg.0
0x924  ldloc.2
0x925  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x92a  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_RenderFormat(string value)
0x92f  br.s     loc_93D
0x931  ldarg.0
0x932  ldloc.2
0x933  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Value()
0x938  call     instance void Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::set_WriteMode(string value)
0x93d  ldloc.1
0x93e  ldc.i4.1
0x93f  add
0x940  stloc.1
0x941  ldloc.1
0x942  ldloc.0
0x943  ldlen
0x944  conv.i4
0x945  blt      loc_8C6
0x94a  ret
```
