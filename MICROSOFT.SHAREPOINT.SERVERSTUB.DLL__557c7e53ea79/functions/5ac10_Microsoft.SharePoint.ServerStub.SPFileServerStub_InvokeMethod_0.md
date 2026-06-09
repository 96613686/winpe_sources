# Microsoft.SharePoint.ServerStub.SPFileServerStub::InvokeMethod_0

- ea: `0x5ac10`
- end: `0x5b282`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::InvokeMethod_0`
- size: `1650`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callees

- `0x5a720`
- `0x5a740`
- `0x5a760`
- `0x5a780`
- `0x5a7a0`
- `0x5a7e0`
- `0x5a820`
- `0x5a850`
- `0x5a880`
- `0x5a8c0`
- `0x5a900`
- `0x5a920`
- `0x5a940`
- `0x5a950`
- `0x5a970`
- `0x5a990`
- `0x5a9b0`
- `0x5a9c0`
- `0x5a9d0`
- `0x5a9f0`
- `0x5aa10`
- `0x5aa20`
- `0x5aa30`
- `0x5aa60`
- `0x5aa80`
- `0x5aaa0`
- `0x5aac0`
- `0x5aae0`
- `0x5ab00`
- `0x5ab40`
- `0x5ab50`
- `0x5ab80`
- `0x5abb0`
- `0x5abe0`
- `0x5ac10`

## string_xrefs

- `0x5adcb`: `Update`
- `0x5b1ed`: `Update`
- `0x5ad22`: `DeleteObject`
- `0x5b07b`: `DeleteObject`
- `0x5acee`: `OpenBinaryStream`
- `0x5b00d`: `OpenBinaryStream`
- `0x5ac7f`: `GetPreAuthorizedAccessUrl`
- `0x5af0f`: `GetPreAuthorizedAccessUrl`
- `0x5ac97`: `GetImagePreviewUri`
- `0x5af45`: `GetImagePreviewUri`
- `0x5acfb`: `OpenBinaryStreamWithOptions`
- `0x5b028`: `OpenBinaryStreamWithOptions`
- `0x5adbe`: `UpdateVirusInfo`
- `0x5b1d1`: `UpdateVirusInfo`
- `0x5add8`: `MoveTo`
- `0x5b209`: `MoveTo`
- `0x5ade5`: `MoveToUsingPath`
- `0x5b225`: `MoveToUsingPath`
- `0x5adf2`: `CopyTo`
- `0x5b241`: `CopyTo`
- `0x5adff`: `CopyToUsingPath`
- `0x5b25d`: `CopyToUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x5ac10  ldarg.s  4
0x5ac12  brtrue.s loc_5AC1F
0x5ac14  ldstr    aProxycontext// "proxyContext"
0x5ac19  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ac1e  throw
0x5ac1f  ldarg.1
0x5ac20  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x5ac25  stloc.0
0x5ac26  ldloc.0
0x5ac27  brtrue.s loc_5AC34
0x5ac29  ldstr    aTarget// "target"
0x5ac2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ac33  throw
0x5ac34  ldarg.0
0x5ac35  ldarg.2
0x5ac36  ldarg.s  4
0x5ac38  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ac3d  starg.s  2
0x5ac3f  ldarg.2
0x5ac40  dup
0x5ac41  stloc.1
0x5ac42  brfalse  loc_5B274
0x5ac47  volatile.
0x5ac49  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001024-1
0x5ac4e  brtrue   loc_5AE12
0x5ac53  ldc.i4.s 0x22
0x5ac55  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5ac5a  dup
0x5ac5b  ldstr    aAddactivities// "AddActivities"
0x5ac60  ldc.i4.0
0x5ac61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ac66  dup
0x5ac67  ldstr    aAddclientactiv// "AddClientActivities"
0x5ac6c  ldc.i4.1
0x5ac6d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ac72  dup
0x5ac73  ldstr    aGetlimitedwebp// "GetLimitedWebPartManager"
0x5ac78  ldc.i4.2
0x5ac79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ac7e  dup
0x5ac7f  ldstr    aGetpreauthoriz// "GetPreAuthorizedAccessUrl"
0x5ac84  ldc.i4.3
0x5ac85  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ac8a  dup
0x5ac8b  ldstr    aGetimageprevie// "GetImagePreviewUrl"
0x5ac90  ldc.i4.4
0x5ac91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ac96  dup
0x5ac97  ldstr    aGetimageprevie_0// "GetImagePreviewUri"
0x5ac9c  ldc.i4.5
0x5ac9d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5aca2  dup
0x5aca3  ldstr    aStartupload// "StartUpload"
0x5aca8  ldc.i4.6
0x5aca9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5acae  dup
0x5acaf  ldstr    aStartuploadfil// "StartUploadFile"
0x5acb4  ldc.i4.7
0x5acb5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5acba  dup
0x5acbb  ldstr    aContinueupload// "ContinueUpload"
0x5acc0  ldc.i4.8
0x5acc1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5acc6  dup
0x5acc7  ldstr    aFinishupload// "FinishUpload"
0x5accc  ldc.i4.s 9
0x5acce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5acd3  dup
0x5acd4  ldstr    aCancelupload// "CancelUpload"
0x5acd9  ldc.i4.s 0xA
0x5acdb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ace0  dup
0x5ace1  ldstr    aGetuploadstatu// "GetUploadStatus"
0x5ace6  ldc.i4.s 0xB
0x5ace8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5aced  dup
0x5acee  ldstr    aOpenbinarystre// "OpenBinaryStream"
0x5acf3  ldc.i4.s 0xC
0x5acf5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5acfa  dup
0x5acfb  ldstr    aOpenbinarystre_0// "OpenBinaryStreamWithOptions"
0x5ad00  ldc.i4.s 0xD
0x5ad02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad07  dup
0x5ad08  ldstr    aSavebinarystre// "SaveBinaryStream"
0x5ad0d  ldc.i4.s 0xE
0x5ad0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad14  dup
0x5ad15  ldstr    aSavebinary// "SaveBinary"
0x5ad1a  ldc.i4.s 0xF
0x5ad1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad21  dup
0x5ad22  ldstr    aDeleteobject// "DeleteObject"
0x5ad27  ldc.i4.s 0x10
0x5ad29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad2e  dup
0x5ad2f  ldstr    aRecycle// "Recycle"
0x5ad34  ldc.i4.s 0x11
0x5ad36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad3b  dup
0x5ad3c  ldstr    aRecyclewitheta// "RecycleWithETag"
0x5ad41  ldc.i4.s 0x12
0x5ad43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad48  dup
0x5ad49  ldstr    aExecutecobaltr// "ExecuteCobaltRequest"
0x5ad4e  ldc.i4.s 0x13
0x5ad50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad55  dup
0x5ad56  ldstr    aCheckout_1// "CheckOut"
0x5ad5b  ldc.i4.s 0x14
0x5ad5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad62  dup
0x5ad63  ldstr    aUndocheckout// "UndoCheckOut"
0x5ad68  ldc.i4.s 0x15
0x5ad6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad6f  dup
0x5ad70  ldstr    aCheckin_1// "CheckIn"
0x5ad75  ldc.i4.s 0x16
0x5ad77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad7c  dup
0x5ad7d  ldstr    aPublish// "Publish"
0x5ad82  ldc.i4.s 0x17
0x5ad84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad89  dup
0x5ad8a  ldstr    aUnpublish// "UnPublish"
0x5ad8f  ldc.i4.s 0x18
0x5ad91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ad96  dup
0x5ad97  ldstr    aApprove// "Approve"
0x5ad9c  ldc.i4.s 0x19
0x5ad9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ada3  dup
0x5ada4  ldstr    aDeny// "Deny"
0x5ada9  ldc.i4.s 0x1A
0x5adab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5adb0  dup
0x5adb1  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0x5adb6  ldc.i4.s 0x1B
0x5adb8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5adbd  dup
0x5adbe  ldstr    aUpdatevirusinf// "UpdateVirusInfo"
0x5adc3  ldc.i4.s 0x1C
0x5adc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5adca  dup
0x5adcb  ldstr    aUpdate// "Update"
0x5add0  ldc.i4.s 0x1D
0x5add2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5add7  dup
0x5add8  ldstr    aMoveto// "MoveTo"
0x5addd  ldc.i4.s 0x1E
0x5addf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ade4  dup
0x5ade5  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5adea  ldc.i4.s 0x1F
0x5adec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5adf1  dup
0x5adf2  ldstr    aCopyto// "CopyTo"
0x5adf7  ldc.i4.s 0x20
0x5adf9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5adfe  dup
0x5adff  ldstr    aCopytousingpat// "CopyToUsingPath"
0x5ae04  ldc.i4.s 0x21
0x5ae06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5ae0b  volatile.
0x5ae0d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001024-1
0x5ae12  volatile.
0x5ae14  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001024-1
0x5ae19  ldloc.1
0x5ae1a  ldloca.s 2
0x5ae1c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5ae21  brfalse  loc_5B274
0x5ae26  ldloc.2
0x5ae27  switch   loc_5AEB9, loc_5AED4, loc_5AEEF, loc_5AF0A, loc_5AF25, loc_5AF40, loc_5AF5B, loc_5AF7B, loc_5AF96, loc_5AFB6, loc_5AFD1, loc_5AFED, loc_5B008, loc_5B023, loc_5B03E, loc_5B05A, loc_5B076, loc_5B092, loc_5B0B2, loc_5B0D2, loc_5B0ED, loc_5B109, loc_5B125, loc_5B141, loc_5B15D, loc_5B179, loc_5B195, loc_5B1B1, loc_5B1CC, loc_5B1E8, loc_5B204, loc_5B220, loc_5B23C, loc_5B258
0x5aeb4  br       loc_5B274
0x5aeb9  ldarg.s  5
0x5aebb  ldc.i4.0
0x5aebc  stind.i1
0x5aebd  ldarg.0
0x5aebe  ldstr    aAddactivities// "AddActivities"
0x5aec3  ldarg.s  4
0x5aec5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5aeca  ldloc.0
0x5aecb  ldarg.3
0x5aecc  ldarg.s  4
0x5aece  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse> Microsoft.SharePoint.ServerStub.SPFileServerStub::AddActivities_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5aed3  ret
0x5aed4  ldarg.s  5
0x5aed6  ldc.i4.0
0x5aed7  stind.i1
0x5aed8  ldarg.0
0x5aed9  ldstr    aAddclientactiv// "AddClientActivities"
0x5aede  ldarg.s  4
0x5aee0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5aee5  ldloc.0
0x5aee6  ldarg.3
0x5aee7  ldarg.s  4
0x5aee9  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse> Microsoft.SharePoint.ServerStub.SPFileServerStub::AddClientActivities_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5aeee  ret
0x5aeef  ldarg.s  5
0x5aef1  ldc.i4.0
0x5aef2  stind.i1
0x5aef3  ldarg.0
0x5aef4  ldstr    aGetlimitedwebp// "GetLimitedWebPartManager"
0x5aef9  ldarg.s  4
0x5aefb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af00  ldloc.0
0x5af01  ldarg.3
0x5af02  ldarg.s  4
0x5af04  call     class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPLimitedWebPartManager Microsoft.SharePoint.ServerStub.SPFileServerStub::GetLimitedWebPartManager_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af09  ret
0x5af0a  ldarg.s  5
0x5af0c  ldc.i4.0
0x5af0d  stind.i1
0x5af0e  ldarg.0
0x5af0f  ldstr    aGetpreauthoriz// "GetPreAuthorizedAccessUrl"
0x5af14  ldarg.s  4
0x5af16  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af1b  ldloc.0
0x5af1c  ldarg.3
0x5af1d  ldarg.s  4
0x5af1f  call     string Microsoft.SharePoint.ServerStub.SPFileServerStub::GetPreAuthorizedAccessUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af24  ret
0x5af25  ldarg.s  5
0x5af27  ldc.i4.0
0x5af28  stind.i1
0x5af29  ldarg.0
0x5af2a  ldstr    aGetimageprevie// "GetImagePreviewUrl"
0x5af2f  ldarg.s  4
0x5af31  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af36  ldloc.0
0x5af37  ldarg.3
0x5af38  ldarg.s  4
0x5af3a  call     string Microsoft.SharePoint.ServerStub.SPFileServerStub::GetImagePreviewUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af3f  ret
0x5af40  ldarg.s  5
0x5af42  ldc.i4.0
0x5af43  stind.i1
0x5af44  ldarg.0
0x5af45  ldstr    aGetimageprevie_0// "GetImagePreviewUri"
0x5af4a  ldarg.s  4
0x5af4c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af51  ldloc.0
0x5af52  ldarg.3
0x5af53  ldarg.s  4
0x5af55  call     class [System]System.Uri Microsoft.SharePoint.ServerStub.SPFileServerStub::GetImagePreviewUri_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af5a  ret
0x5af5b  ldarg.s  5
0x5af5d  ldc.i4.0
0x5af5e  stind.i1
0x5af5f  ldarg.0
0x5af60  ldstr    aStartupload// "StartUpload"
0x5af65  ldarg.s  4
0x5af67  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af6c  ldloc.0
0x5af6d  ldarg.3
0x5af6e  ldarg.s  4
0x5af70  call     int64 Microsoft.SharePoint.ServerStub.SPFileServerStub::StartUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af75  box      [mscorlib]System.Int64
0x5af7a  ret
0x5af7b  ldarg.s  5
0x5af7d  ldc.i4.0
0x5af7e  stind.i1
0x5af7f  ldarg.0
0x5af80  ldstr    aStartuploadfil// "StartUploadFile"
0x5af85  ldarg.s  4
0x5af87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5af8c  ldloc.0
0x5af8d  ldarg.3
0x5af8e  ldarg.s  4
0x5af90  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileServerStub::StartUploadFile_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5af95  ret
0x5af96  ldarg.s  5
0x5af98  ldc.i4.0
0x5af99  stind.i1
0x5af9a  ldarg.0
0x5af9b  ldstr    aContinueupload// "ContinueUpload"
0x5afa0  ldarg.s  4
0x5afa2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5afa7  ldloc.0
0x5afa8  ldarg.3
0x5afa9  ldarg.s  4
0x5afab  call     int64 Microsoft.SharePoint.ServerStub.SPFileServerStub::ContinueUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5afb0  box      [mscorlib]System.Int64
0x5afb5  ret
0x5afb6  ldarg.s  5
0x5afb8  ldc.i4.0
0x5afb9  stind.i1
0x5afba  ldarg.0
0x5afbb  ldstr    aFinishupload// "FinishUpload"
0x5afc0  ldarg.s  4
0x5afc2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5afc7  ldloc.0
0x5afc8  ldarg.3
0x5afc9  ldarg.s  4
0x5afcb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileServerStub::FinishUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5afd0  ret
0x5afd1  ldarg.s  5
0x5afd3  ldc.i4.1
0x5afd4  stind.i1
0x5afd5  ldarg.0
  ... truncated ...
```
