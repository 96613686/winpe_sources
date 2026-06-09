# Microsoft.ReportingServices.ReportRendering.DundasChart::RenderSeriesDataPoints

- ea: `0x181e0`
- end: `0x184c5`
- name: `Microsoft.ReportingServices.ReportRendering.DundasChart::RenderSeriesDataPoints`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x18140`

## callees

- `0x14050`
- `0x14990`
- `0x14a10`
- `0x14d80`
- `0x14ea0`
- `0x150a0`
- `0x15ea0`
- `0x15ff0`
- `0x16230`
- `0x16350`
- `0x165c0`
- `0x166e0`
- `0x181e0`
- `0x184d0`
- `0x18530`
- `0x1a3ee0`
- `0x1a3f00`
- `0x1a3f40`
- `0x1a3f80`

## string_xrefs

- `0x183cb`: `ShowOpenClose`

## pseudocode

```c

```

## disassembly

```asm
0x181e0  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x181e5  ldarg.1
0x181e6  ldnull
0x181e7  cgt.un
0x181e9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x181ee  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.ReportProcessing.Global::Tracer
0x181f3  ldarg.1
0x181f4  callvirt instance bool Microsoft.ReportingServices.ReportRendering.ChartMember::get_IsInnerMostMember()
0x181f9  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x181fe  ldarg.1
0x181ff  callvirt instance int32 Microsoft.ReportingServices.ReportRendering.ChartMember::get_MemberDataPointIndex()
0x18204  stloc.0
0x18205  ldarg.0
0x18206  ldfld    class Microsoft.ReportingServices.ReportRendering.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_owner
0x1820b  callvirt instance class Microsoft.ReportingServices.ReportRendering.ChartDataPointCollection Microsoft.ReportingServices.ReportRendering.Chart::get_DataPointCollection()
0x18210  callvirt instance int32 Microsoft.ReportingServices.ReportRendering.ChartDataPointCollection::get_CategoryCount()
0x18215  stloc.1
0x18216  ldloc.1
0x18217  brtrue.s loc_1821A
0x18219  ret
0x1821a  newobj   instance void [DundasWebChart]Dundas.Charting.WebControl.Series::.ctor()
0x1821f  stloc.3
0x18220  ldloc.3
0x18221  ldarg.0
0x18222  ldarg.1
0x18223  ldloca.s 2
0x18225  call     instance string Microsoft.ReportingServices.ReportRendering.DundasChart::DundasChartType(class Microsoft.ReportingServices.ReportRendering.ChartMember seriesHeader, [out] bool& isLineChart)
0x1822a  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_ChartType(string)
0x1822f  ldloc.3
0x18230  ldc.i4.0
0x18231  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_YValueType(valuetype [DundasWebChart]Dundas.Charting.WebControl.ChartValueTypes)
0x18236  ldloc.3
0x18237  ldarg.1
0x18238  callvirt instance bool Microsoft.ReportingServices.ReportRendering.ChartMember::IsPlotTypeLine()
0x1823d  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_PlotAsLine(bool)
0x18242  ldloc.3
0x18243  ldarg.1
0x18244  callvirt instance bool Microsoft.ReportingServices.ReportRendering.ChartMember::IsPlotTypeLine()
0x18249  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_PlotAsLine(bool)
0x1824e  ldc.i4.3
0x1824f  ldarg.0
0x18250  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18255  callvirt instance valuetype ChartPalette Microsoft.ReportingServices.ReportProcessing.Chart::get_Palette()
0x1825a  bne.un.s loc_18279
0x1825c  ldloc.3
0x1825d  ldc.r4   1.0
0x18262  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderWidth(float32)
0x18267  ldloc.3
0x18268  ldc.i4.5
0x18269  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.ChartDashStyle)
0x1826e  ldloc.3
0x1826f  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Black()
0x18274  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderColor(valuetype [System.Drawing]System.Drawing.Color)
0x18279  ldloc.3
0x1827a  ldstr    aSeries_0// "Series "
0x1827f  ldloca.s 0
0x18281  call     instance string [mscorlib]System.Int32::ToString()
0x18286  call     string [mscorlib]System.String::Concat(string, string)
0x1828b  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_Name(string)
0x18290  ldarg.2
0x18291  brfalse.s loc_1829A
0x18293  ldloc.3
0x18294  ldarg.2
0x18295  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_LegendText(string)
0x1829a  ldarg.0
0x1829b  ldfld    bool Microsoft.ReportingServices.ReportRendering.DundasChart::m_isScalarMode
0x182a0  brfalse.s loc_182AB
0x182a2  ldloc.3
0x182a3  ldc.i4.0
0x182a4  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_XValueIndexed(bool)
0x182a9  br.s     loc_182E8
0x182ab  ldloc.3
0x182ac  ldc.i4.7
0x182ad  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_XValueType(valuetype [DundasWebChart]Dundas.Charting.WebControl.ChartValueTypes)
0x182b2  ldc.i4.3
0x182b3  ldarg.0
0x182b4  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x182b9  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x182be  beq.s    loc_182E8
0x182c0  ldc.i4.7
0x182c1  ldarg.0
0x182c2  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x182c7  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x182cc  beq.s    loc_182E8
0x182ce  ldarg.0
0x182cf  ldarg.0
0x182d0  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x182d5  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x182da  call     instance bool Microsoft.ReportingServices.ReportRendering.DundasChart::ChartTypeWithExplicitXValue(valuetype ChartTypes type)
0x182df  brtrue.s loc_182E8
0x182e1  ldloc.3
0x182e2  ldc.i4.1
0x182e3  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_XValueIndexed(bool)
0x182e8  ldloc.3
0x182e9  callvirt instance bool [DundasWebChart]Dundas.Charting.WebControl.Series::get_PlotAsLine()
0x182ee  brtrue.s loc_1835B
0x182f0  ldarg.0
0x182f1  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x182f6  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x182fb  brfalse.s loc_1830B
0x182fd  ldc.i4.1
0x182fe  ldarg.0
0x182ff  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18304  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18309  bne.un.s loc_1835B
0x1830b  ldarg.0
0x1830c  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18311  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.Chart::get_PointWidth()
0x18316  brfalse.s loc_18349
0x18318  ldloc.3
0x18319  ldstr    aPointwidth// "PointWidth"
0x1831e  ldarg.0
0x1831f  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18324  callvirt instance int32 Microsoft.ReportingServices.ReportProcessing.Chart::get_PointWidth()
0x18329  conv.r8
0x1832a  ldc.r8   0.01
0x18333  mul
0x18334  stloc.s  5
0x18336  ldloca.s 5
0x18338  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1833d  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x18342  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x18347  br.s     loc_183A4
0x18349  ldloc.3
0x1834a  ldstr    aPointwidth// "PointWidth"
0x1834f  ldstr    a055// "0.55"
0x18354  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x18359  br.s     loc_183A4
0x1835b  ldloc.2
0x1835c  brfalse.s loc_1836B
0x1835e  ldloc.3
0x1835f  ldc.r4   3.0
0x18364  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderWidth(float32)
0x18369  br.s     loc_183A4
0x1836b  ldc.i4.3
0x1836c  ldarg.0
0x1836d  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18372  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18377  beq.s    loc_18387
0x18379  ldc.i4.7
0x1837a  ldarg.0
0x1837b  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18380  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18385  bne.un.s loc_183A4
0x18387  ldloc.3
0x18388  ldc.i4.5
0x18389  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.ChartDashStyle)
0x1838e  ldloc.3
0x1838f  ldc.r4   1.0
0x18394  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderWidth(float32)
0x18399  ldloc.3
0x1839a  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::get_Black()
0x1839f  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_BorderColor(valuetype [System.Drawing]System.Drawing.Color)
0x183a4  ldarg.0
0x183a5  call     instance bool Microsoft.ReportingServices.ReportRendering.DundasChart::get_IsCylinder()
0x183aa  brfalse.s loc_183BC
0x183ac  ldloc.3
0x183ad  ldstr    aDrawingstyle// "DrawingStyle"
0x183b2  ldstr    aCylinder// "Cylinder"
0x183b7  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x183bc  ldc.i4.8
0x183bd  ldarg.0
0x183be  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x183c3  callvirt instance valuetype ChartSubTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_SubType()
0x183c8  bne.un.s loc_183DA
0x183ca  ldloc.3
0x183cb  ldstr    aShowopenclose// "ShowOpenClose"
0x183d0  ldstr    aClose// "Close"
0x183d5  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Item(string, string)
0x183da  ldloc.3
0x183db  ldarg.0
0x183dc  ldnull
0x183dd  ldnull
0x183de  call     instance class [System.Drawing]System.Drawing.Font Microsoft.ReportingServices.ReportRendering.DundasChart::GetFont(class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues)
0x183e3  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_Font(class [System.Drawing]System.Drawing.Font)
0x183e8  ldloc.3
0x183e9  ldarg.0
0x183ea  ldnull
0x183eb  ldnull
0x183ec  call     instance valuetype [System.Drawing]System.Drawing.Color Microsoft.ReportingServices.ReportRendering.DundasChart::GetTextColor(class Microsoft.ReportingServices.ReportProcessing.Style styleDef, object[] styleAttributeValues)
0x183f1  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_FontColor(valuetype [System.Drawing]System.Drawing.Color)
0x183f6  ldloc.3
0x183f7  ldc.i4.0
0x183f8  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_ShowLabelAsValue(bool)
0x183fd  ldc.i4.5
0x183fe  ldarg.0
0x183ff  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x18404  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18409  bne.un.s loc_18419
0x1840b  ldloc.3
0x1840c  ldc.i4.4
0x1840d  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerSize(int32)
0x18412  ldloc.3
0x18413  ldc.i4.2
0x18414  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.DataPointAttributes::set_MarkerStyle(valuetype [DundasWebChart]Dundas.Charting.WebControl.MarkerStyle)
0x18419  ldarg.0
0x1841a  ldfld    class Microsoft.ReportingServices.ReportProcessing.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_chart
0x1841f  callvirt instance valuetype ChartTypes Microsoft.ReportingServices.ReportProcessing.Chart::get_Type()
0x18424  stloc.s  6
0x18426  ldloc.s  6
0x18428  ldc.i4.5
0x18429  beq.s    loc_18432
0x1842b  ldloc.s  6
0x1842d  ldc.i4.8
0x1842e  beq.s    loc_1843B
0x18430  br.s     loc_18442
0x18432  ldloc.3
0x18433  ldc.i4.2
0x18434  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_YValuesPerPoint(int32)
0x18439  br.s     loc_18442
0x1843b  ldloc.3
0x1843c  ldc.i4.4
0x1843d  callvirt instance void [DundasWebChart]Dundas.Charting.WebControl.Series::set_YValuesPerPoint(int32)
0x18442  ldarg.0
0x18443  ldfld    class [DundasWebChart]Dundas.Charting.WebControl.Chart Microsoft.ReportingServices.ReportRendering.DundasChart::m_dundasChart
0x18448  callvirt instance class [DundasWebChart]Dundas.Charting.WebControl.SeriesCollection [DundasWebChart]Dundas.Charting.WebControl.Chart::get_Series()
0x1844d  ldloc.3
0x1844e  callvirt instance int32 [DundasWebChart]Dundas.Charting.WebControl.SeriesCollection::Add(object)
0x18453  pop
0x18454  ldc.i4.1
0x18455  stloc.s  4
0x18457  ldc.i4.0
0x18458  stloc.s  7
0x1845a  br.s     loc_184BF
0x1845c  ldarg.0
0x1845d  ldloc.0
0x1845e  ldloc.s  7
0x18460  call     instance void Microsoft.ReportingServices.ReportRendering.DundasChart::HatchStyleIncrement(int32 seriesIndex, int32 categoryIndex)
0x18465  ldarg.0
0x18466  ldloca.s 4
0x18468  ldloc.2
0x18469  ldloc.3
0x1846a  ldarg.1
0x1846b  ldarg.3
0x1846c  ldloc.0
0x1846d  ldloc.s  7
0x1846f  callvirt instance class Microsoft.ReportingServices.ReportRendering.ChartDataPoint Microsoft.ReportingServices.ReportRendering.ChartDataPointCollection::get_Item(int32 series, int32 category)
0x18474  ldarg.0
0x18475  ldfld    class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.ReportRendering.DundasChart::m_categoryLabels
0x1847a  ldloc.s  7
0x1847c  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x18481  ldarg.0
0x18482  ldloc.0
0x18483  ldloc.s  7
0x18485  call     instance int32 Microsoft.ReportingServices.ReportRendering.DundasChart::EncodeDataPointID(int32 seriesIndex, int32 categoryIndex)
0x1848a  ldloc.0
0x1848b  call     instance void Microsoft.ReportingServices.ReportRendering.DundasChart::RenderDataPoint(bool& firstValidDataPointOfSeries, bool isLineChart, class [DundasWebChart]Dundas.Charting.WebControl.Series series, class Microsoft.ReportingServices.ReportRendering.ChartMember seriesHeader, class Microsoft.ReportingServices.ReportRendering.ChartDataPoint dataPoint, object axisLabel, int32 dataPointID, int32 seriesIndex)
0x18490  ldarg.0
0x18491  ldfld    bool Microsoft.ReportingServices.ReportRendering.DundasChart::m_populateSeriesIndexes
0x18496  brfalse.s loc_184A1
0x18498  ldloc.s  7
0x1849a  ldloc.1
0x1849b  ldc.i4.1
0x1849c  sub
0x1849d  ceq
0x1849f  br.s     loc_184A2
0x184a1  ldc.i4.0
0x184a2  ldloc.s  4
0x184a4  and
0x184a5  brfalse.s loc_184B9
0x184a7  ldarg.0
0x184a8  ldfld    class Microsoft.ReportingServices.ReportProcessing.IntList Microsoft.ReportingServices.ReportRendering.DundasChart::m_positiveSeriesIndexes
0x184ad  ldloc.0
0x184ae  box      [mscorlib]System.Int32
0x184b3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x184b8  pop
0x184b9  ldloc.s  7
0x184bb  ldc.i4.1
0x184bc  add
0x184bd  stloc.s  7
0x184bf  ldloc.s  7
0x184c1  ldloc.1
0x184c2  blt.s    loc_1845C
0x184c4  ret
```
