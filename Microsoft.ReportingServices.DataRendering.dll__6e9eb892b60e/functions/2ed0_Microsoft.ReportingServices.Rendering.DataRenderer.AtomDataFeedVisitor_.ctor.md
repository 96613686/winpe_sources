# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::.ctor

- ea: `0x2ed0`
- end: `0x309e`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::.ctor`
- size: `462`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1d70`
- `0x37e0`
- `0x39c0`

## callees

- `0x2b30`
- `0x2ed0`
- `0x37a0`

## pseudocode

```c

```

## disassembly

```asm
0x2ed0  ldarg.0
0x2ed1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::.ctor()
0x2ed6  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnNames
0x2edb  ldarg.0
0x2edc  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata>::.ctor()
0x2ee1  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.ReportingServices.Rendering.DataRenderer.ColumnMetadata> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_columnMetadata
0x2ee6  ldarg.0
0x2ee7  ldarg.1
0x2ee8  ldarg.2
0x2ee9  call     instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomVisitor::.ctor(class [System.Xml]System.Xml.XmlWriter xmlWriter, class [System]System.Collections.Specialized.NameValueCollection reportServerParameters)
0x2eee  ldarg.0
0x2eef  ldarg.3
0x2ef0  stfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x2ef5  ldarg.0
0x2ef6  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x2efb  brfalse.s loc_2F4D
0x2efd  ldarg.0
0x2efe  ldarg.0
0x2eff  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x2f04  callvirt instance int32 class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::get_Count()
0x2f09  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x2f0e  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x2f13  ldarg.0
0x2f14  ldfld    class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameterCollection Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_reportParamters
0x2f19  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportElementCollectionBase`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::GetEnumerator()
0x2f1e  stloc.1
0x2f1f  br.s     loc_2F39
0x2f21  ldloc.1
0x2f22  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter>::get_Current()
0x2f27  stloc.2
0x2f28  ldarg.0
0x2f29  ldfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x2f2e  ldloc.2
0x2f2f  callvirt instance string [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportParameter::get_Name()
0x2f34  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x2f39  ldloc.1
0x2f3a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x2f3f  brtrue.s loc_2F21
0x2f41  leave.s  loc_2F59
0x2f43  ldloc.1
0x2f44  brfalse.s loc_2F4C
0x2f46  ldloc.1
0x2f47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2f4c  endfinally
0x2f4d  ldarg.0
0x2f4e  ldc.i4.0
0x2f4f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor(int32)
0x2f54  stfld    class [mscorlib]System.Collections.Generic.List`1<string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_parameterNames
0x2f59  ldarg.0
0x2f5a  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::.ctor()
0x2f5f  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2f64  ldarg.0
0x2f65  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2f6a  ldc.i4.3
0x2f6b  ldstr    aEdmBoolean// "Edm.Boolean"
0x2f70  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2f75  ldarg.0
0x2f76  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2f7b  ldc.i4.6
0x2f7c  ldstr    aEdmByte// "Edm.Byte"
0x2f81  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2f86  ldarg.0
0x2f87  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2f8c  ldc.i4.5
0x2f8d  ldstr    aEdmSbyte// "Edm.SByte"
0x2f92  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2f97  ldarg.0
0x2f98  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2f9d  ldc.i4.s 0x10
0x2f9f  ldstr    aEdmDatetime// "Edm.DateTime"
0x2fa4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2fa9  ldarg.0
0x2faa  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2faf  ldc.i4.s 0xF
0x2fb1  ldstr    aEdmDecimal// "Edm.Decimal"
0x2fb6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2fbb  ldarg.0
0x2fbc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2fc1  ldc.i4.s 0xD
0x2fc3  ldstr    aEdmSingle// "Edm.Single"
0x2fc8  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2fcd  ldarg.0
0x2fce  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2fd3  ldc.i4.s 0xE
0x2fd5  ldstr    aEdmDouble// "Edm.Double"
0x2fda  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2fdf  ldarg.0
0x2fe0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2fe5  ldc.i4.7
0x2fe6  ldstr    aEdmInt16// "Edm.Int16"
0x2feb  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x2ff0  ldarg.0
0x2ff1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x2ff6  ldc.i4.s 9
0x2ff8  ldstr    aEdmInt32// "Edm.Int32"
0x2ffd  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x3002  ldarg.0
0x3003  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x3008  ldc.i4.s 0xB
0x300a  ldstr    aEdmInt64// "Edm.Int64"
0x300f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x3014  ldarg.0
0x3015  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x301a  ldc.i4.8
0x301b  ldstr    aEdmInt16// "Edm.Int16"
0x3020  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x3025  ldarg.0
0x3026  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x302b  ldc.i4.s 0xA
0x302d  ldstr    aEdmInt32// "Edm.Int32"
0x3032  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x3037  ldarg.0
0x3038  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_typeCodeToEdmMapping
0x303d  ldc.i4.s 0xC
0x303f  ldstr    aEdmInt64// "Edm.Int64"
0x3044  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.TypeCode, string>::Add(var<u1>, !!T0)
0x3049  ldarg.0
0x304a  ldarg.s  4
0x304c  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_dataFeedQueries
0x3051  ldarg.0
0x3052  call     instance string[] Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::GetQueryValueSelect()
0x3057  stloc.0
0x3058  ldloc.0
0x3059  brfalse.s loc_309D
0x305b  ldarg.0
0x305c  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x3061  stfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_selectedColumns
0x3066  ldloc.0
0x3067  stloc.3
0x3068  ldc.i4.0
0x3069  stloc.s  4
0x306b  br.s     loc_3096
0x306d  ldloc.3
0x306e  ldloc.s  4
0x3070  ldelem.ref
0x3071  stloc.s  5
0x3073  ldarg.0
0x3074  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_selectedColumns
0x3079  ldloc.s  5
0x307b  callvirt instance bool [mscorlib]System.Collections.Hashtable::ContainsKey(object)
0x3080  brtrue.s loc_3090
0x3082  ldarg.0
0x3083  ldfld    class [mscorlib]System.Collections.Hashtable Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::m_selectedColumns
0x3088  ldloc.s  5
0x308a  ldnull
0x308b  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3090  ldloc.s  4
0x3092  ldc.i4.1
0x3093  add
0x3094  stloc.s  4
0x3096  ldloc.s  4
0x3098  ldloc.3
0x3099  ldlen
0x309a  conv.i4
0x309b  blt.s    loc_306D
0x309d  ret
```
