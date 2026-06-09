# Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTablix

- ea: `0xb1280`
- end: `0xb1ea9`
- name: `Microsoft.ReportingServices.ReportPublishing.ReportPublishing::ReadTablix`
- size: `3113`
- prototype: ``
- caller_count: `3`
- callee_count: `95`
- tags: `service_task, broker_com_uri`

## callers

- `0x9ec50`
- `0xa8b30`
- `0xb3ab0`

## callees

- `0x9d010`
- `0x9d040`
- `0x9ef40`
- `0x9ef60`
- `0x9f050`
- `0x9f6f0`
- `0x9f860`
- `0x9fe50`
- `0xaa4b0`
- `0xab1c0`
- `0xac160`
- `0xac750`
- `0xac790`
- `0xac850`
- `0xb0fd0`
- `0xb10f0`
- `0xb1100`
- `0xb1270`
- `0xb1280`
- `0xb1eb0`
- `0xb2e80`
- `0xb3a20`
- `0xb3df0`
- `0xbb940`
- `0xbb9a0`
- `0xbcda0`
- `0xbcdb0`
- `0xbcdc0`
- `0xbcdd0`
- `0xbcde0`
- `0xbcdf0`
- `0xbce20`
- `0xbe1c0`
- `0xbe2b0`
- `0xbf360`
- `0xc1260`
- `0xc15c0`
- `0x10def0`
- `0x10df00`
- `0x10df30`
- `0x10df40`
- `0x10dfe0`
- `0x10e000`
- `0x10ea30`
- `0x10ffa0`
- `0x111b20`
- `0x124ca0`
- `0x124cb0`
- `0x124cd0`
- `0x124d20`

## pseudocode

```c

```

## disassembly

