# Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeStaticMethod_0

- ea: `0x9af80`
- end: `0x9b298`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeStaticMethod_0`
- size: `792`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x9ac00`
- `0x9acc0`
- `0x9ad10`
- `0x9ad30`
- `0x9ad70`
- `0x9ada0`
- `0x9ade0`
- `0x9ae00`
- `0x9ae40`
- `0x9ae70`
- `0x9aeb0`
- `0x9aed0`
- `0x9aef0`
- `0x9af00`
- `0x9af20`
- `0x9af50`
- `0x9af70`
- `0x9af80`

## string_xrefs

- `0x9afc0`: `ForwardObjectLink`
- `0x9b10e`: `ForwardObjectLink`
- `0x9afe4`: `CreateAnonymousLink`
- `0x9b156`: `CreateAnonymousLink`
- `0x9aff0`: `CreateAnonymousLinkWithExpiration`
- `0x9b16e`: `CreateAnonymousLinkWithExpiration`
- `0x9affc`: `DeleteAllAnonymousLinksForObject`
- `0x9b186`: `DeleteAllAnonymousLinksForObject`
- `0x9b008`: `DeleteAnonymousLinkForObject`
- `0x9b19f`: `DeleteAnonymousLinkForObject`
- `0x9b014`: `CreateOrganizationSharingLink`
- `0x9b1b8`: `CreateOrganizationSharingLink`
- `0x9b020`: `DestroyOrganizationSharingLink`
- `0x9b1d0`: `DestroyOrganizationSharingLink`
- `0x9b02d`: `GetSharingLinkKind`
- `0x9b1e9`: `GetSharingLinkKind`

## pseudocode

```c

```

## disassembly

