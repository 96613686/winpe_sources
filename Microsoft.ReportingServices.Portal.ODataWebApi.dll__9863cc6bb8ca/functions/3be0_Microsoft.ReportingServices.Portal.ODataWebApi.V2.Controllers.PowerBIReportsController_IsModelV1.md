# Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::IsModelV1

- ea: `0x3be0`
- end: `0x3c29`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V2.Controllers.PowerBIReportsController::IsModelV1`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3b70`
- `0xdf90`

## callees

- `0x3be0`

## pseudocode

```c

```

## disassembly

```asm
0x3be0  ldarg.1
0x3be1  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0x3be6  dup
0x3be7  brtrue.s loc_3BED
0x3be9  pop
0x3bea  ldnull
0x3beb  br.s     loc_3C11
0x3bed  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__32_0
0x3bf2  dup
0x3bf3  brtrue.s loc_3C0C
0x3bf5  pop
0x3bf6  ldsfld   class <>c <>c::<>9
0x3bfb  ldftn    instance bool <>c::<IsModelV1>b__32_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property p)
0x3c01  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0x3c06  dup
0x3c07  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__32_0
0x3c0c  call     T0x2B000064
0x3c11  stloc.0
0x3c12  ldloc.0
0x3c13  brfalse.s loc_3C27
0x3c15  ldloc.0
0x3c16  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::get_Value()
0x3c1b  ldstr    aPowerbiV1// "PowerBI_V1"
0x3c20  ldc.i4.5
0x3c21  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3c26  ret
0x3c27  ldc.i4.1
0x3c28  ret
```
