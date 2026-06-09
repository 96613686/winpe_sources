# Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::OnTextBoxBegin

- ea: `0x5e60`
- end: `0x5fb4`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::OnTextBoxBegin`
- size: `340`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x280`
- `0x5e50`
- `0x5e60`
- `0x62b0`

## pseudocode

```c

```

## disassembly

```asm
0x5e60  ldarg.0
0x5e61  ldflda   valuetype [mscorlib]System.Nullable`1<int32> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::maxRows
0x5e66  call     instance bool valuetype [mscorlib]System.Nullable`1<int32>::get_HasValue()
0x5e6b  brfalse.s loc_5E81
0x5e6d  ldarg.0
0x5e6e  ldfld    int32 Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowCounter
0x5e73  ldarg.0
0x5e74  ldflda   valuetype [mscorlib]System.Nullable`1<int32> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::maxRows
0x5e79  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<int32>::get_Value()
0x5e7e  blt.s    loc_5E81
0x5e80  ret
0x5e81  ldarg.0
0x5e82  ldfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::firstValueInRow
0x5e87  brfalse.s loc_5EA2
0x5e89  ldarg.0
0x5e8a  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor Microsoft.ReportingServices.Rendering.DataRenderer.JsonDataHandler::visitor
0x5e8f  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.JsonVisitor::StartArray()
0x5e94  ldarg.0
0x5e95  ldc.i4.0
0x5e96  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::firstValueInRow
0x5e9b  ldarg.0
0x5e9c  ldc.i4.1
0x5e9d  stfld    bool Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowHasValues
0x5ea2  ldarg.1
0x5ea3  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_DataElementName()
0x5ea8  brtrue.s loc_5EB5
0x5eaa  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonSharedDataSetTableReportFormatInvalid()
0x5eaf  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x5eb4  throw
0x5eb5  ldarg.1
0x5eb6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x5ebb  brfalse  loc_5FB0
0x5ec0  ldarg.1
0x5ec1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CustomPropertyCollection [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_CustomProperties()
0x5ec6  ldstr    aOriginalfieldn// "OriginalFieldName"
0x5ecb  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CustomProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CustomPropertyCollection::get_Item(string)
0x5ed0  stloc.0
0x5ed1  ldloc.0
0x5ed2  brtrue.s loc_5ED5
0x5ed4  ret
0x5ed5  ldloc.0
0x5ed6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.CustomProperty::get_Value()
0x5edb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty::get_Value()
0x5ee0  isinst   [mscorlib]System.String
0x5ee5  stloc.1
0x5ee6  ldarg.0
0x5ee7  ldarg.1
0x5ee8  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Name()
0x5eed  ldloc.1
0x5eee  call     instance string Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::GenerateKey(string controlName, string fieldName)
0x5ef3  stloc.2
0x5ef4  ldarg.0
0x5ef5  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::columnDefinitions
0x5efa  ldloc.2
0x5efb  ldloca.s 3
0x5efd  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>::TryGetValue(var<u1>, !!T0)
0x5f02  brtrue.s loc_5F2C
0x5f04  ldloca.s 5
0x5f06  initobj  Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition
0x5f0c  ldloca.s 5
0x5f0e  ldloc.1
0x5f0f  stfld    string Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::Name
0x5f14  ldloca.s 5
0x5f16  ldc.i4.0
0x5f17  stfld    valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::DataType
0x5f1c  ldloc.s  5
0x5f1e  stloc.3
0x5f1f  ldarg.0
0x5f20  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::columnDefinitions
0x5f25  ldloc.2
0x5f26  ldloc.3
0x5f27  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>::Add(var<u1>, !!T0)
0x5f2c  ldarg.1
0x5f2d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItemInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportItem::get_Instance()
0x5f32  castclass [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance
0x5f37  stloc.s  4
0x5f39  ldloc.s  4
0x5f3b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x5f40  brfalse.s loc_5F9D
0x5f42  ldloc.3
0x5f43  ldfld    valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::DataType
0x5f48  brtrue.s loc_5F95
0x5f4a  ldtoken  [mscorlib]System.TypeCode
0x5f4f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x5f54  ldloc.s  4
0x5f56  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x5f5b  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x5f60  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x5f65  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x5f6a  unbox.any [mscorlib]System.TypeCode
0x5f6f  stloc.s  6
0x5f71  ldloca.s 3
0x5f73  ldloc.s  6
0x5f75  stfld    valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::DataType
0x5f7a  ldarg.0
0x5f7b  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::columnDefinitions
0x5f80  ldloc.2
0x5f81  ldloc.3
0x5f82  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition>::set_Item(var<u1>, !!T0)
0x5f87  leave.s  loc_5F9D
0x5f89  pop
0x5f8a  call     string Microsoft.ReportingServices.DataRendering.StringResources::get_rrJsonSharedDataSetTableReportFormatInvalid()
0x5f8f  newobj   instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportRenderingException::.ctor(string)
0x5f94  throw
0x5f95  ldloc.3
0x5f96  ldfld    valuetype [mscorlib]System.TypeCode Microsoft.ReportingServices.Rendering.DataRenderer.ColumnDefinition::DataType
0x5f9b  stloc.s  6
0x5f9d  ldarg.0
0x5f9e  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.JsonSharedDataSetTableHandler::rowValuesCache
0x5fa3  ldloc.2
0x5fa4  ldloc.s  4
0x5fa6  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.TextBoxInstance::get_OriginalValue()
0x5fab  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, object>::Add(var<u1>, !!T0)
0x5fb0  ldarg.3
0x5fb1  ldc.i4.0
0x5fb2  stind.i1
0x5fb3  ret
```
