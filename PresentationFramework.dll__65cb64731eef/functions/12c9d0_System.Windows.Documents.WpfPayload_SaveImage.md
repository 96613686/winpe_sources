# System.Windows.Documents.WpfPayload::SaveImage

- ea: `0x12c9d0`
- end: `0x12caa9`
- name: `System.Windows.Documents.WpfPayload::SaveImage`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x107810`

## callees

- `0x12c8e0`
- `0x12c9d0`
- `0x12cca0`
- `0x12d190`
- `0x12d1e0`
- `0x12d280`
- `0x12d2a0`

## string_xrefs

- `0x12ca1f`: `<Span xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"><InlineUIContainer><Image Width="`
- `0x12ca53`: `" ><Image.Source><BitmapImage CacheOption="OnLoad" UriSource="`

## pseudocode

```c

```

## disassembly

```asm
0x12c9d0  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x12c9d5  stloc.0
0x12c9d6  ldnull
0x12c9d7  newobj   instance void System.Windows.Documents.WpfPayload::.ctor(class [WindowsBase]System.IO.Packaging.Package package)
0x12c9dc  stloc.1
0x12c9dd  ldloc.1
0x12c9de  ldloc.0
0x12c9df  callvirt instance class [WindowsBase]System.IO.Packaging.Package System.Windows.Documents.WpfPayload::CreatePackage(class [mscorlib]System.IO.Stream stream)
0x12c9e4  stloc.2
0x12c9e5  ldc.i4.0
0x12c9e6  stloc.3
0x12c9e7  ldloc.3
0x12c9e8  ldarg.1
0x12c9e9  call     string System.Windows.Documents.WpfPayload::GetImageName(int32 imageIndex, string imageContentType)
0x12c9ee  call     string System.Windows.Documents.WpfPayload::GetImageReference(string imageName)
0x12c9f3  stloc.s  4
0x12c9f5  ldloc.1
0x12c9f6  callvirt instance class [WindowsBase]System.IO.Packaging.PackagePart System.Windows.Documents.WpfPayload::CreateWpfEntryPart()
0x12c9fb  stloc.s  5
0x12c9fd  ldloc.s  5
0x12c9ff  callvirt instance class [mscorlib]System.IO.Stream [WindowsBase]System.IO.Packaging.PackagePart::GetStream()
0x12ca04  stloc.s  6
0x12ca06  ldloc.s  6
0x12ca08  stloc.s  7
0x12ca0a  ldloc.s  6
0x12ca0c  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x12ca11  stloc.s  8
0x12ca13  ldloc.s  8
0x12ca15  stloc.s  9
0x12ca17  ldc.i4.7
0x12ca18  newarr   [mscorlib]System.String
0x12ca1d  dup
0x12ca1e  ldc.i4.0
0x12ca1f  ldstr    aSpanXmlnsHttpS_0// "<Span xmlns=\"http://schemas.microsoft."...
0x12ca24  stelem.ref
0x12ca25  dup
0x12ca26  ldc.i4.1
0x12ca27  ldarg.0
0x12ca28  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Width()
0x12ca2d  stloc.s  0xB
0x12ca2f  ldloca.s 0xB
0x12ca31  call     instance string [mscorlib]System.Double::ToString()
0x12ca36  stelem.ref
0x12ca37  dup
0x12ca38  ldc.i4.2
0x12ca39  ldstr    aHeight_2// "\" Height=\""
0x12ca3e  stelem.ref
0x12ca3f  dup
0x12ca40  ldc.i4.3
0x12ca41  ldarg.0
0x12ca42  callvirt instance float64 [PresentationCore]System.Windows.Media.ImageSource::get_Height()
0x12ca47  stloc.s  0xB
0x12ca49  ldloca.s 0xB
0x12ca4b  call     instance string [mscorlib]System.Double::ToString()
0x12ca50  stelem.ref
0x12ca51  dup
0x12ca52  ldc.i4.4
0x12ca53  ldstr    aImageSourceBit// "\" ><Image.Source><BitmapImage CacheOpt"...
0x12ca58  stelem.ref
0x12ca59  dup
0x12ca5a  ldc.i4.5
0x12ca5b  ldloc.s  4
0x12ca5d  stelem.ref
0x12ca5e  dup
0x12ca5f  ldc.i4.6
0x12ca60  ldstr    aImageSourceIma// "\"/></Image.Source></Image></InlineUICo"...
0x12ca65  stelem.ref
0x12ca66  call     string [mscorlib]System.String::Concat(string[])
0x12ca6b  stloc.s  0xA
0x12ca6d  ldloc.s  8
0x12ca6f  ldloc.s  0xA
0x12ca71  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x12ca76  leave.s  loc_12CA90
0x12ca78  ldloc.s  9
0x12ca7a  brfalse.s loc_12CA83
0x12ca7c  ldloc.s  9
0x12ca7e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12ca83  endfinally
0x12ca84  ldloc.s  7
0x12ca86  brfalse.s loc_12CA8F
0x12ca88  ldloc.s  7
0x12ca8a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12ca8f  endfinally
0x12ca90  ldloc.1
0x12ca91  ldloc.s  5
0x12ca93  ldarg.0
0x12ca94  ldarg.1
0x12ca95  ldloc.3
0x12ca96  callvirt instance void System.Windows.Documents.WpfPayload::CreateImagePart(class [WindowsBase]System.IO.Packaging.PackagePart sourcePart, class [PresentationCore]System.Windows.Media.Imaging.BitmapSource imageSource, string imageContentType, int32 imageIndex)
0x12ca9b  leave.s  loc_12CAA7
0x12ca9d  ldloc.2
0x12ca9e  brfalse.s loc_12CAA6
0x12caa0  ldloc.2
0x12caa1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x12caa6  endfinally
0x12caa7  ldloc.0
0x12caa8  ret
```
