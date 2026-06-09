# Microsoft.ReportingServices.Modeling.DataSourceView::LoadXmlElement

- ea: `0xd000`
- end: `0xd1b4`
- name: `Microsoft.ReportingServices.Modeling.DataSourceView::LoadXmlElement`
- size: `436`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0xd000`
- `0xd1c0`
- `0x2f850`

## string_xrefs

- `0xd196`: `http://www.w3.org/2001/XMLSchema`
- `0xd0d4`: `CreatedTimestamp`
- `0xd0e6`: `LastSchemaUpdate`

## pseudocode

```c

```

## disassembly

```asm
0xd000  ldarg.1
0xd001  callvirt instance string [System.Xml]System.Xml.XmlReader::get_LocalName()
0xd006  stloc.0
0xd007  ldloc.0
0xd008  brfalse  loc_D1B0
0xd00d  ldloc.0
0xd00e  call     instance int32 [mscorlib]System.String::get_Length()
0xd013  stloc.1
0xd014  ldloc.1
0xd015  ldc.i4.s 0xB
0xd017  bgt.s    loc_D03F
0xd019  ldloc.1
0xd01a  ldc.i4.2
0xd01b  sub
0xd01c  switch   loc_D07F, loc_D1B0, loc_D094, loc_D1B0, loc_D109
0xd035  ldloc.1
0xd036  ldc.i4.s 0xB
0xd038  beq.s    loc_D051
0xd03a  br       loc_D1B0
0xd03f  ldloc.1
0xd040  ldc.i4.s 0xC
0xd042  beq      loc_D0F7
0xd047  ldloc.1
0xd048  ldc.i4.s 0x10
0xd04a  beq.s    loc_D068
0xd04c  br       loc_D1B0
0xd051  ldloc.0
0xd052  ldc.i4.0
0xd053  call     instance char [mscorlib]System.String::get_Chars(int32)
0xd058  stloc.2
0xd059  ldloc.2
0xd05a  ldc.i4.s 0x41
0xd05c  beq.s    loc_D0BE
0xd05e  ldloc.2
0xd05f  ldc.i4.s 0x44
0xd061  beq.s    loc_D0A9
0xd063  br       loc_D1B0
0xd068  ldloc.0
0xd069  ldc.i4.0
0xd06a  call     instance char [mscorlib]System.String::get_Chars(int32)
0xd06f  stloc.2
0xd070  ldloc.2
0xd071  ldc.i4.s 0x43
0xd073  beq.s    loc_D0D3
0xd075  ldloc.2
0xd076  ldc.i4.s 0x4C
0xd078  beq.s    loc_D0E5
0xd07a  br       loc_D1B0
0xd07f  ldloc.0
0xd080  ldstr    aId// "ID"
0xd085  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd08a  brtrue   loc_D11B
0xd08f  br       loc_D1B0
0xd094  ldloc.0
0xd095  ldstr    aName// "Name"
0xd09a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd09f  brtrue   loc_D12C
0xd0a4  br       loc_D1B0
0xd0a9  ldloc.0
0xd0aa  ldstr    aDescription// "Description"
0xd0af  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0b4  brtrue   loc_D13A
0xd0b9  br       loc_D1B0
0xd0be  ldloc.0
0xd0bf  ldstr    aAnnotations// "Annotations"
0xd0c4  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0c9  brtrue   loc_D164
0xd0ce  br       loc_D1B0
0xd0d3  ldloc.0
0xd0d4  ldstr    aCreatedtimesta// "CreatedTimestamp"
0xd0d9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0de  brtrue.s loc_D148
0xd0e0  br       loc_D1B0
0xd0e5  ldloc.0
0xd0e6  ldstr    aLastschemaupda// "LastSchemaUpdate"
0xd0eb  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd0f0  brtrue.s loc_D156
0xd0f2  br       loc_D1B0
0xd0f7  ldloc.0
0xd0f8  ldstr    aDatasourceid// "DataSourceID"
0xd0fd  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd102  brtrue.s loc_D182
0xd104  br       loc_D1B0
0xd109  ldloc.0
0xd10a  ldstr    aSchema// "Schema"
0xd10f  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd114  brtrue.s loc_D190
0xd116  br       loc_D1B0
0xd11b  ldarg.0
0xd11c  ldarg.1
0xd11d  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0xd122  stfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_id
0xd127  br       loc_D1B2
0xd12c  ldarg.0
0xd12d  ldarg.1
0xd12e  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0xd133  stfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_name
0xd138  br.s     loc_D1B2
0xd13a  ldarg.0
0xd13b  ldarg.1
0xd13c  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0xd141  stfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_description
0xd146  br.s     loc_D1B2
0xd148  ldarg.0
0xd149  ldarg.1
0xd14a  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::ReadDateTimeChecked(class [System.Xml]System.Xml.XmlReader xr)
0xd14f  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::m_createdTimestamp
0xd154  br.s     loc_D1B2
0xd156  ldarg.0
0xd157  ldarg.1
0xd158  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::ReadDateTimeChecked(class [System.Xml]System.Xml.XmlReader xr)
0xd15d  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Modeling.DataSourceView::m_lastSchemaUpdate
0xd162  br.s     loc_D1B2
0xd164  ldarg.0
0xd165  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0xd16a  stfld    class [System.Xml]System.Xml.XmlDocument Microsoft.ReportingServices.Modeling.DataSourceView::m_annotations
0xd16f  ldarg.0
0xd170  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.ReportingServices.Modeling.DataSourceView::m_annotations
0xd175  ldarg.1
0xd176  callvirt instance class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::ReadSubtree()
0xd17b  callvirt instance void [System.Xml]System.Xml.XmlDocument::Load(class [System.Xml]System.Xml.XmlReader)
0xd180  br.s     loc_D1B2
0xd182  ldarg.0
0xd183  ldarg.1
0xd184  callvirt instance string [System.Xml]System.Xml.XmlReader::ReadElementContentAsString()
0xd189  stfld    string Microsoft.ReportingServices.Modeling.DataSourceView::m_dataSourceID
0xd18e  br.s     loc_D1B2
0xd190  ldarg.1
0xd191  ldstr    aSchema_0// "schema"
0xd196  ldstr    aHttpWwwW3Org20_1// "http://www.w3.org/2001/XMLSchema"
0xd19b  callvirt instance bool [System.Xml]System.Xml.XmlReader::ReadToDescendant(string, string)
0xd1a0  brfalse.s loc_D1B2
0xd1a2  ldarg.0
0xd1a3  ldfld    class IDsvInfo Microsoft.ReportingServices.Modeling.DataSourceView::m_dsvInfo
0xd1a8  ldarg.1
0xd1a9  callvirt instance void IDsvInfo::Load(class [System.Xml]System.Xml.XmlReader xr)
0xd1ae  br.s     loc_D1B2
0xd1b0  ldc.i4.0
0xd1b1  ret
0xd1b2  ldc.i4.1
0xd1b3  ret
```
