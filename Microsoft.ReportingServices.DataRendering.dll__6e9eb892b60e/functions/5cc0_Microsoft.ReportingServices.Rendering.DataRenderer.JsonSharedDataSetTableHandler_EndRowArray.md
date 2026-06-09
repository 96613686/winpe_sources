# Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::EndRowArray

- ea: `0x5cc0`
- end: `0x5d3c`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::EndRowArray`
- size: `124`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5c70`
- `0x5c80`

## callees

- `0x5cc0`
- `0x60f0`
- `0x62c0`

## pseudocode

```c

```

## disassembly

```asm
0x5cc0  ldarg.0
0x5cc1  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowHasValues
0x5cc6  brfalse.s loc_5D3B
0x5cc8  ldarg.0
0x5cc9  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowValuesCache
0x5cce  callvirt instance class [mscorlib]System.Collections.Generic.ICollection`1<var<u1>> class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::get_Values()
0x5cd3  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<object>::GetEnumerator()
0x5cd8  stloc.0
0x5cd9  br.s     loc_5D03
0x5cdb  ldloc.0
0x5cdc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<object>::get_Current()
0x5ce1  stloc.1
0x5ce2  ldloc.1
0x5ce3  brtrue.s loc_5CF7
0x5ce5  ldarg.0
0x5ce6  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5ceb  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x5cf0  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue(object value)
0x5cf5  br.s     loc_5D03
0x5cf7  ldarg.0
0x5cf8  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5cfd  ldloc.1
0x5cfe  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue(object value)
0x5d03  ldloc.0
0x5d04  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5d09  brtrue.s loc_5CDB
0x5d0b  leave.s  loc_5D17
0x5d0d  ldloc.0
0x5d0e  brfalse.s loc_5D16
0x5d10  ldloc.0
0x5d11  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5d16  endfinally
0x5d17  ldarg.0
0x5d18  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5d1d  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::EndArray()
0x5d22  ldarg.0
0x5d23  ldarg.0
0x5d24  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowCounter
0x5d29  ldc.i4.1
0x5d2a  add
0x5d2b  stfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowCounter
0x5d30  ldarg.0
0x5d31  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowValuesCache
0x5d36  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, object>>::Clear()
0x5d3b  ret
```
