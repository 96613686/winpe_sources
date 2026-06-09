# Microsoft.SharePoint.ServerStub.SPFileServerStub::InvokeMethod

- ea: `0x58550`
- end: `0x58bc2`
- name: `Microsoft.SharePoint.ServerStub.SPFileServerStub::InvokeMethod`
- size: `1650`
- prototype: ``
- caller_count: `0`
- callee_count: `35`
- tags: `installer_update, broker_com_uri`

## callees

- `0x58060`
- `0x58080`
- `0x580a0`
- `0x580c0`
- `0x580e0`
- `0x58120`
- `0x58160`
- `0x58190`
- `0x581c0`
- `0x58200`
- `0x58240`
- `0x58260`
- `0x58280`
- `0x58290`
- `0x582b0`
- `0x582d0`
- `0x582f0`
- `0x58300`
- `0x58310`
- `0x58330`
- `0x58350`
- `0x58360`
- `0x58370`
- `0x583a0`
- `0x583c0`
- `0x583e0`
- `0x58400`
- `0x58420`
- `0x58440`
- `0x58480`
- `0x58490`
- `0x584c0`
- `0x584f0`
- `0x58520`
- `0x58550`

## string_xrefs

- `0x5870b`: `Update`
- `0x58b2d`: `Update`
- `0x58662`: `DeleteObject`
- `0x589bb`: `DeleteObject`
- `0x5862e`: `OpenBinaryStream`
- `0x5894d`: `OpenBinaryStream`
- `0x585bf`: `GetPreAuthorizedAccessUrl`
- `0x5884f`: `GetPreAuthorizedAccessUrl`
- `0x585d7`: `GetImagePreviewUri`
- `0x58885`: `GetImagePreviewUri`
- `0x5863b`: `OpenBinaryStreamWithOptions`
- `0x58968`: `OpenBinaryStreamWithOptions`
- `0x586fe`: `UpdateVirusInfo`
- `0x58b11`: `UpdateVirusInfo`
- `0x58718`: `MoveTo`
- `0x58b49`: `MoveTo`
- `0x58725`: `MoveToUsingPath`
- `0x58b65`: `MoveToUsingPath`
- `0x58732`: `CopyTo`
- `0x58b81`: `CopyTo`
- `0x5873f`: `CopyToUsingPath`
- `0x58b9d`: `CopyToUsingPath`

## pseudocode

```c

```

## disassembly