```asm
0x9af80  ldarg.3
0x9af81  brtrue.s loc_9AF8E
0x9af83  ldstr    aProxycontext// "proxyContext"
0x9af88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9af8d  throw
0x9af8e  ldarg.0
0x9af8f  ldarg.1
0x9af90  ldarg.3
0x9af91  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9af96  starg.s  1
0x9af98  ldarg.1
0x9af99  dup
0x9af9a  stloc.0
0x9af9b  brfalse  loc_9B291
0x9afa0  volatile.
0x9afa2  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191d-1
0x9afa7  brtrue   loc_9B08E
0x9afac  ldc.i4.s 0x11
0x9afae  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x9afb3  dup
0x9afb4  ldstr    aShareobject// "ShareObject"
0x9afb9  ldc.i4.0
0x9afba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9afbf  dup
0x9afc0  ldstr    aForwardobjectl// "ForwardObjectLink"
0x9afc5  ldc.i4.1
0x9afc6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9afcb  dup
0x9afcc  ldstr    aUnshareobject// "UnshareObject"
0x9afd1  ldc.i4.2
0x9afd2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9afd7  dup
0x9afd8  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0x9afdd  ldc.i4.3
0x9afde  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9afe3  dup
0x9afe4  ldstr    aCreateanonymou// "CreateAnonymousLink"
0x9afe9  ldc.i4.4
0x9afea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9afef  dup
0x9aff0  ldstr    aCreateanonymou_0// "CreateAnonymousLinkWithExpiration"
0x9aff5  ldc.i4.5
0x9aff6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9affb  dup
0x9affc  ldstr    aDeleteallanony// "DeleteAllAnonymousLinksForObject"
0x9b001  ldc.i4.6
0x9b002  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b007  dup
0x9b008  ldstr    aDeleteanonymou// "DeleteAnonymousLinkForObject"
0x9b00d  ldc.i4.7
0x9b00e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b013  dup
0x9b014  ldstr    aCreateorganiza// "CreateOrganizationSharingLink"
0x9b019  ldc.i4.8
0x9b01a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b01f  dup
0x9b020  ldstr    aDestroyorganiz// "DestroyOrganizationSharingLink"
0x9b025  ldc.i4.s 9
0x9b027  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b02c  dup
0x9b02d  ldstr    aGetsharinglink_0// "GetSharingLinkKind"
0x9b032  ldc.i4.s 0xA
0x9b034  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b039  dup
0x9b03a  ldstr    aGetweburlfromp// "GetWebUrlFromPageUrl"
0x9b03f  ldc.i4.s 0xB
0x9b041  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b046  dup
0x9b047  ldstr    aGetcontextwebi// "GetContextWebInformation"
0x9b04c  ldc.i4.s 0xC
0x9b04e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b053  dup
0x9b054  ldstr    aGetdocumentlib// "GetDocumentLibraries"
0x9b059  ldc.i4.s 0xD
0x9b05b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b060  dup
0x9b061  ldstr    aGetdocumentand// "GetDocumentAndMediaLibraries"
0x9b066  ldc.i4.s 0xE
0x9b068  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b06d  dup
0x9b06e  ldstr    aDefaultdocumen_0// "DefaultDocumentLibraryUrl"
0x9b073  ldc.i4.s 0xF
0x9b075  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b07a  dup
0x9b07b  ldstr    aGetcontextwebt// "GetContextWebThemeData"
0x9b080  ldc.i4.s 0x10
0x9b082  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9b087  volatile.
0x9b089  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191d-1
0x9b08e  volatile.
0x9b090  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x600191d-1
0x9b095  ldloc.0
0x9b096  ldloca.s 1
0x9b098  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9b09d  brfalse  loc_9B291
0x9b0a2  ldloc.1
0x9b0a3  switch   loc_9B0F1, loc_9B109, loc_9B121, loc_9B139, loc_9B151, loc_9B169, loc_9B181, loc_9B19A, loc_9B1B3, loc_9B1CB, loc_9B1E4, loc_9B201, loc_9B219, loc_9B231, loc_9B249, loc_9B261, loc_9B279
0x9b0ec  br       loc_9B291
0x9b0f1  ldarg.s  4
0x9b0f3  ldc.i4.0
0x9b0f4  stind.i1
0x9b0f5  ldarg.0
0x9b0f6  ldstr    aShareobject// "ShareObject"
0x9b0fb  ldarg.3
0x9b0fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b101  ldarg.2
0x9b102  ldarg.3
0x9b103  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::ShareObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b108  ret
0x9b109  ldarg.s  4
0x9b10b  ldc.i4.0
0x9b10c  stind.i1
0x9b10d  ldarg.0
0x9b10e  ldstr    aForwardobjectl// "ForwardObjectLink"
0x9b113  ldarg.3
0x9b114  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b119  ldarg.2
0x9b11a  ldarg.3
0x9b11b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::ForwardObjectLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b120  ret
0x9b121  ldarg.s  4
0x9b123  ldc.i4.0
0x9b124  stind.i1
0x9b125  ldarg.0
0x9b126  ldstr    aUnshareobject// "UnshareObject"
0x9b12b  ldarg.3
0x9b12c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b131  ldarg.2
0x9b132  ldarg.3
0x9b133  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::UnshareObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b138  ret
0x9b139  ldarg.s  4
0x9b13b  ldc.i4.0
0x9b13c  stind.i1
0x9b13d  ldarg.0
0x9b13e  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0x9b143  ldarg.3
0x9b144  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b149  ldarg.2
0x9b14a  ldarg.3
0x9b14b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings Microsoft.SharePoint.ServerStub.SPWebServerStub::GetObjectSharingSettings_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b150  ret
0x9b151  ldarg.s  4
0x9b153  ldc.i4.0
0x9b154  stind.i1
0x9b155  ldarg.0
0x9b156  ldstr    aCreateanonymou// "CreateAnonymousLink"
0x9b15b  ldarg.3
0x9b15c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b161  ldarg.2
0x9b162  ldarg.3
0x9b163  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateAnonymousLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b168  ret
0x9b169  ldarg.s  4
0x9b16b  ldc.i4.0
0x9b16c  stind.i1
0x9b16d  ldarg.0
0x9b16e  ldstr    aCreateanonymou_0// "CreateAnonymousLinkWithExpiration"
0x9b173  ldarg.3
0x9b174  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b179  ldarg.2
0x9b17a  ldarg.3
0x9b17b  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateAnonymousLinkWithExpiration_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b180  ret
0x9b181  ldarg.s  4
0x9b183  ldc.i4.1
0x9b184  stind.i1
0x9b185  ldarg.0
0x9b186  ldstr    aDeleteallanony// "DeleteAllAnonymousLinksForObject"
0x9b18b  ldarg.3
0x9b18c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b191  ldarg.2
0x9b192  ldarg.3
0x9b193  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DeleteAllAnonymousLinksForObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b198  ldnull
0x9b199  ret
0x9b19a  ldarg.s  4
0x9b19c  ldc.i4.1
0x9b19d  stind.i1
0x9b19e  ldarg.0
0x9b19f  ldstr    aDeleteanonymou// "DeleteAnonymousLinkForObject"
0x9b1a4  ldarg.3
0x9b1a5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b1aa  ldarg.2
0x9b1ab  ldarg.3
0x9b1ac  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DeleteAnonymousLinkForObject_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b1b1  ldnull
0x9b1b2  ret
0x9b1b3  ldarg.s  4
0x9b1b5  ldc.i4.0
0x9b1b6  stind.i1
0x9b1b7  ldarg.0
0x9b1b8  ldstr    aCreateorganiza// "CreateOrganizationSharingLink"
0x9b1bd  ldarg.3
0x9b1be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b1c3  ldarg.2
0x9b1c4  ldarg.3
0x9b1c5  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateOrganizationSharingLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b1ca  ret
0x9b1cb  ldarg.s  4
0x9b1cd  ldc.i4.1
0x9b1ce  stind.i1
0x9b1cf  ldarg.0
0x9b1d0  ldstr    aDestroyorganiz// "DestroyOrganizationSharingLink"
0x9b1d5  ldarg.3
0x9b1d6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b1db  ldarg.2
0x9b1dc  ldarg.3
0x9b1dd  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DestroyOrganizationSharingLink_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b1e2  ldnull
0x9b1e3  ret
0x9b1e4  ldarg.s  4
0x9b1e6  ldc.i4.0
0x9b1e7  stind.i1
0x9b1e8  ldarg.0
0x9b1e9  ldstr    aGetsharinglink_0// "GetSharingLinkKind"
0x9b1ee  ldarg.3
0x9b1ef  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b1f4  ldarg.2
0x9b1f5  ldarg.3
0x9b1f6  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.ServerStub.SPWebServerStub::GetSharingLinkKind_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b1fb  box      [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x9b200  ret
0x9b201  ldarg.s  4
0x9b203  ldc.i4.0
0x9b204  stind.i1
0x9b205  ldarg.0
0x9b206  ldstr    aGetweburlfromp// "GetWebUrlFromPageUrl"
0x9b20b  ldarg.3
0x9b20c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b211  ldarg.2
0x9b212  ldarg.3
0x9b213  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::GetWebUrlFromPageUrl_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b218  ret
0x9b219  ldarg.s  4
0x9b21b  ldc.i4.0
0x9b21c  stind.i1
0x9b21d  ldarg.0
0x9b21e  ldstr    aGetcontextwebi// "GetContextWebInformation"
0x9b223  ldarg.3
0x9b224  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b229  ldarg.2
0x9b22a  ldarg.3
0x9b22b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContextWebInformation Microsoft.SharePoint.ServerStub.SPWebServerStub::GetContextWebInformation_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b230  ret
0x9b231  ldarg.s  4
0x9b233  ldc.i4.0
0x9b234  stind.i1
0x9b235  ldarg.0
0x9b236  ldstr    aGetdocumentlib// "GetDocumentLibraries"
0x9b23b  ldarg.3
0x9b23c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b241  ldarg.2
0x9b242  ldarg.3
0x9b243  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::GetDocumentLibraries_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b248  ret
0x9b249  ldarg.s  4
0x9b24b  ldc.i4.0
0x9b24c  stind.i1
0x9b24d  ldarg.0
0x9b24e  ldstr    aGetdocumentand// "GetDocumentAndMediaLibraries"
0x9b253  ldarg.3
0x9b254  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b259  ldarg.2
0x9b25a  ldarg.3
0x9b25b  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::GetDocumentAndMediaLibraries_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b260  ret
0x9b261  ldarg.s  4
0x9b263  ldc.i4.0
0x9b264  stind.i1
0x9b265  ldarg.0
0x9b266  ldstr    aDefaultdocumen_0// "DefaultDocumentLibraryUrl"
0x9b26b  ldarg.3
0x9b26c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b271  ldarg.2
0x9b272  ldarg.3
0x9b273  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation Microsoft.SharePoint.ServerStub.SPWebServerStub::DefaultDocumentLibraryUrl_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b278  ret
0x9b279  ldarg.s  4
0x9b27b  ldc.i4.0
0x9b27c  stind.i1
0x9b27d  ldarg.0
0x9b27e  ldstr    aGetcontextwebt// "GetContextWebThemeData"
0x9b283  ldarg.3
0x9b284  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9b289  ldarg.2
0x9b28a  ldarg.3
0x9b28b  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::GetContextWebThemeData_MethodProxy(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValueCollection xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9b290  ret
0x9b291  ldarg.1
0x9b292  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x9b297  throw
```