```asm
0xb1280  ldarg.0
0xb1281  call     instance int32 Microsoft.ReportingServices.ReportPublishing.ReportPublishing::GenerateID()
0xb1286  ldarg.1
0xb1287  newobj   instance void Microsoft.ReportingServices.ReportIntermediateFormat.Tablix::.ctor(int32 id, class Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem parent)
0xb128c  stloc.0
0xb128d  ldloc.0
0xb128e  ldarg.0
0xb128f  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb1294  ldstr    aName_1// "Name"
0xb1299  callvirt instance string [System.Xml]System.Xml.XmlReader::GetAttribute(string)
0xb129e  callvirt instance void Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::set_Name(string value)
0xb12a3  ldc.i4.0
0xb12a4  stloc.1
0xb12a5  ldarga.s 2
0xb12a7  call     instance valuetype Microsoft.ReportingServices.ReportPublishing.LocationFlags Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_Location()
0xb12ac  ldc.i4.4
0xb12ad  and
0xb12ae  brtrue.s loc_B12BF
0xb12b0  ldc.i4.1
0xb12b1  stloc.1
0xb12b2  ldarg.0
0xb12b3  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion>::.ctor()
0xb12b8  stfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_nestedDataRegions
0xb12bd  br.s     loc_B12DE
0xb12bf  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0xb12c4  ldarg.0
0xb12c5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_nestedDataRegions
0xb12ca  ldnull
0xb12cb  cgt.un
0xb12cd  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0xb12d2  ldarg.0
0xb12d3  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_nestedDataRegions
0xb12d8  ldloc.0
0xb12d9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion>::Add(var<u1>)
0xb12de  ldarga.s 2
0xb12e0  dup
0xb12e1  call     instance valuetype Microsoft.ReportingServices.ReportPublishing.LocationFlags Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_Location()
0xb12e6  ldc.i4.6
0xb12e7  or
0xb12e8  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_Location(valuetype Microsoft.ReportingServices.ReportPublishing.LocationFlags value)
0xb12ed  ldarga.s 2
0xb12ef  ldloc.0
0xb12f0  callvirt instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_ObjectType()
0xb12f5  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectType(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType value)
0xb12fa  ldarga.s 2
0xb12fc  ldloc.0
0xb12fd  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xb1302  call     instance void Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::set_ObjectName(string value)
0xb1307  ldarg.0
0xb1308  ldloc.0
0xb1309  call     instance void Microsoft.ReportingServices.ReportPublishing.ReportPublishing::RegisterDataRegion(class Microsoft.ReportingServices.ReportIntermediateFormat.DataRegion dataRegion)
0xb130e  ldc.i4.1
0xb130f  stloc.2
0xb1310  ldarg.0
0xb1311  ldfld    class Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportItemNames
0xb1316  ldarga.s 2
0xb1318  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb131d  ldarga.s 2
0xb131f  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb1324  ldarga.s 2
0xb1326  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb132b  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.CLSUniqueNameValidator::Validate(valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string name, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xb1330  brtrue.s loc_B1334
0xb1332  ldc.i4.0
0xb1333  stloc.2
0xb1334  ldarg.0
0xb1335  ldfld    class Microsoft.ReportingServices.ReportPublishing.ScopeNameValidator Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_scopeNames
0xb133a  ldc.i4.0
0xb133b  ldarga.s 2
0xb133d  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb1342  ldarga.s 2
0xb1344  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb1349  ldarga.s 2
0xb134b  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb1350  ldarga.s 2
0xb1352  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb1357  callvirt instance bool Microsoft.ReportingServices.ReportPublishing.ScopeNameValidator::Validate(bool isGrouping, string scopeName, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, class Microsoft.ReportingServices.ReportProcessing.ErrorContext errorContext)
0xb135c  brfalse.s loc_B1372
0xb135e  ldarg.0
0xb135f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.ISortFilterScope> Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reportScopes
0xb1364  ldloc.0
0xb1365  callvirt instance string Microsoft.ReportingServices.ReportIntermediateFormat.ReportItem::get_Name()
0xb136a  ldloc.0
0xb136b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.ReportIntermediateFormat.ISortFilterScope>::Add(var<u1>, !!T0)
0xb1370  br.s     loc_B1374
0xb1372  ldc.i4.0
0xb1373  stloc.2
0xb1374  ldarga.s 2
0xb1376  call     instance valuetype Microsoft.ReportingServices.ReportPublishing.LocationFlags Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_Location()
0xb137b  ldc.i4.s 0x40
0xb137d  and
0xb137e  brfalse.s loc_B13A6
0xb1380  ldarga.s 2
0xb1382  call     instance class Microsoft.ReportingServices.ReportProcessing.PublishingErrorContext Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ErrorContext()
0xb1387  ldc.i4.s 0x16
0xb1389  ldc.i4.0
0xb138a  ldarga.s 2
0xb138c  call     instance valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectType()
0xb1391  ldarga.s 2
0xb1393  call     instance string Microsoft.ReportingServices.ReportPublishing.PublishingContextStruct::get_ObjectName()
0xb1398  ldnull
0xb1399  call     T0x2B000001
0xb139e  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ProcessingMessage Microsoft.ReportingServices.ReportProcessing.ErrorContext::Register(valuetype Microsoft.ReportingServices.ReportProcessing.ProcessingErrorCode code, valuetype Microsoft.ReportingServices.ReportProcessing.Severity severity, valuetype Microsoft.ReportingServices.ReportProcessing.ObjectType objectType, string objectName, string propertyName, string[] arguments)
0xb13a3  pop
0xb13a4  ldc.i4.0
0xb13a5  stloc.2
0xb13a6  ldnull
0xb13a7  stloc.3
0xb13a8  ldc.i4.0
0xb13a9  stloc.s  4
0xb13ab  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.ReportIntermediateFormat.TextBox>::.ctor()
0xb13b0  stloc.s  5
0xb13b2  ldnull
0xb13b3  stloc.s  6
0xb13b5  ldarg.0
0xb13b6  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb13bb  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0xb13c0  pop
0xb13c1  ldarg.0
0xb13c2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb13c7  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0xb13cc  stloc.s  7
0xb13ce  ldloc.s  7
0xb13d0  ldc.i4.1
0xb13d1  beq.s    loc_B13E1
0xb13d3  ldloc.s  7
0xb13d5  ldc.i4.s 0xF
0xb13d7  beq      loc_B1D70
0xb13dc  br       loc_B1D8A
0xb13e1  ldarg.0
0xb13e2  ldfld    class Microsoft.ReportingServices.ReportPublishing.RmlValidatingReader Microsoft.ReportingServices.ReportPublishing.ReportPublishing::m_reader
0xb13e7  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xb13ec  stloc.s  8
0xb13ee  ldloc.s  8
0xb13f0  brfalse  loc_B1D8A
0xb13f5  ldloc.s  8
0xb13f7  call     instance int32 [mscorlib]System.String::get_Length()
0xb13fc  stloc.s  9
0xb13fe  ldloc.s  9
0xb1400  ldc.i4.3
0xb1401  sub
0xb1402  switch   loc_B16E2, loc_B16F8, loc_B149A, loc_B14BB, loc_B1530, loc_B157B, loc_B14DC, loc_B1506, loc_B15FB, loc_B15BD, loc_B18DC, loc_B1D8A, loc_B145C, loc_B1551, loc_B159C, loc_B163D, loc_B198C, loc_B1D8A, loc_B161C, loc_B1976
0xb1457  br       loc_B1D8A
0xb145c  ldloc.s  8
0xb145e  ldc.i4.0
0xb145f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1464  stloc.s  0xA
0xb1466  ldloc.s  0xA
0xb1468  ldc.i4.s 0x46
0xb146a  bgt.un.s loc_B1483
0xb146c  ldloc.s  0xA
0xb146e  ldc.i4.s 0x44
0xb1470  beq      loc_B1674
0xb1475  ldloc.s  0xA
0xb1477  ldc.i4.s 0x46
0xb1479  beq      loc_B16A0
0xb147e  br       loc_B1D8A
0xb1483  ldloc.s  0xA
0xb1485  ldc.i4.s 0x4C
0xb1487  beq      loc_B168A
0xb148c  ldloc.s  0xA
0xb148e  ldc.i4.s 0x53
0xb1490  beq      loc_B165E
0xb1495  br       loc_B1D8A
0xb149a  ldloc.s  8
0xb149c  ldc.i4.0
0xb149d  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb14a2  stloc.s  0xA
0xb14a4  ldloc.s  0xA
0xb14a6  ldc.i4.s 0x53
0xb14a8  beq      loc_B16B6
0xb14ad  ldloc.s  0xA
0xb14af  ldc.i4.s 0x57
0xb14b1  beq      loc_B16CC
0xb14b6  br       loc_B1D8A
0xb14bb  ldloc.s  8
0xb14bd  ldc.i4.0
0xb14be  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb14c3  stloc.s  0xA
0xb14c5  ldloc.s  0xA
0xb14c7  ldc.i4.s 0x48
0xb14c9  beq      loc_B170E
0xb14ce  ldloc.s  0xA
0xb14d0  ldc.i4.s 0x5A
0xb14d2  beq      loc_B1724
0xb14d7  br       loc_B1D8A
0xb14dc  ldloc.s  8
0xb14de  ldc.i4.0
0xb14df  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb14e4  stloc.s  0xA
0xb14e6  ldloc.s  0xA
0xb14e8  ldc.i4.s 0x43
0xb14ea  beq      loc_B173A
0xb14ef  ldloc.s  0xA
0xb14f1  ldc.i4.s 0x50
0xb14f3  beq      loc_B1750
0xb14f8  ldloc.s  0xA
0xb14fa  ldc.i4.s 0x54
0xb14fc  beq      loc_B1766
0xb1501  br       loc_B1D8A
0xb1506  ldloc.s  8
0xb1508  ldc.i4.0
0xb1509  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb150e  stloc.s  0xA
0xb1510  ldloc.s  0xA
0xb1512  ldc.i4.s 0x4C
0xb1514  beq      loc_B17A8
0xb1519  ldloc.s  0xA
0xb151b  ldc.i4.s 0x54
0xb151d  beq      loc_B1792
0xb1522  ldloc.s  0xA
0xb1524  ldc.i4.s 0x56
0xb1526  beq      loc_B177C
0xb152b  br       loc_B1D8A
0xb1530  ldloc.s  8
0xb1532  ldc.i4.0
0xb1533  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1538  stloc.s  0xA
0xb153a  ldloc.s  0xA
0xb153c  ldc.i4.s 0x46
0xb153e  beq      loc_B17D4
0xb1543  ldloc.s  0xA
0xb1545  ldc.i4.s 0x54
0xb1547  beq      loc_B17BE
0xb154c  br       loc_B1D8A
0xb1551  ldloc.s  8
0xb1553  ldc.i4.0
0xb1554  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1559  stloc.s  0xA
0xb155b  ldloc.s  0xA
0xb155d  ldc.i4.s 0x43
0xb155f  beq      loc_B1800
0xb1564  ldloc.s  0xA
0xb1566  ldc.i4.s 0x44
0xb1568  beq      loc_B17EA
0xb156d  ldloc.s  0xA
0xb156f  ldc.i4.s 0x52
0xb1571  beq      loc_B1816
0xb1576  br       loc_B1D8A
0xb157b  ldloc.s  8
0xb157d  ldc.i4.0
0xb157e  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1583  stloc.s  0xA
0xb1585  ldloc.s  0xA
0xb1587  ldc.i4.s 0x42
0xb1589  beq      loc_B182C
0xb158e  ldloc.s  0xA
0xb1590  ldc.i4.s 0x50
0xb1592  beq      loc_B1842
0xb1597  br       loc_B1D8A
0xb159c  ldloc.s  8
0xb159e  ldc.i4.0
0xb159f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb15a4  stloc.s  0xA
0xb15a6  ldloc.s  0xA
0xb15a8  ldc.i4.s 0x42
0xb15aa  beq      loc_B186E
0xb15af  ldloc.s  0xA
0xb15b1  ldc.i4.s 0x44
0xb15b3  beq      loc_B1858
0xb15b8  br       loc_B1D8A
0xb15bd  ldloc.s  8
0xb15bf  ldc.i4.0
0xb15c0  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb15c5  stloc.s  0xA
0xb15c7  ldloc.s  0xA
0xb15c9  ldc.i4.s 0x4B
0xb15cb  bgt.un.s loc_B15E4
0xb15cd  ldloc.s  0xA
0xb15cf  ldc.i4.s 0x42
0xb15d1  beq      loc_B18C6
0xb15d6  ldloc.s  0xA
0xb15d8  ldc.i4.s 0x4B
0xb15da  beq      loc_B1884
0xb15df  br       loc_B1D8A
0xb15e4  ldloc.s  0xA
0xb15e6  ldc.i4.s 0x52
0xb15e8  beq      loc_B189A
0xb15ed  ldloc.s  0xA
0xb15ef  ldc.i4.s 0x54
0xb15f1  beq      loc_B18B0
0xb15f6  br       loc_B1D8A
0xb15fb  ldloc.s  8
0xb15fd  ldc.i4.0
0xb15fe  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1603  stloc.s  0xA
0xb1605  ldloc.s  0xA
0xb1607  ldc.i4.s 0x44
0xb1609  beq      loc_B18F2
0xb160e  ldloc.s  0xA
0xb1610  ldc.i4.s 0x52
0xb1612  beq      loc_B1908
0xb1617  br       loc_B1D8A
0xb161c  ldloc.s  8
0xb161e  ldc.i4.0
0xb161f  call     instance char [mscorlib]System.String::get_Chars(int32)
0xb1624  stloc.s  0xA
0xb1626  ldloc.s  0xA
0xb1628  ldc.i4.s 0x4F
0xb162a  beq      loc_B1934
  ... truncated ...
```
