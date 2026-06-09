# Microsoft.ReportingServices.ReportRendering.DundasChart::RenderDataPoint

- ea: `0x18530`
- end: `0x18df9`
- name: `Microsoft.ReportingServices.ReportRendering.DundasChart::RenderDataPoint`
- size: `2249`
- prototype: ``
- caller_count: `1`
- callee_count: `42`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x181e0`

## callees

- `0x9c90`
- `0xb4c0`
- `0x15420`
- `0x16030`
- `0x161f0`
- `0x16230`
- `0x16350`
- `0x163f0`
- `0x16490`
- `0x164e0`
- `0x16500`
- `0x16540`
- `0x16640`
- `0x16690`
- `0x18530`
- `0x18e00`
- `0x179fe0`
- `0x18f510`
- `0x1a3dd0`
- `0x1a3ee0`
- `0x1a3f00`
- `0x1a3f80`
- `0x1a5b00`
- `0x1a5b20`
- `0x1a5b40`
- `0x1a5b60`
- `0x1a5b80`
- `0x1a5ba0`
- `0x1a6020`
- `0x1a6040`
- `0x1a6060`
- `0x1a6080`
- `0x1a60a0`
- `0x1a7470`
- `0x1a74a0`
- `0x1afab0`
- `0x1afad0`
- `0x1afaf0`
- `0x1afb10`
- `0x1afb50`
- `0x1afb70`
- `0x1ca990`

## string_xrefs

- `0x1869c`: `Inside`
- `0x186b1`: `Outside`

## pseudocode

```c

