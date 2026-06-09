# Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSetting

- ea: `0x420`
- end: `0x45a`
- name: `Microsoft.ReportingServices.Delivery.ReportContentDelivery.ReportContentDeliveryProvider::GetSetting`
- size: `58`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3f0`
- `0x410`

## callees

- `0x420`

## pseudocode

```c

```

## disassembly

```asm
0x420  ldarg.1
0x421  brfalse.s loc_426
0x423  ldarg.2
0x424  brtrue.s loc_428
0x426  ldnull
0x427  ret
0x428  ldarg.2
0x429  stloc.0
0x42a  ldc.i4.0
0x42b  stloc.1
0x42c  br.s     loc_452
0x42e  ldloc.0
0x42f  ldloc.1
0x430  ldelem.ref
0x431  stloc.2
0x432  ldloc.2
0x433  brfalse.s loc_44E
0x435  ldloc.2
0x436  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x43b  brfalse.s loc_44E
0x43d  ldarg.1
0x43e  ldloc.2
0x43f  callvirt instance string [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.Setting::get_Name()
0x444  ldc.i4.5
0x445  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x44a  brtrue.s loc_44E
0x44c  ldloc.2
0x44d  ret
0x44e  ldloc.1
0x44f  ldc.i4.1
0x450  add
0x451  stloc.1
0x452  ldloc.1
0x453  ldloc.0
0x454  ldlen
0x455  conv.i4
0x456  blt.s    loc_42E
0x458  ldnull
0x459  ret
```