```asm
0x58550  ldarg.s  4
0x58552  brtrue.s loc_5855F
0x58554  ldstr    aProxycontext// "proxyContext"
0x58559  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5855e  throw
0x5855f  ldarg.1
0x58560  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFile
0x58565  stloc.0
0x58566  ldloc.0
0x58567  brtrue.s loc_58574
0x58569  ldstr    aTarget// "target"
0x5856e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x58573  throw
0x58574  ldarg.0
0x58575  ldarg.2
0x58576  ldarg.s  4
0x58578  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5857d  starg.s  2
0x5857f  ldarg.2
0x58580  dup
0x58581  stloc.1
0x58582  brfalse  loc_58BB4
0x58587  volatile.
0x58589  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff4-1
0x5858e  brtrue   loc_58752
0x58593  ldc.i4.s 0x22
0x58595  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5859a  dup
0x5859b  ldstr    aAddactivities// "AddActivities"
0x585a0  ldc.i4.0
0x585a1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585a6  dup
0x585a7  ldstr    aAddclientactiv// "AddClientActivities"
0x585ac  ldc.i4.1
0x585ad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585b2  dup
0x585b3  ldstr    aGetlimitedwebp// "GetLimitedWebPartManager"
0x585b8  ldc.i4.2
0x585b9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585be  dup
0x585bf  ldstr    aGetpreauthoriz// "GetPreAuthorizedAccessUrl"
0x585c4  ldc.i4.3
0x585c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585ca  dup
0x585cb  ldstr    aGetimageprevie// "GetImagePreviewUrl"
0x585d0  ldc.i4.4
0x585d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585d6  dup
0x585d7  ldstr    aGetimageprevie_0// "GetImagePreviewUri"
0x585dc  ldc.i4.5
0x585dd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585e2  dup
0x585e3  ldstr    aStartupload// "StartUpload"
0x585e8  ldc.i4.6
0x585e9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585ee  dup
0x585ef  ldstr    aStartuploadfil// "StartUploadFile"
0x585f4  ldc.i4.7
0x585f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x585fa  dup
0x585fb  ldstr    aContinueupload// "ContinueUpload"
0x58600  ldc.i4.8
0x58601  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58606  dup
0x58607  ldstr    aFinishupload// "FinishUpload"
0x5860c  ldc.i4.s 9
0x5860e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58613  dup
0x58614  ldstr    aCancelupload// "CancelUpload"
0x58619  ldc.i4.s 0xA
0x5861b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58620  dup
0x58621  ldstr    aGetuploadstatu// "GetUploadStatus"
0x58626  ldc.i4.s 0xB
0x58628  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5862d  dup
0x5862e  ldstr    aOpenbinarystre// "OpenBinaryStream"
0x58633  ldc.i4.s 0xC
0x58635  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5863a  dup
0x5863b  ldstr    aOpenbinarystre_0// "OpenBinaryStreamWithOptions"
0x58640  ldc.i4.s 0xD
0x58642  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58647  dup
0x58648  ldstr    aSavebinarystre// "SaveBinaryStream"
0x5864d  ldc.i4.s 0xE
0x5864f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58654  dup
0x58655  ldstr    aSavebinary// "SaveBinary"
0x5865a  ldc.i4.s 0xF
0x5865c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58661  dup
0x58662  ldstr    aDeleteobject// "DeleteObject"
0x58667  ldc.i4.s 0x10
0x58669  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5866e  dup
0x5866f  ldstr    aRecycle// "Recycle"
0x58674  ldc.i4.s 0x11
0x58676  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5867b  dup
0x5867c  ldstr    aRecyclewitheta// "RecycleWithETag"
0x58681  ldc.i4.s 0x12
0x58683  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58688  dup
0x58689  ldstr    aExecutecobaltr// "ExecuteCobaltRequest"
0x5868e  ldc.i4.s 0x13
0x58690  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58695  dup
0x58696  ldstr    aCheckout_1// "CheckOut"
0x5869b  ldc.i4.s 0x14
0x5869d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586a2  dup
0x586a3  ldstr    aUndocheckout// "UndoCheckOut"
0x586a8  ldc.i4.s 0x15
0x586aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586af  dup
0x586b0  ldstr    aCheckin_1// "CheckIn"
0x586b5  ldc.i4.s 0x16
0x586b7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586bc  dup
0x586bd  ldstr    aPublish// "Publish"
0x586c2  ldc.i4.s 0x17
0x586c4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586c9  dup
0x586ca  ldstr    aUnpublish// "UnPublish"
0x586cf  ldc.i4.s 0x18
0x586d1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586d6  dup
0x586d7  ldstr    aApprove// "Approve"
0x586dc  ldc.i4.s 0x19
0x586de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586e3  dup
0x586e4  ldstr    aDeny// "Deny"
0x586e9  ldc.i4.s 0x1A
0x586eb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586f0  dup
0x586f1  ldstr    aGetwopiframeur// "GetWOPIFrameUrl"
0x586f6  ldc.i4.s 0x1B
0x586f8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x586fd  dup
0x586fe  ldstr    aUpdatevirusinf// "UpdateVirusInfo"
0x58703  ldc.i4.s 0x1C
0x58705  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5870a  dup
0x5870b  ldstr    aUpdate// "Update"
0x58710  ldc.i4.s 0x1D
0x58712  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58717  dup
0x58718  ldstr    aMoveto// "MoveTo"
0x5871d  ldc.i4.s 0x1E
0x5871f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58724  dup
0x58725  ldstr    aMovetousingpat// "MoveToUsingPath"
0x5872a  ldc.i4.s 0x1F
0x5872c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x58731  dup
0x58732  ldstr    aCopyto// "CopyTo"
0x58737  ldc.i4.s 0x20
0x58739  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5873e  dup
0x5873f  ldstr    aCopytousingpat// "CopyToUsingPath"
0x58744  ldc.i4.s 0x21
0x58746  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5874b  volatile.
0x5874d  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff4-1
0x58752  volatile.
0x58754  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ff4-1
0x58759  ldloc.1
0x5875a  ldloca.s 2
0x5875c  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x58761  brfalse  loc_58BB4
0x58766  ldloc.2
0x58767  switch   loc_587F9, loc_58814, loc_5882F, loc_5884A, loc_58865, loc_58880, loc_5889B, loc_588BB, loc_588D6, loc_588F6, loc_58911, loc_5892D, loc_58948, loc_58963, loc_5897E, loc_5899A, loc_589B6, loc_589D2, loc_589F2, loc_58A12, loc_58A2D, loc_58A49, loc_58A65, loc_58A81, loc_58A9D, loc_58AB9, loc_58AD5, loc_58AF1, loc_58B0C, loc_58B28, loc_58B44, loc_58B60, loc_58B7C, loc_58B98
0x587f4  br       loc_58BB4
0x587f9  ldarg.s  5
0x587fb  ldc.i4.0
0x587fc  stind.i1
0x587fd  ldarg.0
0x587fe  ldstr    aAddactivities// "AddActivities"
0x58803  ldarg.s  4
0x58805  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5880a  ldloc.0
0x5880b  ldarg.3
0x5880c  ldarg.s  4
0x5880e  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse> Microsoft.SharePoint.ServerStub.SPFileServerStub::AddActivities_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x58813  ret
0x58814  ldarg.s  5
0x58816  ldc.i4.0
0x58817  stind.i1
0x58818  ldarg.0
0x58819  ldstr    aAddclientactiv// "AddClientActivities"
0x5881e  ldarg.s  4
0x58820  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58825  ldloc.0
0x58826  ldarg.3
0x58827  ldarg.s  4
0x58829  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityResponse> Microsoft.SharePoint.ServerStub.SPFileServerStub::AddClientActivities_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5882e  ret
0x5882f  ldarg.s  5
0x58831  ldc.i4.0
0x58832  stind.i1
0x58833  ldarg.0
0x58834  ldstr    aGetlimitedwebp// "GetLimitedWebPartManager"
0x58839  ldarg.s  4
0x5883b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58840  ldloc.0
0x58841  ldarg.3
0x58842  ldarg.s  4
0x58844  call     class [Microsoft.SharePoint]Microsoft.SharePoint.WebPartPages.SPLimitedWebPartManager Microsoft.SharePoint.ServerStub.SPFileServerStub::GetLimitedWebPartManager_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x58849  ret
0x5884a  ldarg.s  5
0x5884c  ldc.i4.0
0x5884d  stind.i1
0x5884e  ldarg.0
0x5884f  ldstr    aGetpreauthoriz// "GetPreAuthorizedAccessUrl"
0x58854  ldarg.s  4
0x58856  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5885b  ldloc.0
0x5885c  ldarg.3
0x5885d  ldarg.s  4
0x5885f  call     string Microsoft.SharePoint.ServerStub.SPFileServerStub::GetPreAuthorizedAccessUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x58864  ret
0x58865  ldarg.s  5
0x58867  ldc.i4.0
0x58868  stind.i1
0x58869  ldarg.0
0x5886a  ldstr    aGetimageprevie// "GetImagePreviewUrl"
0x5886f  ldarg.s  4
0x58871  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58876  ldloc.0
0x58877  ldarg.3
0x58878  ldarg.s  4
0x5887a  call     string Microsoft.SharePoint.ServerStub.SPFileServerStub::GetImagePreviewUrl_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5887f  ret
0x58880  ldarg.s  5
0x58882  ldc.i4.0
0x58883  stind.i1
0x58884  ldarg.0
0x58885  ldstr    aGetimageprevie_0// "GetImagePreviewUri"
0x5888a  ldarg.s  4
0x5888c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58891  ldloc.0
0x58892  ldarg.3
0x58893  ldarg.s  4
0x58895  call     class [System]System.Uri Microsoft.SharePoint.ServerStub.SPFileServerStub::GetImagePreviewUri_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x5889a  ret
0x5889b  ldarg.s  5
0x5889d  ldc.i4.0
0x5889e  stind.i1
0x5889f  ldarg.0
0x588a0  ldstr    aStartupload// "StartUpload"
0x588a5  ldarg.s  4
0x588a7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x588ac  ldloc.0
0x588ad  ldarg.3
0x588ae  ldarg.s  4
0x588b0  call     int64 Microsoft.SharePoint.ServerStub.SPFileServerStub::StartUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x588b5  box      [mscorlib]System.Int64
0x588ba  ret
0x588bb  ldarg.s  5
0x588bd  ldc.i4.0
0x588be  stind.i1
0x588bf  ldarg.0
0x588c0  ldstr    aStartuploadfil// "StartUploadFile"
0x588c5  ldarg.s  4
0x588c7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x588cc  ldloc.0
0x588cd  ldarg.3
0x588ce  ldarg.s  4
0x588d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileServerStub::StartUploadFile_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x588d5  ret
0x588d6  ldarg.s  5
0x588d8  ldc.i4.0
0x588d9  stind.i1
0x588da  ldarg.0
0x588db  ldstr    aContinueupload// "ContinueUpload"
0x588e0  ldarg.s  4
0x588e2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x588e7  ldloc.0
0x588e8  ldarg.3
0x588e9  ldarg.s  4
0x588eb  call     int64 Microsoft.SharePoint.ServerStub.SPFileServerStub::ContinueUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x588f0  box      [mscorlib]System.Int64
0x588f5  ret
0x588f6  ldarg.s  5
0x588f8  ldc.i4.0
0x588f9  stind.i1
0x588fa  ldarg.0
0x588fb  ldstr    aFinishupload// "FinishUpload"
0x58900  ldarg.s  4
0x58902  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x58907  ldloc.0
0x58908  ldarg.3
0x58909  ldarg.s  4
0x5890b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile Microsoft.SharePoint.ServerStub.SPFileServerStub::FinishUpload_MethodProxy(class [Microsoft.SharePoint]Microsoft.SharePoint.SPFile target, class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x58910  ret
0x58911  ldarg.s  5
0x58913  ldc.i4.1
0x58914  stind.i1
0x58915  ldarg.0
  ... truncated ...
```
