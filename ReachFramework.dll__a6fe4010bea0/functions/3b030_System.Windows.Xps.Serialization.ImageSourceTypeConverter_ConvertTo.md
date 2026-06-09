# System.Windows.Xps.Serialization.ImageSourceTypeConverter::ConvertTo

- ea: `0x3b030`
- end: `0x3b20d`
- name: `System.Windows.Xps.Serialization.ImageSourceTypeConverter::ConvertTo`
- size: `477`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `service_task`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x1efa0`
- `0x20210`
- `0x266f0`
- `0x2e7e0`
- `0x2e7f0`
- `0x305d0`
- `0x305e0`
- `0x30600`
- `0x30640`
- `0x35890`
- `0x3b030`
- `0x3b220`
- `0x3b250`
- `0x3b290`
- `0x3b3a0`
- `0x3b400`
- `0x3b4b0`
- `0x3b620`
- `0x3b6b0`

## string_xrefs

- `0x3b118`: `ReachSerialization_NoImageService`

## pseudocode

```c

```

## disassembly

```asm
0x3b030  ldc.i4   0x13B6
0x3b035  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x3b03a  ldarg.1
0x3b03b  brtrue.s loc_3B048
0x3b03d  ldstr    aContext// "context"
0x3b042  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3b047  throw
0x3b048  ldarg.s  4
0x3b04a  call     bool System.Windows.Xps.Serialization.ImageSourceTypeConverter::IsSupportedType(class [mscorlib]System.Type type)
0x3b04f  brtrue.s loc_3B061
0x3b051  ldstr    aConverterConve_0// "Converter_ConvertToNotSupported"
0x3b056  call     string System.Windows.Xps.SR::Get(string id)
0x3b05b  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x3b060  throw
0x3b061  ldarg.3
0x3b062  castclass [PresentationCore]System.Windows.Media.Imaging.BitmapSource
0x3b067  stloc.0
0x3b068  ldloc.0
0x3b069  brtrue.s loc_3B091
0x3b06b  ldstr    aMustbeoftype// "MustBeOfType"
0x3b070  ldc.i4.2
0x3b071  newarr   [mscorlib]System.Object
0x3b076  dup
0x3b077  ldc.i4.0
0x3b078  ldstr    aValue// "value"
0x3b07d  stelem.ref
0x3b07e  dup
0x3b07f  ldc.i4.1
0x3b080  ldstr    aBitmapsource// "BitmapSource"
0x3b085  stelem.ref
0x3b086  call     string System.Windows.Xps.SR::Get(string id, object[] args)
0x3b08b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3b090  throw
0x3b091  ldarg.1
0x3b092  ldtoken  System.Windows.Xps.Serialization.XpsSerializationManager
0x3b097  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b09c  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3b0a1  castclass System.Windows.Xps.Serialization.PackageSerializationManager
0x3b0a6  stloc.1
0x3b0a7  ldarg.0
0x3b0a8  ldloc.1
0x3b0a9  ldloc.0
0x3b0aa  call     instance class [System]System.Uri System.Windows.Xps.Serialization.ImageSourceTypeConverter::GetBitmapSourceFromImageTable(class System.Windows.Xps.Serialization.PackageSerializationManager manager, class [PresentationCore]System.Windows.Media.Imaging.BitmapSource bitmapSource)
0x3b0af  stloc.2
0x3b0b0  ldloc.1
0x3b0b1  callvirt instance class System.Windows.Xps.Packaging.XpsResourcePolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_ResourcePolicy()
0x3b0b6  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [System]System.Uri> System.Windows.Xps.Packaging.XpsResourcePolicy::get_CurrentPageImageTable()
0x3b0bb  stloc.3
0x3b0bc  ldloc.2
0x3b0bd  ldnull
0x3b0be  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x3b0c3  brfalse.s loc_3B0F4
0x3b0c5  ldloc.2
0x3b0c6  callvirt instance int32 [mscorlib]System.Object::GetHashCode()
0x3b0cb  stloc.s  4
0x3b0cd  ldloc.3
0x3b0ce  ldloc.s  4
0x3b0d0  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [System]System.Uri>::ContainsKey(var<u1>)
0x3b0d5  brtrue   loc_3B201
0x3b0da  ldloc.1
0x3b0db  ldloc.2
0x3b0dc  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_ResourceRelationshipName()
0x3b0e1  callvirt instance void System.Windows.Xps.Serialization.PackageSerializationManager::AddRelationshipToCurrentPage(class [System]System.Uri targetUri, string relationshipName)
0x3b0e6  ldloc.3
0x3b0e7  ldloc.s  4
0x3b0e9  ldloc.2
0x3b0ea  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class [System]System.Uri>::Add(var<u1>, !!T0)
0x3b0ef  br       loc_3B201
0x3b0f4  ldloc.1
0x3b0f5  callvirt instance class System.Windows.Xps.Packaging.XpsResourcePolicy System.Windows.Xps.Serialization.PackageSerializationManager::get_ResourcePolicy()
0x3b0fa  stloc.s  5
0x3b0fc  ldloc.s  5
0x3b0fe  ldtoken  System.Windows.Xps.Serialization.XpsImageSerializationService
0x3b103  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b108  callvirt instance object [mscorlib]System.IServiceProvider::GetService(class [mscorlib]System.Type)
0x3b10d  castclass System.Windows.Xps.Serialization.XpsImageSerializationService
0x3b112  stloc.s  6
0x3b114  ldloc.s  6
0x3b116  brtrue.s loc_3B128
0x3b118  ldstr    aReachserializa_22// "ReachSerialization_NoImageService"
0x3b11d  call     string System.Windows.Xps.SR::Get(string id)
0x3b122  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x3b127  throw
0x3b128  ldloc.s  6
0x3b12a  ldloc.0
0x3b12b  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapEncoder System.Windows.Xps.Serialization.XpsImageSerializationService::GetEncoder(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource bitmapSource)
0x3b130  stloc.s  7
0x3b132  ldloc.s  7
0x3b134  call     string System.Windows.Xps.Serialization.ImageSourceTypeConverter::GetImageMimeType(class [PresentationCore]System.Windows.Media.Imaging.BitmapEncoder encoder)
0x3b139  stloc.s  8
0x3b13b  ldloc.s  6
0x3b13d  ldloc.0
0x3b13e  callvirt instance bool System.Windows.Xps.Serialization.XpsImageSerializationService::IsSupportedMimeType(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource bitmapSource)
0x3b143  stloc.s  9
0x3b145  ldloc.1
0x3b146  ldtoken  [PresentationCore]System.Windows.Media.Imaging.BitmapSource
0x3b14b  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b150  ldloc.s  8
0x3b152  callvirt instance class System.Windows.Xps.Serialization.XpsResourceStream System.Windows.Xps.Serialization.PackageSerializationManager::AcquireResourceStream(class [mscorlib]System.Type resourceType, string resourceID)
0x3b157  stloc.s  0xA
0x3b159  ldc.i4.0
0x3b15a  stloc.s  0xB
0x3b15c  ldloc.0
0x3b15d  isinst   [PresentationCore]System.Windows.Media.Imaging.BitmapFrame
0x3b162  stloc.s  0xC
0x3b164  ldloc.s  9
0x3b166  brfalse.s loc_3B1B5
0x3b168  ldloc.s  0xC
0x3b16a  brfalse.s loc_3B1B5
0x3b16c  ldloc.s  0xC
0x3b16e  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapDecoder [PresentationCore]System.Windows.Media.Imaging.BitmapFrame::get_Decoder()
0x3b173  brfalse.s loc_3B1B5
0x3b175  ldloc.s  0xC
0x3b177  callvirt instance class [PresentationCore]System.Windows.Media.Imaging.BitmapDecoder [PresentationCore]System.Windows.Media.Imaging.BitmapFrame::get_Decoder()
0x3b17c  stloc.s  0xD
0x3b17e  ldloc.s  0xD
0x3b180  callvirt instance string [mscorlib]System.Object::ToString()
0x3b185  newobj   instance void [System]System.Uri::.ctor(string)
0x3b18a  stloc.s  0xE
0x3b18c  ldloc.s  0xE
0x3b18e  call     class [mscorlib]System.IO.Stream [PresentationCore]MS.Internal.WpfWebRequestHelper::CreateRequestAndGetResponseStream(class [System]System.Uri)
0x3b193  stloc.s  0xF
0x3b195  ldloc.s  0xF
0x3b197  ldloc.s  0xA
0x3b199  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Serialization.XpsResourceStream::get_Stream()
0x3b19e  call     void System.Windows.Xps.Serialization.ImageSourceTypeConverter::CopyImageStream(class [mscorlib]System.IO.Stream sourceStream, class [mscorlib]System.IO.Stream destinationStream)
0x3b1a3  ldloc.s  0xF
0x3b1a5  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x3b1aa  ldc.i4.1
0x3b1ab  stloc.s  0xB
0x3b1ad  leave.s  loc_3B1B5
0x3b1af  pop
0x3b1b0  leave.s  loc_3B1B5
0x3b1b2  pop
0x3b1b3  leave.s  loc_3B1B5
0x3b1b5  ldloc.s  0xB
0x3b1b7  brtrue.s loc_3B1E1
0x3b1b9  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x3b1be  stloc.s  0x10
0x3b1c0  ldloc.0
0x3b1c1  ldloc.s  7
0x3b1c3  ldloc.s  0x10
0x3b1c5  call     void System.Windows.Xps.Serialization.ImageSourceTypeConverter::ReEncodeImage(class [PresentationCore]System.Windows.Media.Imaging.BitmapSource bitmapSource, class [PresentationCore]System.Windows.Media.Imaging.BitmapEncoder encoder, class [mscorlib]System.IO.Stream stream)
0x3b1ca  ldloc.s  0x10
0x3b1cc  ldc.i4.0
0x3b1cd  conv.i8
0x3b1ce  callvirt instance void [mscorlib]System.IO.Stream::set_Position(int64)
0x3b1d3  ldloc.s  0x10
0x3b1d5  ldloc.s  0xA
0x3b1d7  callvirt instance class [mscorlib]System.IO.Stream System.Windows.Xps.Serialization.XpsResourceStream::get_Stream()
0x3b1dc  call     void System.Windows.Xps.Serialization.ImageSourceTypeConverter::CopyImageStream(class [mscorlib]System.IO.Stream sourceStream, class [mscorlib]System.IO.Stream destinationStream)
0x3b1e1  ldloc.s  0xA
0x3b1e3  callvirt instance class [System]System.Uri System.Windows.Xps.Serialization.XpsResourceStream::get_Uri()
0x3b1e8  stloc.2
0x3b1e9  ldloc.1
0x3b1ea  ldtoken  [PresentationCore]System.Windows.Media.Imaging.BitmapSource
0x3b1ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3b1f4  callvirt instance void System.Windows.Xps.Serialization.PackageSerializationManager::ReleaseResourceStream(class [mscorlib]System.Type resourceType)
0x3b1f9  ldarg.0
0x3b1fa  ldloc.1
0x3b1fb  ldloc.2
0x3b1fc  call     instance void System.Windows.Xps.Serialization.ImageSourceTypeConverter::AddBitmapSourceToImageTables(class System.Windows.Xps.Serialization.PackageSerializationManager manager, class [System]System.Uri imageUri)
0x3b201  ldc.i4   0x13B7
0x3b206  call     void System.Windows.Xps.Serialization.Toolbox::EmitEvent(valuetype [WindowsBase]MS.Utility.EventTrace/Event evt)
0x3b20b  ldloc.2
0x3b20c  ret
```
