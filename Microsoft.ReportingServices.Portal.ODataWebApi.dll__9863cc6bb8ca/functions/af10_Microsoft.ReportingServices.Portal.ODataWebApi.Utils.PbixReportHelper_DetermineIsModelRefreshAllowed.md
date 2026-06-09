# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DetermineIsModelRefreshAllowed

- ea: `0xaf10`
- end: `0xaf77`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DetermineIsModelRefreshAllowed`
- size: `103`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0xaf10`

## pseudocode

```c

```

## disassembly

```asm
0xaf10  ldarg.1
0xaf11  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property> [Microsoft.ReportingServices.Portal.Interfaces]Model.CatalogItem::get_Properties()
0xaf16  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__27_0
0xaf1b  dup
0xaf1c  brtrue.s loc_AF35
0xaf1e  pop
0xaf1f  ldsfld   class <>c <>c::<>9
0xaf24  ldftn    instance bool <>c::<DetermineIsModelRefreshAllowed>b__27_0(class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property x)
0xaf2a  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool>::.ctor(object, native int)
0xaf2f  dup
0xaf30  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.Property, bool> <>c::<>9__27_0
0xaf35  call     T0x2B0000EC
0xaf3a  call     T0x2B0000ED
0xaf3f  ldarg.1
0xaf40  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataSources()
0xaf45  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> <>c::<>9__27_1
0xaf4a  dup
0xaf4b  brtrue.s loc_AF64
0xaf4d  pop
0xaf4e  ldsfld   class <>c <>c::<>9
0xaf53  ldftn    instance bool <>c::<DetermineIsModelRefreshAllowed>b__27_1(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource x)
0xaf59  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool>::.ctor(object, native int)
0xaf5e  dup
0xaf5f  stsfld   class [mscorlib]System.Func`2<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource, bool> <>c::<>9__27_1
0xaf64  call     T0x2B0000EE
0xaf69  stloc.0
0xaf6a  ldloca.s 0
0xaf6c  call     instance string [mscorlib]System.Boolean::ToString()
0xaf71  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.Property::set_Value(string)
0xaf76  ret
```
