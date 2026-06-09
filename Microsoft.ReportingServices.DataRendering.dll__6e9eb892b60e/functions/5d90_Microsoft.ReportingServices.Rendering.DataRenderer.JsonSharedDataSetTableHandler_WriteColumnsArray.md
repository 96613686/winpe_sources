# Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::WriteColumnsArray

- ea: `0x5d90`
- end: `0x5e49`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::WriteColumnsArray`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x5c80`

## callees

- `0x350`
- `0x5d90`
- `0x60c0`
- `0x60d0`
- `0x60e0`
- `0x60f0`
- `0x62b0`
- `0x62c0`

## pseudocode

```c

```

## disassembly

```asm
0x5d90  ldarg.0
0x5d91  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5d96  ldstr    aColumns// "Columns"
0x5d9b  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyName(string name)
0x5da0  ldarg.0
0x5da1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5da6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::StartArray()
0x5dab  ldarg.0
0x5dac  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::columnDefinitions
0x5db1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>>::GetEnumerator()
0x5db6  stloc.0
0x5db7  br.s     loc_5E29
0x5db9  ldloc.0
0x5dba  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>>::get_Current()
0x5dbf  stloc.1
0x5dc0  ldarg.0
0x5dc1  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5dc6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::StartObject()
0x5dcb  ldarg.0
0x5dcc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5dd1  ldstr    aName// "Name"
0x5dd6  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyName(string name)
0x5ddb  ldarg.0
0x5ddc  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5de1  ldloca.s 1
0x5de3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>::get_Value()
0x5de8  ldfld    string Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::Name
0x5ded  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue(object value)
0x5df2  ldarg.0
0x5df3  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5df8  ldstr    aType// "Type"
0x5dfd  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyName(string name)
0x5e02  ldarg.0
0x5e03  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5e08  ldloca.s 1
0x5e0a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>::get_Value()
0x5e0f  ldfld    valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::DataType
0x5e14  call     string Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetJsonSchemaDataType(valuetype [mscorlib]System.TypeCode typeCode)
0x5e19  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::WritePropertyValue(object value)
0x5e1e  ldarg.0
0x5e1f  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5e24  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::EndObject()
0x5e29  ldloc.0
0x5e2a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x5e2f  brtrue.s loc_5DB9
0x5e31  leave.s  loc_5E3D
0x5e33  ldloc.0
0x5e34  brfalse.s loc_5E3C
0x5e36  ldloc.0
0x5e37  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5e3c  endfinally
0x5e3d  ldarg.0
0x5e3e  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5e43  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::EndArray()
0x5e48  ret
```
