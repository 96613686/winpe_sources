# Microsoft.ReportingServices.Library.PowerPointExport::Export

- ea: `0x331a0`
- end: `0x333b9`
- name: `Microsoft.ReportingServices.Library.PowerPointExport::Export`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x6b8c0`

## callees

- `0x32620`
- `0x32680`
- `0x32700`
- `0x32780`
- `0x32870`
- `0x32990`
- `0x329f0`
- `0x32b00`
- `0x32b80`
- `0x32ba0`
- `0x32bc0`
- `0x32bd0`
- `0x32cc0`
- `0x32dc0`
- `0x32f90`
- `0x32fb0`
- `0x32fe0`
- `0x330a0`
- `0x331a0`
- `0x77360`

## string_xrefs

- `0x331b0`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x331c4`: `Microsoft.ReportingServices.Library.PowerPointExport.CrescentTemplate.pptx`
- `0x332ae`: `ItemPath={0},ReportServerUri={1},ViewMode={2},ReportSection={3},AllowSectionNavigation=False,ApplicationHost=PowerPoint,Fit=True,PreviewBar=False,BackgroundColor=White,Border=True,AllowEditViewMode=False,AllowFullScreenViewMode=False,Trace_HostApplication=Powerpoint`
- `0x332c7`: `CachedPreview`
- `0x332ed`: `Microsoft.ReportingServices.Library.PowerPointExport.NoPreview.png`

## pseudocode

```c

```

## disassembly

