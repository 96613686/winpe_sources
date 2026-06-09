# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::Deliver

- ea: `0x2a0`
- end: `0x39c`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::Deliver`
- size: `252`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callees

- `0x100`
- `0x2a0`
- `0x760`
- `0x770`
- `0x780`
- `0x850`
- `0x870`

## string_xrefs

- `0x329`: `Error writing file {0} to path {1}`

## pseudocode

```c

```

## disassembly

```asm
0x2a0  ldnull
0x2a1  stloc.1
0x2a2  ldarg.0
0x2a3  ldarg.1
0x2a4  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::get_UserData()
0x2a9  ldloca.s 0
0x2ab  callvirt instance bool Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::IsValidSettingsData(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings, [out] class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[]& outputSettings)
0x2b0  brtrue.s loc_301
0x2b2  ldloc.0
0x2b3  stloc.2
0x2b4  ldc.i4.0
0x2b5  stloc.3
0x2b6  br.s     loc_2F9
0x2b8  ldloc.2
0x2b9  ldloc.3
0x2ba  ldelem.ref
0x2bb  stloc.s  4
0x2bd  ldloc.s  4
0x2bf  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x2c4  brfalse.s loc_2F5
0x2c6  ldloc.s  4
0x2c8  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x2cd  ldsfld   string [mscorlib]System.String::Empty
0x2d2  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2d7  brfalse.s loc_2F5
0x2d9  ldarg.1
0x2da  ldloc.s  4
0x2dc  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Error()
0x2e1  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x2e6  ldarg.1
0x2e7  ldc.i4.0
0x2e8  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Retry(bool)
0x2ed  ldc.i4.0
0x2ee  stloc.s  5
0x2f0  leave    loc_399
0x2f5  ldloc.3
0x2f6  ldc.i4.1
0x2f7  add
0x2f8  stloc.3
0x2f9  ldloc.3
0x2fa  ldloc.2
0x2fb  ldlen
0x2fc  conv.i4
0x2fd  blt.s    loc_2B8
0x2ff  br.s     loc_351
0x301  ldarg.0
0x302  ldloc.0
0x303  callvirt instance class Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSubscriptionData(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting[] settings)
0x308  stloc.1
0x309  ldarg.0
0x30a  ldarg.1
0x30b  ldloc.1
0x30c  callvirt instance bool Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::SaveReport(class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification notification, class Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData data)
0x311  stloc.s  6
0x313  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x318  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x31d  brfalse.s loc_34B
0x31f  ldloc.s  6
0x321  brtrue.s loc_34B
0x323  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x328  ldc.i4.3
0x329  ldstr    aErrorWritingFi// "Error writing file {0} to path {1}"
0x32e  ldc.i4.2
0x32f  newarr   [mscorlib]System.Object
0x334  dup
0x335  ldc.i4.0
0x336  ldloc.1
0x337  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x33c  stelem.ref
0x33d  dup
0x33e  ldc.i4.1
0x33f  ldloc.1
0x340  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_Path()
0x345  stelem.ref
0x346  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x34b  ldloc.s  6
0x34d  stloc.s  5
0x34f  leave.s  loc_399
0x351  leave.s  loc_397
0x353  stloc.s  7
0x355  ldarg.1
0x356  ldloc.1
0x357  callvirt instance string Microsoft.ReportingServices.Delivery.ReportContentDelivery.SubscriptionData::get_FileName()
0x35c  ldloc.s  7
0x35e  callvirt instance string [mscorlib]System.Exception::get_Message()
0x363  call     string Microsoft.ReportingServices.Delivery.ReportContentDeliveryProviderRes::CouldNotWriteFile(string filename, string message)
0x368  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::set_Status(string)
0x36d  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x372  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x377  brfalse.s loc_38B
0x379  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::m_tracer
0x37e  ldc.i4.3
0x37f  ldloc.s  7
0x381  callvirt instance string [mscorlib]System.Object::ToString()
0x386  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x38b  ldc.i4.0
0x38c  stloc.s  5
0x38e  leave.s  loc_399
0x390  ldarg.1
0x391  callvirt instance void [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Notification::Save()
0x396  endfinally
0x397  ldc.i4.0
0x398  ret
0x399  ldloc.s  5
0x39b  ret
```