```

## disassembly

```asm
0x18530  ldarg.3
0x18531  newobj   instance void [DundasWebChart]Dundas.Charting.WebControl.DataPoint::.ctor(class [DundasWebChart]Dundas.Charting.WebControl.Series)
0x18536  stloc.0
0x18537  ldsfld   valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::Empty
0x1853c  stloc.1
0x1853d  ldarg.s  5
0x1853f  brfalse.s loc_1854A
0x18541  ldarg.s  5
0x18543  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x18548  brtrue.s loc_18583
0x1854a  ldarg.s  6
0x1854c  brtrue.s loc_18557
0x1854e  ldloc.0
0x1854f  ldc.i4.1
0x18550  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_EmptyX(bool)
0x18555  br.s     loc_1856E
0x18557  ldloc.0
0x18558  ldarg.s  6
0x1855a  ldc.i4.1
0x1855b  newarr   [mscorlib]System.Object
0x18560  dup
0x18561  ldc.i4.0
0x18562  ldc.i4.0
0x18563  box      [mscorlib]System.Int32
0x18568  stelem.ref
0x18569  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPoint::SetValueXY(object, object[])
0x1856e  ldloc.0
0x1856f  ldc.i4.1
0x18570  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPoint::set_Empty(bool)
0x18575  ldarg.3
0x18576  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.DataPointCollection [DundasWebChart]Dundas.Charting.WebControl.Series::get_Points()
0x1857b  ldloc.0
0x1857c  callvirt instance int32 [DundasWebChart]Dundas.Charting.WebControl.DataPointCollection::Add(class [DundasWebChart]Dundas.Charting.WebControl.DataPoint)
0x18581  pop
0x18582  ret
0x18583  ldarg.0
0x18584  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18589  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointList Microsoft.ReportingServices.ReportProcessing.Chart::get_ChartDataPoints()
0x1858e  ldarg.s  5
0x18590  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x18595  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_DataPointIndex()
0x1859a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPoint Microsoft.ReportingServices.ReportProcessing.ChartDataPointList::get_Item(int32 index)
0x1859f  stloc.2
0x185a0  ldloc.0
0x185a1  ldarg.s  7
0x185a3  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_ElementID(int32)
0x185a8  ldloc.2
0x185a9  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Action Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_Action()
0x185ae  brfalse.s loc_185CA
0x185b0  ldloc.0
0x185b1  ldstr    aX_0// "X"
0x185b6  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Href(string)
0x185bb  ldloc.0
0x185bc  ldarg.s  7
0x185be  ldarg.0
0x185bf  ldfld    int32 Microsoft.ReportingServices.ReportRendering.DundasChart::c_offset
0x185c4  add
0x185c5  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MapAreaID(int32)
0x185ca  ldloc.2
0x185cb  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x185d0  brfalse  loc_18795
0x185d5  ldloc.2
0x185d6  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x185db  callvirt instance bool Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Visible()
0x185e0  brfalse  loc_18795
0x185e5  ldloc.0
0x185e6  ldarg.0
0x185e7  ldloc.2
0x185e8  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x185ed  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_StyleClass()
0x185f2  ldarg.s  5
0x185f4  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x185f9  callvirt instance object[] Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_DataLabelStyleAttributeValues()
0x185fe  call     instance class [System.Drawing]System.Drawing.Font Microsoft.ReportingServices.ReportRendering.DundasChart::GetFont(class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues)
0x18603  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Font(class [System.Drawing]System.Drawing.Font)
0x18608  ldloc.0
0x18609  ldarg.0
0x1860a  ldloc.2
0x1860b  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18610  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_StyleClass()
0x18615  ldarg.s  5
0x18617  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x1861c  callvirt instance object[] Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_DataLabelStyleAttributeValues()
0x18621  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.ReportingServices.ReportRendering.DundasChart::GetTextColor(class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues)
0x18626  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_FontColor(valuetype [System.Drawing]System.Drawing.Color)
0x1862b  ldloc.0
0x1862c  ldloc.2
0x1862d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18632  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Rotation()
0x18637  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_FontAngle(int32)
0x1863c  ldloc.0
0x1863d  ldarg.0
0x1863e  ldloc.2
0x1863f  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18644  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_StyleClass()
0x18649  ldarg.s  5
0x1864b  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x18650  callvirt instance object[] Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_DataLabelStyleAttributeValues()
0x18655  call     instance string Microsoft.ReportingServices.ReportRendering.DundasChart::GetFormatCode(class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues)
0x1865a  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_LabelFormat(string)
0x1865f  ldc.i4.3
0x18660  ldarg.0
0x18661  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18666  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x1866b  beq.s    loc_1867B
0x1866d  ldc.i4.7
0x1866e  ldarg.0
0x1866f  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18674  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18679  bne.un.s loc_186BD
0x1867b  ldloc.2
0x1867c  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18681  callvirt instance valuetype Positions Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Position()
0x18686  brfalse.s loc_18696
0x18688  ldc.i4.5
0x18689  ldloc.2
0x1868a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x1868f  callvirt instance valuetype Positions Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Position()
0x18694  bne.un.s loc_186AB
0x18696  ldloc.0
0x18697  ldstr    aLabelstyle// "LabelStyle"
0x1869c  ldstr    aInside// "Inside"
0x186a1  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x186a6  br       loc_18739
0x186ab  ldloc.0
0x186ac  ldstr    aLabelstyle// "LabelStyle"
0x186b1  ldstr    aOutside// "Outside"
0x186b6  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x186bb  br.s     loc_18739
0x186bd  ldloc.2
0x186be  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x186c3  callvirt instance valuetype Positions Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Position()
0x186c8  brfalse.s loc_186F1
0x186ca  ldloc.0
0x186cb  ldstr    aLabelstyle// "LabelStyle"
0x186d0  ldloc.2
0x186d1  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x186d6  callvirt instance valuetype Positions Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Position()
0x186db  stloc.s  0xB
0x186dd  ldloca.s 0xB
0x186df  constrained. Positions
0x186e5  callvirt instance string [mscorlib]System.Object::ToString()
0x186ea  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x186ef  br.s     loc_18739
0x186f1  ldarg.3
0x186f2  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle [DundasWebChart]Dundas.Charting.WebControl.Series::get_SmartLabels()
0x186f7  ldc.i4.1
0x186f8  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle::set_Enabled(bool)
0x186fd  ldarg.3
0x186fe  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle [DundasWebChart]Dundas.Charting.WebControl.Series::get_SmartLabels()
0x18703  ldc.i4.1
0x18704  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle::set_AllowOutsidePlotArea(valuetype [DundasWebChart]Dundas.Charting.WebControl.LabelOutsidePlotAreaStyle)
0x18709  ldarg.3
0x1870a  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle [DundasWebChart]Dundas.Charting.WebControl.Series::get_SmartLabels()
0x1870f  ldc.i4.5
0x18710  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle::set_CalloutLineStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.ChartDashStyle)
0x18715  ldarg.3
0x18716  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle [DundasWebChart]Dundas.Charting.WebControl.Series::get_SmartLabels()
0x1871b  ldc.i4   0x8C
0x18720  ldc.i4.0
0x18721  ldc.i4.0
0x18722  ldc.i4.0
0x18723  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32, int32)
0x18728  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle::set_CalloutLineColor(valuetype [System.Drawing]System.Drawing.Color)
0x1872d  ldarg.3
0x1872e  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle [DundasWebChart]Dundas.Charting.WebControl.Series::get_SmartLabels()
0x18733  ldc.i4.1
0x18734  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.SmartLabelsStyle::set_CalloutLineWidth(int32)
0x18739  ldnull
0x1873a  stloc.s  0xA
0x1873c  ldloc.2
0x1873d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18742  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Value()
0x18747  brfalse.s loc_1877E
0x18749  ldc.i4.3
0x1874a  ldloc.2
0x1874b  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18750  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Value()
0x18755  callvirt instance valuetype Types Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_Type()
0x1875a  bne.un.s loc_18770
0x1875c  ldloc.2
0x1875d  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataLabel Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_DataLabel()
0x18762  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ExpressionInfo Microsoft.ReportingServices.ReportProcessing.ChartDataLabel::get_Value()
0x18767  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ExpressionInfo::get_Value()
0x1876c  stloc.s  0xA
0x1876e  br.s     loc_1877E
0x18770  ldarg.s  5
0x18772  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x18777  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_DataLabelValue()
0x1877c  stloc.s  0xA
0x1877e  ldloc.s  0xA
0x18780  brtrue.s loc_1878B
0x18782  ldloc.0
0x18783  ldc.i4.1
0x18784  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_ShowLabelAsValue(bool)
0x18789  br.s     loc_187C5
0x1878b  ldloc.0
0x1878c  ldloc.s  0xA
0x1878e  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Label(string)
0x18793  br.s     loc_187C5
0x18795  ldarg.1
0x18796  ldind.u1
0x18797  brfalse.s loc_187C5
0x18799  ldc.i4.3
0x1879a  ldarg.0
0x1879b  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x187a0  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x187a5  beq.s    loc_187B5
0x187a7  ldc.i4.7
0x187a8  ldarg.0
0x187a9  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x187ae  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x187b3  bne.un.s loc_187C5
0x187b5  ldarg.3
0x187b6  ldstr    aLabelstyle// "LabelStyle"
0x187bb  ldstr    aDisabled// "Disabled"
0x187c0  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x187c5  ldarg.0
0x187c6  call     instance bool Microsoft.ReportingServices.ReportRendering.DundasChart::get_IsExploded()
0x187cb  brfalse.s loc_187DD
0x187cd  ldloc.0
0x187ce  ldstr    aExploded// "Exploded"
0x187d3  ldstr    aTrue// "true"
0x187d8  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x187dd  ldarg.1
0x187de  ldind.u1
0x187df  brfalse.s loc_187F1
0x187e1  ldc.i4.6
0x187e2  ldloc.2
0x187e3  callvirt instance valuetype MarkerTypes Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerType()
0x187e8  bne.un.s loc_187F1
0x187ea  ldarg.0
0x187eb  call     instance valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle Microsoft.ReportingServices.ReportRendering.DundasChart::GetNextSeriesMarkerStyle()
0x187f0  pop
0x187f1  ldloc.2
0x187f2  callvirt instance valuetype MarkerTypes Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerType()
0x187f7  brfalse  loc_188F5
0x187fc  ldc.r8   0.0
0x18805  stloc.s  0xC
0x18807  ldloc.2
0x18808  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerSize()
0x1880d  brfalse.s loc_1881C
0x1880f  ldloc.2
0x18810  callvirt instance string Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerSize()
0x18815  ldloca.s 0xC
0x18817  call     void Microsoft.ReportingServices.ReportProcessing.Validator::ParseSize(string size, [out] float64& sizeInMM)
0x1881c  ldloc.0
0x1881d  ldloc.s  0xC
0x1881f  ldc.r8   96.0
0x18828  mul
0x18829  ldc.r8   0.03937007874
0x18832  mul
0x18833  call     float64 [mscorlib]System.Math::Round(float64)
0x18838  conv.i4
0x18839  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerSize(int32)
0x1883e  ldc.i4.6
0x1883f  ldloc.2
0x18840  callvirt instance valuetype MarkerTypes Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerType()
0x18845  bne.un.s loc_18855
0x18847  ldloc.0
0x18848  ldarg.0
0x18849  ldfld    valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle Microsoft.ReportingServices.ReportRendering.DundasChart::m_currentAutoMarkerStyle
0x1884e  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle)
0x18853  br.s     loc_18867
0x18855  ldloc.0
0x18856  ldarg.0
0x18857  ldloc.2
0x18858  callvirt instance valuetype MarkerTypes Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerType()
0x1885d  call     instance valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle Microsoft.ReportingServices.ReportRendering.DundasChart::DundasMarkerStyle(valuetype MarkerTypes type)
0x18862  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle)
0x18867  ldarg.1
0x18868  ldind.u1
0x18869  brfalse.s loc_18883
0x1886b  ldarg.3
0x1886c  ldloc.0
0x1886d  callvirt instance valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::get_MarkerStyle()
0x18872  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle)
0x18877  ldarg.3
0x18878  ldloc.0
0x18879  callvirt instance int32 [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::get_MarkerSize()
0x1887e  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerSize(int32)
0x18883  ldarg.0
0x18884  ldstr    aBackgroundcolo// "BackgroundColor"
0x18889  ldloc.2
0x1888a  callvirt instance class Microsoft.ReportingServices.ReportProcessing.Style Microsoft.ReportingServices.ReportProcessing.ChartDataPoint::get_MarkerStyleClass()
0x1888f  ldarg.s  5
0x18891  callvirt instance class Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo Microsoft.ReportingServices.ReportRendering.ChartDataPoint::get_InstanceInfo()
0x18896  callvirt instance object[] Microsoft.ReportingServices.ReportProcessing.ChartDataPointInstanceInfo::get_MarkerStyleAttributeValues()
0x1889b  ldc.i4.0
0x1889c  call     object Microsoft.ReportingServices.ReportRendering.Style::GetStyleValue(string styleName, class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues, bool returnDefaultStyle)
0x188a1  ldloca.s 1
0x188a3  call     instance bool Microsoft.ReportingServices.ReportRendering.DundasChart::SetDataPointColorProperty(object rdlColor, [out] valuetype [System.Drawing]System.Drawing.Color& dundasColor)
0x188a8  brfalse.s loc_188BC
0x188aa  ldloc.0
0x188ab  ldloc.1
0x188ac  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerColor(valuetype [System.Drawing]System.Drawing.Color)
0x188b1  ldarg.1
0x188b2  ldind.u1
0x188b3  brfalse.s loc_188BC
0x188b5  ldarg.3
  ... truncated ...
```