```asm
0x331a0  ldarg.3
0x331a1  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x331a6  stloc.0
0x331a7  ldarg.s  5
0x331a9  ldloc.0
0x331aa  ldstr    aPptx// "pptx"
0x331af  ldnull
0x331b0  ldstr    aApplicationVnd_0// "application/vnd.openxmlformats-officedo"...
0x331b5  ldc.i4.1
0x331b6  ldc.i4.0
0x331b7  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.CreateAndRegisterStream::Invoke(string, string, class [mscorlib]System.Text.Encoding, string, bool, valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.StreamOper)
0x331bc  stloc.1
0x331bd  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x331c2  stloc.2
0x331c3  ldloc.2
0x331c4  ldstr    aMicrosoftRepor_1// "Microsoft.ReportingServices.Library.Pow"...
0x331c9  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x331ce  stloc.s  6
0x331d0  ldloc.s  6
0x331d2  ldloc.1
0x331d3  ldc.i4   0x1000
0x331d8  call     int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.StreamSupport::CopyStreamUsingBuffer(class [mscorlib]System.IO.Stream, class [mscorlib]System.IO.Stream, int32)
0x331dd  pop
0x331de  leave.s  loc_331EC
0x331e0  ldloc.s  6
0x331e2  brfalse.s loc_331EB
0x331e4  ldloc.s  6
0x331e6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x331eb  endfinally
0x331ec  ldnull
0x331ed  stloc.3
0x331ee  ldnull
0x331ef  stloc.s  4
0x331f1  ldnull
0x331f2  stloc.s  5
0x331f4  ldarg.0
0x331f5  call     class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportPublishing.ReportArchive [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportPublishing.ReportArchive::Load(class [mscorlib]System.IO.Stream)
0x331fa  stloc.s  5
0x331fc  ldloc.s  5
0x331fe  callvirt instance class [mscorlib]System.IO.Stream [Microsoft.ReportingServices.ProcessingCore]Microsoft.Reporting.Packaging.Internal.ReportArchiveBase::GetReportDefinitionStream()
0x33203  call     class Microsoft.ReportingServices.Library.RdlxReport Microsoft.ReportingServices.Library.RdlxReport::Load(class [mscorlib]System.IO.Stream stream)
0x33208  stloc.s  7
0x3320a  ldloc.s  5
0x3320c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.IO.Stream> [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportPublishing.ReportArchive::GetSectionPreviewLocationsMap()
0x33211  stloc.s  4
0x33213  ldarg.1
0x33214  newobj   instance void Microsoft.ReportingServices.Library.SilverlightProperties::.ctor(string stringSource)
0x33219  stloc.s  8
0x3321b  ldloc.s  8
0x3321d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x33222  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x33227  callvirt instance void Microsoft.ReportingServices.Library.SilverlightProperties::set_StringUICulture(string value)
0x3322c  ldloc.s  8
0x3322e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x33233  callvirt instance string [mscorlib]System.Globalization.CultureInfo::get_Name()
0x33238  callvirt instance void Microsoft.ReportingServices.Library.SilverlightProperties::set_StringCulture(string value)
0x3323d  ldc.i4.1
0x3323e  stloc.s  9
0x33240  ldloc.1
0x33241  newobj   instance void Microsoft.ReportingServices.Library.Presentation::.ctor(class [mscorlib]System.IO.Stream file)
0x33246  stloc.s  0xA
0x33248  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::.ctor()
0x3324d  stloc.s  0xB
0x3324f  ldloc.s  7
0x33251  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ReportSection> Microsoft.ReportingServices.Library.RdlxReport::get_Sections()
0x33256  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.ReportingServices.Library.ReportSection>::GetEnumerator()
0x3325b  stloc.s  0xC
0x3325d  br       loc_33370
0x33262  ldloca.s 0xC
0x33264  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Library.ReportSection>::get_Current()
0x33269  stloc.s  0xD
0x3326b  newobj   instance void Microsoft.ReportingServices.Library.PersistStorage::.ctor()
0x33270  stloc.3
0x33271  ldnull
0x33272  stloc.s  0xE
0x33274  ldarg.s  4
0x33276  brfalse.s loc_33289
0x33278  ldarg.s  4
0x3327a  ldloc.s  0xD
0x3327c  callvirt instance string Microsoft.ReportingServices.Library.ReportSection::get_Name()
0x33281  ldloca.s 0xE
0x33283  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.IO.Stream>::TryGetValue(var<u1>, !!T0)
0x33288  pop
0x33289  ldloc.s  0xE
0x3328b  brtrue.s loc_332A7
0x3328d  ldloc.s  0xD
0x3328f  callvirt instance string Microsoft.ReportingServices.Library.ReportSection::get_PreviewId()
0x33294  brfalse.s loc_332A7
0x33296  ldloc.s  4
0x33298  ldloc.s  0xD
0x3329a  callvirt instance string Microsoft.ReportingServices.Library.ReportSection::get_PreviewId()
0x3329f  ldloca.s 0xE
0x332a1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.IO.Stream>::TryGetValue(var<u1>, !!T0)
0x332a6  pop
0x332a7  ldloc.s  8
0x332a9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x332ae  ldstr    aItempath0Repor// "ItemPath={0},ReportServerUri={1},ViewMo"...
0x332b3  ldc.i4.4
0x332b4  newarr   [mscorlib]System.Object
0x332b9  dup
0x332ba  ldc.i4.0
0x332bb  ldarg.3
0x332bc  stelem.ref
0x332bd  dup
0x332be  ldc.i4.1
0x332bf  ldarg.2
0x332c0  stelem.ref
0x332c1  dup
0x332c2  ldc.i4.2
0x332c3  ldloc.s  0xE
0x332c5  brfalse.s loc_332CE
0x332c7  ldstr    aCachedpreview// "CachedPreview"
0x332cc  br.s     loc_332D3
0x332ce  ldstr    aPresentation// "Presentation"
0x332d3  stelem.ref
0x332d4  dup
0x332d5  ldc.i4.3
0x332d6  ldloc.s  0xD
0x332d8  callvirt instance string Microsoft.ReportingServices.Library.ReportSection::get_Name()
0x332dd  stelem.ref
0x332de  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x332e3  callvirt instance void Microsoft.ReportingServices.Library.SilverlightProperties::set_StringInitParams(string value)
0x332e8  ldloc.s  0xE
0x332ea  brtrue.s loc_332F9
0x332ec  ldloc.2
0x332ed  ldstr    aMicrosoftRepor_2// "Microsoft.ReportingServices.Library.Pow"...
0x332f2  callvirt instance class [mscorlib]System.IO.Stream [mscorlib]System.Reflection.Assembly::GetManifestResourceStream(string)
0x332f7  stloc.s  0xE
0x332f9  ldloc.s  8
0x332fb  ldloc.s  0xE
0x332fd  callvirt instance void Microsoft.ReportingServices.Library.SilverlightProperties::LoadImage(class [mscorlib]System.IO.Stream image)
0x33302  ldloc.s  0xE
0x33304  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x33309  conv.i4
0x3330a  ldc.i4   0x100
0x3330f  add
0x33310  newobj   instance void Microsoft.ReportingServices.Common.SegmentedMemoryStream::.ctor(int32 capacity)
0x33315  stloc.s  0xF
0x33317  ldloc.s  8
0x33319  ldloc.s  0xF
0x3331b  callvirt instance void Microsoft.ReportingServices.Library.SilverlightProperties::Serialize(class [mscorlib]System.IO.Stream stream)
0x33320  ldloc.3
0x33321  ldloc.s  0xF
0x33323  callvirt instance void Microsoft.ReportingServices.Library.PersistStorage::SetContent(class [mscorlib]System.IO.Stream data)
0x33328  leave.s  loc_33336
0x3332a  ldloc.s  0xF
0x3332c  brfalse.s loc_33335
0x3332e  ldloc.s  0xF
0x33330  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x33335  endfinally
0x33336  ldloc.s  9
0x33338  ldc.i4.1
0x33339  bne.un.s loc_33352
0x3333b  ldloc.s  0xA
0x3333d  ldloc.s  9
0x3333f  ldloc.3
0x33340  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.PersistStorage::GetData()
0x33345  ldloc.s  0xE
0x33347  ldloca.s 0x10
0x33349  ldloca.s 0x11
0x3334b  callvirt instance void Microsoft.ReportingServices.Library.Presentation::UpdateSlide(int32 slideNum, class [mscorlib]System.IO.Stream activeXData, class [mscorlib]System.IO.Stream previewImage, [out] class [WindowsBase]System.IO.Packaging.PackagePart& activeXBin, [out] class [WindowsBase]System.IO.Packaging.PackagePart& image)
0x33350  br.s     loc_3336A
0x33352  ldloc.s  0xB
0x33354  ldloc.s  0xA
0x33356  ldloc.s  9
0x33358  ldloc.3
0x33359  callvirt instance class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.PersistStorage::GetData()
0x3335e  ldloc.s  0xE
0x33360  callvirt instance class [System]System.Uri Microsoft.ReportingServices.Library.Presentation::AddSlide(int32 slideNum, class [mscorlib]System.IO.Stream activeXData, class [mscorlib]System.IO.Stream previewImage)
0x33365  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri>::Add(var<u1>)
0x3336a  ldloc.s  9
0x3336c  ldc.i4.1
0x3336d  add
0x3336e  stloc.s  9
0x33370  ldloca.s 0xC
0x33372  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Library.ReportSection>::MoveNext()
0x33377  brtrue   loc_33262
0x3337c  leave.s  loc_3338C
0x3337e  ldloca.s 0xC
0x33380  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.ReportingServices.Library.ReportSection>
0x33386  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3338b  endfinally
0x3338c  ldloc.s  0xA
0x3338e  ldloc.s  0xB
0x33390  callvirt instance void Microsoft.ReportingServices.Library.Presentation::AddSlidesToPresentation(class [mscorlib]System.Collections.Generic.List`1<class [System]System.Uri> slides)
0x33395  leave.s  loc_333B8
0x33397  ldloc.s  0xA
0x33399  brfalse.s loc_333A2
0x3339b  ldloc.s  0xA
0x3339d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x333a2  endfinally
0x333a3  ldloc.3
0x333a4  brfalse.s loc_333AC
0x333a6  ldloc.3
0x333a7  callvirt instance void Microsoft.ReportingServices.Library.PersistStorage::Close()
0x333ac  ldloc.s  5
0x333ae  brfalse.s loc_333B7
0x333b0  ldloc.s  5
0x333b2  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportPublishing.ReportArchive::Close()
0x333b7  endfinally
0x333b8  ret
```
