# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::IsValueInValidRange

- ea: `0x3a0`
- end: `0x3ef`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::IsValueInValidRange`
- size: `79`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x3a0`
- `0x410`

## pseudocode

```c

```

## disassembly

```asm
0x3a0  ldarg.0
0x3a1  ldarg.1
0x3a2  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::ExtensionSetting(string name)
0x3a7  stloc.0
0x3a8  ldloc.0
0x3a9  brfalse.s loc_3B3
0x3ab  ldloc.0
0x3ac  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues()
0x3b1  brtrue.s loc_3B5
0x3b3  ldc.i4.1
0x3b4  ret
0x3b5  ldloc.0
0x3b6  callvirt instance class [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue[] [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_ValidValues()
0x3bb  stloc.1
0x3bc  ldc.i4.0
0x3bd  stloc.2
0x3be  br.s     loc_3E7
0x3c0  ldloc.1
0x3c1  ldloc.2
0x3c2  ldelem.ref
0x3c3  stloc.3
0x3c4  ldloc.3
0x3c5  brtrue.s loc_3CC
0x3c7  ldarg.2
0x3c8  brtrue.s loc_3CC
0x3ca  ldc.i4.1
0x3cb  ret
0x3cc  ldloc.3
0x3cd  brfalse.s loc_3E3
0x3cf  ldarg.2
0x3d0  brfalse.s loc_3E3
0x3d2  ldloc.3
0x3d3  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.ValidValue::get_Value()
0x3d8  ldarg.2
0x3d9  ldc.i4.5
0x3da  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x3df  brtrue.s loc_3E3
0x3e1  ldc.i4.1
0x3e2  ret
0x3e3  ldloc.2
0x3e4  ldc.i4.1
0x3e5  add
0x3e6  stloc.2
0x3e7  ldloc.2
0x3e8  ldloc.1
0x3e9  ldlen
0x3ea  conv.i4
0x3eb  blt.s    loc_3C0
0x3ed  ldc.i4.0
0x3ee  ret
```
