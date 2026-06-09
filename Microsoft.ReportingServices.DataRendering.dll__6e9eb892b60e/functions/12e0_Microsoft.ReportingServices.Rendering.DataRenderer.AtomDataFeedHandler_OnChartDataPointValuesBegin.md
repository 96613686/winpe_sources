# Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnChartDataPointValuesBegin

- ea: `0x12e0`
- end: `0x152d`
- name: `Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::OnChartDataPointValuesBegin`
- size: `589`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11e0`
- `0x12e0`
- `0x3370`

## pseudocode

```c

```

## disassembly

```asm
0x12e0  ldarg.1
0x12e1  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Instance()
0x12e6  stloc.0
0x12e7  ldnull
0x12e8  stloc.1
0x12e9  ldc.i4.s 0x12
0x12eb  stloc.2
0x12ec  ldarg.1
0x12ed  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_X()
0x12f2  brfalse.s loc_132C
0x12f4  ldarg.2
0x12f5  brfalse.s loc_131F
0x12f7  ldloc.0
0x12f8  brfalse.s loc_131F
0x12fa  ldloc.0
0x12fb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x1300  brfalse.s loc_131F
0x1302  ldloc.0
0x1303  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x1308  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x130d  stloc.1
0x130e  ldloc.0
0x130f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_X()
0x1314  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1319  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x131e  stloc.2
0x131f  ldarg.0
0x1320  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1325  ldloc.1
0x1326  ldloc.2
0x1327  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x132c  ldarg.1
0x132d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Y()
0x1332  brfalse.s loc_136C
0x1334  ldarg.2
0x1335  brfalse.s loc_135F
0x1337  ldloc.0
0x1338  brfalse.s loc_135F
0x133a  ldloc.0
0x133b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x1340  brfalse.s loc_135F
0x1342  ldloc.0
0x1343  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x1348  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x134d  stloc.1
0x134e  ldloc.0
0x134f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Y()
0x1354  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1359  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x135e  stloc.2
0x135f  ldarg.0
0x1360  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1365  ldloc.1
0x1366  ldloc.2
0x1367  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x136c  ldarg.1
0x136d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Size()
0x1372  brfalse.s loc_13AC
0x1374  ldarg.2
0x1375  brfalse.s loc_139F
0x1377  ldloc.0
0x1378  brfalse.s loc_139F
0x137a  ldloc.0
0x137b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x1380  brfalse.s loc_139F
0x1382  ldloc.0
0x1383  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x1388  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x138d  stloc.1
0x138e  ldloc.0
0x138f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Size()
0x1394  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1399  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x139e  stloc.2
0x139f  ldarg.0
0x13a0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x13a5  ldloc.1
0x13a6  ldloc.2
0x13a7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x13ac  ldarg.1
0x13ad  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_High()
0x13b2  brfalse.s loc_13EC
0x13b4  ldarg.2
0x13b5  brfalse.s loc_13DF
0x13b7  ldloc.0
0x13b8  brfalse.s loc_13DF
0x13ba  ldloc.0
0x13bb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x13c0  brfalse.s loc_13DF
0x13c2  ldloc.0
0x13c3  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x13c8  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x13cd  stloc.1
0x13ce  ldloc.0
0x13cf  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_High()
0x13d4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x13d9  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x13de  stloc.2
0x13df  ldarg.0
0x13e0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x13e5  ldloc.1
0x13e6  ldloc.2
0x13e7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x13ec  ldarg.1
0x13ed  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Low()
0x13f2  brfalse.s loc_142C
0x13f4  ldarg.2
0x13f5  brfalse.s loc_141F
0x13f7  ldloc.0
0x13f8  brfalse.s loc_141F
0x13fa  ldloc.0
0x13fb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x1400  brfalse.s loc_141F
0x1402  ldloc.0
0x1403  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x1408  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x140d  stloc.1
0x140e  ldloc.0
0x140f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Low()
0x1414  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1419  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x141e  stloc.2
0x141f  ldarg.0
0x1420  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1425  ldloc.1
0x1426  ldloc.2
0x1427  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x142c  ldarg.1
0x142d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Start()
0x1432  brfalse.s loc_146C
0x1434  ldarg.2
0x1435  brfalse.s loc_145F
0x1437  ldloc.0
0x1438  brfalse.s loc_145F
0x143a  ldloc.0
0x143b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x1440  brfalse.s loc_145F
0x1442  ldloc.0
0x1443  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x1448  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x144d  stloc.1
0x144e  ldloc.0
0x144f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Start()
0x1454  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1459  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x145e  stloc.2
0x145f  ldarg.0
0x1460  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1465  ldloc.1
0x1466  ldloc.2
0x1467  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x146c  ldarg.1
0x146d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_End()
0x1472  brfalse.s loc_14AC
0x1474  ldarg.2
0x1475  brfalse.s loc_149F
0x1477  ldloc.0
0x1478  brfalse.s loc_149F
0x147a  ldloc.0
0x147b  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x1480  brfalse.s loc_149F
0x1482  ldloc.0
0x1483  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x1488  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x148d  stloc.1
0x148e  ldloc.0
0x148f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_End()
0x1494  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1499  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x149e  stloc.2
0x149f  ldarg.0
0x14a0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x14a5  ldloc.1
0x14a6  ldloc.2
0x14a7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x14ac  ldarg.1
0x14ad  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Mean()
0x14b2  brfalse.s loc_14EC
0x14b4  ldarg.2
0x14b5  brfalse.s loc_14DF
0x14b7  ldloc.0
0x14b8  brfalse.s loc_14DF
0x14ba  ldloc.0
0x14bb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x14c0  brfalse.s loc_14DF
0x14c2  ldloc.0
0x14c3  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x14c8  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x14cd  stloc.1
0x14ce  ldloc.0
0x14cf  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Mean()
0x14d4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x14d9  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x14de  stloc.2
0x14df  ldarg.0
0x14e0  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x14e5  ldloc.1
0x14e6  ldloc.2
0x14e7  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x14ec  ldarg.1
0x14ed  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ReportVariantProperty [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValues::get_Median()
0x14f2  brfalse.s loc_152C
0x14f4  ldarg.2
0x14f5  brfalse.s loc_151F
0x14f7  ldloc.0
0x14f8  brfalse.s loc_151F
0x14fa  ldloc.0
0x14fb  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x1500  brfalse.s loc_151F
0x1502  ldloc.0
0x1503  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x1508  call     string Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandler::XmlConvertOrginalValue(object value)
0x150d  stloc.1
0x150e  ldloc.0
0x150f  callvirt instance object [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.OnDemandReportRendering.ChartDataPointValuesInstance::get_Median()
0x1514  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1519  call     valuetype [mscorlib]System.TypeCode [mscorlib]System.Type::GetTypeCode(class [mscorlib]System.Type)
0x151e  stloc.2
0x151f  ldarg.0
0x1520  ldfld    class Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedHandlerBase::m_visitor
0x1525  ldloc.1
0x1526  ldloc.2
0x1527  callvirt instance void Microsoft.ReportingServices.Rendering.DataRenderer.AtomDataFeedVisitor::WriteValue(string value, valuetype [mscorlib]System.TypeCode typeCode)
0x152c  ret
```
