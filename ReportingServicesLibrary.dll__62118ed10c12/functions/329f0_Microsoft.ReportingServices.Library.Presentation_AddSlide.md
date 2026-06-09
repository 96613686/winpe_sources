# Microsoft.ReportingServices.Library.Presentation::AddSlide

- ea: `0x329f0`
- end: `0x32afa`
- name: `Microsoft.ReportingServices.Library.Presentation::AddSlide`
- size: `266`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x331a0`

## callees

- `0x32800`
- `0x32990`

## string_xrefs

- `0x329fe`: `/ppt/activeX/activeX1.xml`
- `0x32a08`: `/ppt/activeX/activeX{0}.xml`
- `0x32a26`: `http://schemas.microsoft.com/office/2006/relationships/activeXControlBinary`
- `0x32a5f`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/image`
- `0x32ae4`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/image`
- `0x32a70`: `/ppt/slides/slide1.xml`
- `0x32a7a`: `/ppt/slides/slide{0}.xml`
- `0x32a97`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/vmlDrawing`
- `0x32aaf`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/control`
- `0x32ac0`: `../slideLayouts/slideLayout2.xml`
- `0x32acc`: `http://schemas.openxmlformats.org/officeDocument/2006/relationships/slideLayout`

## pseudocode

```c

```

## disassembly

```asm
0x329f0  ldarg.0
0x329f1  ldarg.1
0x329f2  ldarg.2
0x329f3  ldarg.3
0x329f4  ldloca.s 0
0x329f6  ldloca.s 1
0x329f8  call     instance void Microsoft.ReportingServices.Library.Presentation::UpdateSlide(int32 slideNum, class [mscorlib]System.IO.Stream activeXData, class [mscorlib]System.IO.Stream previewImage, [out] class [WindowsBase]System.IO.Packaging.PackagePart& activeXBin, [out] class [WindowsBase]System.IO.Packaging.PackagePart& image)
0x329fd  ldarg.0
0x329fe  ldstr    aPptActivexActi_0// "/ppt/activeX/activeX1.xml"
0x32a03  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32a08  ldstr    aPptActivexActi_1// "/ppt/activeX/activeX{0}.xml"
0x32a0d  ldarg.1
0x32a0e  box      [mscorlib]System.Int32
0x32a13  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x32a18  call     instance class [WindowsBase]System.IO.Packaging.PackagePart Microsoft.ReportingServices.Library.Presentation::CopyPart(string src, string dest)
0x32a1d  stloc.2
0x32a1e  ldloc.2
0x32a1f  ldloc.0
0x32a20  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32a25  ldc.i4.0
0x32a26  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/office/200"...
0x32a2b  ldstr    aRid1// "rId1"
0x32a30  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32a35  pop
0x32a36  ldarg.0
0x32a37  ldstr    aPptDrawingsVml// "/ppt/drawings/vmlDrawing1.vml"
0x32a3c  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32a41  ldstr    aPptDrawingsVml_0// "/ppt/drawings/vmlDrawing{0}.vml"
0x32a46  ldarg.1
0x32a47  box      [mscorlib]System.Int32
0x32a4c  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x32a51  call     instance class [WindowsBase]System.IO.Packaging.PackagePart Microsoft.ReportingServices.Library.Presentation::CopyPart(string src, string dest)
0x32a56  stloc.3
0x32a57  ldloc.3
0x32a58  ldloc.1
0x32a59  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32a5e  ldc.i4.0
0x32a5f  ldstr    aHttpSchemasOpe_2// "http://schemas.openxmlformats.org/offic"...
0x32a64  ldstr    aRid1// "rId1"
0x32a69  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32a6e  pop
0x32a6f  ldarg.0
0x32a70  ldstr    aPptSlidesSlide// "/ppt/slides/slide1.xml"
0x32a75  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x32a7a  ldstr    aPptSlidesSlide_0// "/ppt/slides/slide{0}.xml"
0x32a7f  ldarg.1
0x32a80  box      [mscorlib]System.Int32
0x32a85  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object)
0x32a8a  call     instance class [WindowsBase]System.IO.Packaging.PackagePart Microsoft.ReportingServices.Library.Presentation::CopyPart(string src, string dest)
0x32a8f  dup
0x32a90  ldloc.3
0x32a91  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32a96  ldc.i4.0
0x32a97  ldstr    aHttpSchemasOpe_3// "http://schemas.openxmlformats.org/offic"...
0x32a9c  ldstr    aRid1// "rId1"
0x32aa1  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32aa6  pop
0x32aa7  dup
0x32aa8  ldloc.2
0x32aa9  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32aae  ldc.i4.0
0x32aaf  ldstr    aHttpSchemasOpe_4// "http://schemas.openxmlformats.org/offic"...
0x32ab4  ldstr    aRid2// "rId2"
0x32ab9  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32abe  pop
0x32abf  dup
0x32ac0  ldstr    aSlidelayoutsSl// "../slideLayouts/slideLayout2.xml"
0x32ac5  ldc.i4.2
0x32ac6  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x32acb  ldc.i4.0
0x32acc  ldstr    aHttpSchemasOpe_5// "http://schemas.openxmlformats.org/offic"...
0x32ad1  ldstr    aRid3// "rId3"
0x32ad6  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32adb  pop
0x32adc  dup
0x32add  ldloc.1
0x32ade  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32ae3  ldc.i4.0
0x32ae4  ldstr    aHttpSchemasOpe_2// "http://schemas.openxmlformats.org/offic"...
0x32ae9  ldstr    aRid4// "rId4"
0x32aee  callvirt instance class [WindowsBase]System.IO.Packaging.PackageRelationship [WindowsBase]System.IO.Packaging.PackagePart::CreateRelationship(class [System]System.Uri, valuetype [WindowsBase]System.IO.Packaging.TargetMode, string, string)
0x32af3  pop
0x32af4  callvirt instance class [System]System.Uri [WindowsBase]System.IO.Packaging.PackagePart::get_Uri()
0x32af9  ret
```
