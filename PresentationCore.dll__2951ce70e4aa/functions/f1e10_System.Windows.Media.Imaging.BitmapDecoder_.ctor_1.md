# System.Windows.Media.Imaging.BitmapDecoder::.ctor_1

- ea: `0xf1e10`
- end: `0xf1f07`
- name: `System.Windows.Media.Imaging.BitmapDecoder::.ctor_1`
- size: `247`
- prototype: ``
- caller_count: `7`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0xf4230`
- `0xfacd0`
- `0xfadc0`
- `0xfb540`
- `0xfb950`
- `0xfcdf0`
- `0xfcf90`

## callees

- `0xa53c0`
- `0xf1e10`
- `0xf27f0`
- `0xf2910`
- `0xf2d50`
- `0xf2dd0`
- `0xfb020`
- `0x146e40`

## string_xrefs

- `0xf1e5a`: `bitmapUri`
- `0xf1ec7`: `Image_CantDealWithUri`

## pseudocode

```c

```

## disassembly

```asm
0xf1e10  ldarg.0
0xf1e11  ldc.i4.1
0xf1e12  stfld    bool System.Windows.Media.Imaging.BitmapDecoder::_shouldCacheDecoder
0xf1e17  ldarg.0
0xf1e18  newobj   instance void System.Windows.Media.UniqueEventHelper::.ctor()
0xf1e1d  stfld    class System.Windows.Media.UniqueEventHelper System.Windows.Media.Imaging.BitmapDecoder::_downloadEvent
0xf1e22  ldarg.0
0xf1e23  newobj   instance void class System.Windows.Media.UniqueEventHelper`1<class System.Windows.Media.Imaging.DownloadProgressEventArgs>::.ctor()
0xf1e28  stfld    class System.Windows.Media.UniqueEventHelper`1<class System.Windows.Media.Imaging.DownloadProgressEventArgs> System.Windows.Media.Imaging.BitmapDecoder::_progressEvent
0xf1e2d  ldarg.0
0xf1e2e  newobj   instance void class System.Windows.Media.UniqueEventHelper`1<class System.Windows.Media.ExceptionEventArgs>::.ctor()
0xf1e33  stfld    class System.Windows.Media.UniqueEventHelper`1<class System.Windows.Media.ExceptionEventArgs> System.Windows.Media.Imaging.BitmapDecoder::_failedEvent
0xf1e38  ldarg.0
0xf1e39  newobj   instance void [mscorlib]System.Object::.ctor()
0xf1e3e  stfld    object System.Windows.Media.Imaging.BitmapDecoder::_syncObject
0xf1e43  ldarg.0
0xf1e44  call     instance void [WindowsBase]System.Windows.Threading.DispatcherObject::.ctor()
0xf1e49  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xf1e4e  stloc.2
0xf1e4f  ldc.i4.0
0xf1e50  stloc.1
0xf1e51  ldarg.1
0xf1e52  ldnull
0xf1e53  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xf1e58  brfalse.s loc_F1E65
0xf1e5a  ldstr    aBitmapuri// "bitmapUri"
0xf1e5f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf1e64  throw
0xf1e65  ldarg.2
0xf1e66  ldc.i4.8
0xf1e67  and
0xf1e68  brfalse.s loc_F1E70
0xf1e6a  ldarg.1
0xf1e6b  call     void System.Windows.Media.Imaging.ImagingCache::RemoveFromDecoderCache(class [System]System.Uri uri)
0xf1e70  ldarg.1
0xf1e71  ldloca.s 2
0xf1e73  call     class System.Windows.Media.Imaging.BitmapDecoder System.Windows.Media.Imaging.BitmapDecoder::CheckCache(class [System]System.Uri uri, [out] valuetype [mscorlib]System.Guid& clsId)
0xf1e78  stloc.0
0xf1e79  ldloc.0
0xf1e7a  brfalse.s loc_F1E8A
0xf1e7c  ldarg.0
0xf1e7d  ldloc.0
0xf1e7e  callvirt instance class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapDecoder::get_InternalDecoder()
0xf1e83  stfld    class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapDecoder::_decoderHandle
0xf1e88  br.s     loc_F1EBC
0xf1e8a  ldarg.0
0xf1e8b  ldarg.1
0xf1e8c  ldnull
0xf1e8d  ldarg.3
0xf1e8e  ldloca.s 2
0xf1e90  ldloca.s 1
0xf1e92  ldarg.0
0xf1e93  ldflda   class [mscorlib]System.IO.Stream System.Windows.Media.Imaging.BitmapDecoder::_uriStream
0xf1e98  ldarg.0
0xf1e99  ldflda   class [mscorlib]System.IO.UnmanagedMemoryStream System.Windows.Media.Imaging.BitmapDecoder::_unmanagedMemoryStream
0xf1e9e  ldarg.0
0xf1e9f  ldflda   class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle System.Windows.Media.Imaging.BitmapDecoder::_safeFilehandle
0xf1ea4  call     class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapDecoder::SetupDecoderFromUriOrStream(class [System]System.Uri uri, class [mscorlib]System.IO.Stream stream, valuetype System.Windows.Media.Imaging.BitmapCacheOption cacheOption, [out] valuetype [mscorlib]System.Guid& clsId, [out] bool& isOriginalWritable, [out] class [mscorlib]System.IO.Stream& uriStream, [out] class [mscorlib]System.IO.UnmanagedMemoryStream& unmanagedMemoryStream, [out] class [mscorlib]Microsoft.Win32.SafeHandles.SafeFileHandle& safeFilehandle)
0xf1ea9  stfld    class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapDecoder::_decoderHandle
0xf1eae  ldarg.0
0xf1eaf  ldfld    class [mscorlib]System.IO.Stream System.Windows.Media.Imaging.BitmapDecoder::_uriStream
0xf1eb4  brtrue.s loc_F1EBC
0xf1eb6  ldarg.0
0xf1eb7  call     void [mscorlib]System.GC::SuppressFinalize(object)
0xf1ebc  ldloc.2
0xf1ebd  ldarg.s  4
0xf1ebf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0xf1ec4  brfalse.s loc_F1ED7
0xf1ec6  ldarg.1
0xf1ec7  ldstr    aImageCantdealw// "Image_CantDealWithUri"
0xf1ecc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0xf1ed1  newobj   instance void [WindowsBase]System.IO.FileFormatException::.ctor(class [System]System.Uri, string)
0xf1ed6  throw
0xf1ed7  ldarg.0
0xf1ed8  ldarg.1
0xf1ed9  stfld    class [System]System.Uri System.Windows.Media.Imaging.BitmapDecoder::_uri
0xf1ede  ldarg.0
0xf1edf  ldarg.2
0xf1ee0  stfld    valuetype System.Windows.Media.Imaging.BitmapCreateOptions System.Windows.Media.Imaging.BitmapDecoder::_createOptions
0xf1ee5  ldarg.0
0xf1ee6  ldarg.3
0xf1ee7  stfld    valuetype System.Windows.Media.Imaging.BitmapCacheOption System.Windows.Media.Imaging.BitmapDecoder::_cacheOption
0xf1eec  ldarg.0
0xf1eed  ldarg.0
0xf1eee  ldfld    class System.Windows.Media.SafeMILHandle System.Windows.Media.Imaging.BitmapDecoder::_decoderHandle
0xf1ef3  stfld    object System.Windows.Media.Imaging.BitmapDecoder::_syncObject
0xf1ef8  ldarg.0
0xf1ef9  ldloc.1
0xf1efa  stfld    bool System.Windows.Media.Imaging.BitmapDecoder::_isOriginalWritable
0xf1eff  ldarg.0
0xf1f00  ldloc.0
0xf1f01  call     instance void System.Windows.Media.Imaging.BitmapDecoder::Initialize(class System.Windows.Media.Imaging.BitmapDecoder decoder)
0xf1f06  ret
```
