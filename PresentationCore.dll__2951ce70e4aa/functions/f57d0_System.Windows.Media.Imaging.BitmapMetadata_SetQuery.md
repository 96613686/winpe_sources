# System.Windows.Media.Imaging.BitmapMetadata::SetQuery

- ea: `0xf57d0`
- end: `0xf58e1`
- name: `System.Windows.Media.Imaging.BitmapMetadata::SetQuery`
- size: `273`
- prototype: ``
- caller_count: `12`
- callee_count: `8`
- tags: ``

## callers

- `0xf5ac0`
- `0xf5b10`
- `0xf5b60`
- `0xf5bb0`
- `0xf5be0`
- `0xf5c40`
- `0xf5cd0`
- `0xf5d00`
- `0xf5d30`
- `0xf5d60`
- `0xf5d90`
- `0xf5dc0`

## callees

- `0xf57d0`
- `0xf5e80`
- `0xfbce0`
- `0xfc280`
- `0xfca40`
- `0x106440`
- `0x146e40`
- `0x1537a0`

## string_xrefs

- `0xf57fa`: `Image_MetadataReadOnly`

## pseudocode

```c

```

## disassembly

```asm
0xf57d0  ldarg.0
0xf57d1  call     instance void [WindowsBase]System.Windows.Freezable::WritePreamble()
0xf57d6  ldarg.1
0xf57d7  brtrue.s loc_F57E4
0xf57d9  ldstr    aQuery// "query"
0xf57de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf57e3  throw
0xf57e4  ldarg.2
0xf57e5  brtrue.s loc_F57F2
0xf57e7  ldstr    aValue// "value"
0xf57ec  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf57f1  throw
0xf57f2  ldarg.0
0xf57f3  ldfld    bool System.Windows.Media.Imaging.BitmapMetadata::_readOnly
0xf57f8  brfalse.s loc_F580A
0xf57fa  ldstr    aImageMetadatar// "Image_MetadataReadOnly"
0xf57ff  call     string MS.Internal.PresentationCore.SR::Get(string id)
0xf5804  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf5809  throw
0xf580a  ldarg.0
0xf580b  ldarg.1
0xf580c  stfld    string System.Windows.Media.Imaging.BitmapMetadata::_setQueryString
0xf5811  ldarg.0
0xf5812  ldarg.2
0xf5813  stfld    object System.Windows.Media.Imaging.BitmapMetadata::_setQueryValue
0xf5818  ldarg.0
0xf5819  call     instance void System.Windows.Media.Imaging.BitmapMetadata::EnsureBitmapMetadata()
0xf581e  ldloca.s 7
0xf5820  initobj  System.Windows.Media.Imaging.PROPVARIANT
0xf5826  ldloca.s 7
0xf5828  ldarg.2
0xf5829  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Init(object value)
0xf582e  ldloca.s 7
0xf5830  call     instance bool System.Windows.Media.Imaging.PROPVARIANT::get_RequiresSyncObject()
0xf5835  brfalse.s loc_F589E
0xf5837  ldarg.2
0xf5838  isinst   System.Windows.Media.Imaging.BitmapMetadata
0xf583d  stloc.0
0xf583e  ldloc.0
0xf583f  ldnull
0xf5840  cgt.un
0xf5842  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool)
0xf5847  ldloc.0
0xf5848  callvirt instance void [WindowsBase]System.Windows.Threading.DispatcherObject::VerifyAccess()
0xf584d  ldloc.0
0xf584e  ldfld    object System.Windows.Media.Imaging.BitmapMetadata::_syncObject
0xf5853  stloc.3
0xf5854  ldc.i4.0
0xf5855  stloc.s  6
0xf5857  ldloc.3
0xf5858  ldloca.s 6
0xf585a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf585f  ldarg.0
0xf5860  ldfld    object System.Windows.Media.Imaging.BitmapMetadata::_syncObject
0xf5865  stloc.2
0xf5866  ldc.i4.0
0xf5867  stloc.s  5
0xf5869  ldloc.2
0xf586a  ldloca.s 5
0xf586c  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf5871  ldarg.0
0xf5872  ldfld    class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapMetadata::_metadataHandle
0xf5877  ldarg.1
0xf5878  ldloca.s 7
0xf587a  call     int32 WICMetadataQueryWriter::SetMetadataByName(class System.Windows.Media.SafeMILHandle THIS_PTR, [out] [hasfieldmarshal] string wzName, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xf587f  call     void MS.Internal.HRESULT::Check(int32 hr)
0xf5884  leave.s  loc_F58DA
0xf5886  ldloc.s  5
0xf5888  brfalse.s loc_F5890
0xf588a  ldloc.2
0xf588b  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf5890  endfinally
0xf5891  leave.s  loc_F589E
0xf5893  ldloc.s  6
0xf5895  brfalse.s loc_F589D
0xf5897  ldloc.3
0xf5898  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf589d  endfinally
0xf589e  ldarg.0
0xf589f  ldfld    object System.Windows.Media.Imaging.BitmapMetadata::_syncObject
0xf58a4  stloc.1
0xf58a5  ldc.i4.0
0xf58a6  stloc.s  4
0xf58a8  ldloc.1
0xf58a9  ldloca.s 4
0xf58ab  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xf58b0  ldarg.0
0xf58b1  ldfld    class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapMetadata::_metadataHandle
0xf58b6  ldarg.1
0xf58b7  ldloca.s 7
0xf58b9  call     int32 WICMetadataQueryWriter::SetMetadataByName(class System.Windows.Media.SafeMILHandle THIS_PTR, [out] [hasfieldmarshal] string wzName, valuetype System.Windows.Media.Imaging.PROPVARIANT& propValue)
0xf58be  call     void MS.Internal.HRESULT::Check(int32 hr)
0xf58c3  leave.s  loc_F58DA
0xf58c5  ldloc.s  4
0xf58c7  brfalse.s loc_F58CF
0xf58c9  ldloc.1
0xf58ca  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xf58cf  endfinally
0xf58d0  leave.s  loc_F58DA
0xf58d2  ldloca.s 7
0xf58d4  call     instance void System.Windows.Media.Imaging.PROPVARIANT::Clear()
0xf58d9  endfinally
0xf58da  ldarg.0
0xf58db  call     instance void [WindowsBase]System.Windows.Freezable::WritePostscript()
0xf58e0  ret
```
