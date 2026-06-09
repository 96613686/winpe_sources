# System.Windows.Interop.DocObjHost::MS.Internal.Progressivity.IByteRangeDownloaderService.InitializeByteRangeDownloader

- ea: `0x1cc310`
- end: `0x1cc396`
- name: `System.Windows.Interop.DocObjHost::MS.Internal.Progressivity.IByteRangeDownloaderService.InitializeByteRangeDownloader`
- size: `134`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x38c40`
- `0x1cc310`

## string_xrefs

- `0x1cc321`: `tempFile`
- `0x1cc37a`: `tempFile`
- `0x1cc370`: `InvalidTempFileName`

## pseudocode

```c

```

## disassembly

```asm
0x1cc310  ldarg.1
0x1cc311  brtrue.s loc_1CC31E
0x1cc313  ldstr    aUrl// "url"
0x1cc318  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cc31d  throw
0x1cc31e  ldarg.2
0x1cc31f  brtrue.s loc_1CC32C
0x1cc321  ldstr    aTempfile// "tempFile"
0x1cc326  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cc32b  throw
0x1cc32c  ldarg.3
0x1cc32d  brtrue.s loc_1CC33A
0x1cc32f  ldstr    aEventhandle// "eventHandle"
0x1cc334  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1cc339  throw
0x1cc33a  ldarg.3
0x1cc33b  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x1cc340  brtrue.s loc_1CC34A
0x1cc342  ldarg.3
0x1cc343  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsClosed()
0x1cc348  brfalse.s loc_1CC35F
0x1cc34a  ldstr    aInvalideventha// "InvalidEventHandle"
0x1cc34f  call     string System.Windows.SR::Get(string id)
0x1cc354  ldstr    aEventhandle// "eventHandle"
0x1cc359  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1cc35e  throw
0x1cc35f  ldarg.1
0x1cc360  ldc.i4.1
0x1cc361  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1cc366  stloc.0
0x1cc367  ldarg.2
0x1cc368  callvirt instance int32 [mscorlib]System.String::get_Length()
0x1cc36d  ldc.i4.0
0x1cc36e  bgt.s    loc_1CC385
0x1cc370  ldstr    aInvalidtempfil// "InvalidTempFileName"
0x1cc375  call     string System.Windows.SR::Get(string id)
0x1cc37a  ldstr    aTempfile// "tempFile"
0x1cc37f  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1cc384  throw
0x1cc385  ldloc.0
0x1cc386  ldarg.2
0x1cc387  ldarg.3
0x1cc388  newobj   instance void [PresentationCore]MS.Internal.IO.Packaging.ByteRangeDownloader::.ctor(class [System]System.Uri, string, class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle)
0x1cc38d  stloc.1
0x1cc38e  ldarg.0
0x1cc38f  ldloc.1
0x1cc390  stfld    object System.Windows.Interop.DocObjHost::_downloader
0x1cc395  ret
```
