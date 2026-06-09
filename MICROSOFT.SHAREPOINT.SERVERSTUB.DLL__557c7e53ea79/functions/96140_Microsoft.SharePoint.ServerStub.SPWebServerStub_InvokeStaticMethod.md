# Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeStaticMethod

- ea: `0x96140`
- end: `0x96458`
- name: `Microsoft.SharePoint.ServerStub.SPWebServerStub::InvokeStaticMethod`
- size: `792`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x95dc0`
- `0x95e80`
- `0x95ed0`
- `0x95ef0`
- `0x95f30`
- `0x95f60`
- `0x95fa0`
- `0x95fc0`
- `0x96000`
- `0x96030`
- `0x96070`
- `0x96090`
- `0x960b0`
- `0x960c0`
- `0x960e0`
- `0x96110`
- `0x96130`
- `0x96140`

## string_xrefs

- `0x96180`: `ForwardObjectLink`
- `0x962ce`: `ForwardObjectLink`
- `0x961a4`: `CreateAnonymousLink`
- `0x96316`: `CreateAnonymousLink`
- `0x961b0`: `CreateAnonymousLinkWithExpiration`
- `0x9632e`: `CreateAnonymousLinkWithExpiration`
- `0x961bc`: `DeleteAllAnonymousLinksForObject`
- `0x96346`: `DeleteAllAnonymousLinksForObject`
- `0x961c8`: `DeleteAnonymousLinkForObject`
- `0x9635f`: `DeleteAnonymousLinkForObject`
- `0x961d4`: `CreateOrganizationSharingLink`
- `0x96378`: `CreateOrganizationSharingLink`
- `0x961e0`: `DestroyOrganizationSharingLink`
- `0x96390`: `DestroyOrganizationSharingLink`
- `0x961ed`: `GetSharingLinkKind`
- `0x963a9`: `GetSharingLinkKind`

## pseudocode

```c

```

## disassembly

```asm
0x96140  ldarg.3
0x96141  brtrue.s loc_9614E
0x96143  ldstr    aProxycontext// "proxyContext"
0x96148  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9614d  throw
0x9614e  ldarg.0
0x9614f  ldarg.1
0x96150  ldarg.3
0x96151  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96156  starg.s  1
0x96158  ldarg.1
0x96159  dup
0x9615a  stloc.0
0x9615b  brfalse  loc_96451
0x96160  volatile.
0x96162  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018b7-1
0x96167  brtrue   loc_9624E
0x9616c  ldc.i4.s 0x11
0x9616e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x96173  dup
0x96174  ldstr    aShareobject// "ShareObject"
0x96179  ldc.i4.0
0x9617a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9617f  dup
0x96180  ldstr    aForwardobjectl// "ForwardObjectLink"
0x96185  ldc.i4.1
0x96186  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9618b  dup
0x9618c  ldstr    aUnshareobject// "UnshareObject"
0x96191  ldc.i4.2
0x96192  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96197  dup
0x96198  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0x9619d  ldc.i4.3
0x9619e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961a3  dup
0x961a4  ldstr    aCreateanonymou// "CreateAnonymousLink"
0x961a9  ldc.i4.4
0x961aa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961af  dup
0x961b0  ldstr    aCreateanonymou_0// "CreateAnonymousLinkWithExpiration"
0x961b5  ldc.i4.5
0x961b6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961bb  dup
0x961bc  ldstr    aDeleteallanony// "DeleteAllAnonymousLinksForObject"
0x961c1  ldc.i4.6
0x961c2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961c7  dup
0x961c8  ldstr    aDeleteanonymou// "DeleteAnonymousLinkForObject"
0x961cd  ldc.i4.7
0x961ce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961d3  dup
0x961d4  ldstr    aCreateorganiza// "CreateOrganizationSharingLink"
0x961d9  ldc.i4.8
0x961da  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961df  dup
0x961e0  ldstr    aDestroyorganiz// "DestroyOrganizationSharingLink"
0x961e5  ldc.i4.s 9
0x961e7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961ec  dup
0x961ed  ldstr    aGetsharinglink_0// "GetSharingLinkKind"
0x961f2  ldc.i4.s 0xA
0x961f4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x961f9  dup
0x961fa  ldstr    aGetweburlfromp// "GetWebUrlFromPageUrl"
0x961ff  ldc.i4.s 0xB
0x96201  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96206  dup
0x96207  ldstr    aGetcontextwebi// "GetContextWebInformation"
0x9620c  ldc.i4.s 0xC
0x9620e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96213  dup
0x96214  ldstr    aGetdocumentlib// "GetDocumentLibraries"
0x96219  ldc.i4.s 0xD
0x9621b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96220  dup
0x96221  ldstr    aGetdocumentand// "GetDocumentAndMediaLibraries"
0x96226  ldc.i4.s 0xE
0x96228  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9622d  dup
0x9622e  ldstr    aDefaultdocumen_0// "DefaultDocumentLibraryUrl"
0x96233  ldc.i4.s 0xF
0x96235  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x9623a  dup
0x9623b  ldstr    aGetcontextwebt// "GetContextWebThemeData"
0x96240  ldc.i4.s 0x10
0x96242  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x96247  volatile.
0x96249  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018b7-1
0x9624e  volatile.
0x96250  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60018b7-1
0x96255  ldloc.0
0x96256  ldloca.s 1
0x96258  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x9625d  brfalse  loc_96451
0x96262  ldloc.1
0x96263  switch   loc_962B1, loc_962C9, loc_962E1, loc_962F9, loc_96311, loc_96329, loc_96341, loc_9635A, loc_96373, loc_9638B, loc_963A4, loc_963C1, loc_963D9, loc_963F1, loc_96409, loc_96421, loc_96439
0x962ac  br       loc_96451
0x962b1  ldarg.s  4
0x962b3  ldc.i4.0
0x962b4  stind.i1
0x962b5  ldarg.0
0x962b6  ldstr    aShareobject// "ShareObject"
0x962bb  ldarg.3
0x962bc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x962c1  ldarg.2
0x962c2  ldarg.3
0x962c3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::ShareObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x962c8  ret
0x962c9  ldarg.s  4
0x962cb  ldc.i4.0
0x962cc  stind.i1
0x962cd  ldarg.0
0x962ce  ldstr    aForwardobjectl// "ForwardObjectLink"
0x962d3  ldarg.3
0x962d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x962d9  ldarg.2
0x962da  ldarg.3
0x962db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::ForwardObjectLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x962e0  ret
0x962e1  ldarg.s  4
0x962e3  ldc.i4.0
0x962e4  stind.i1
0x962e5  ldarg.0
0x962e6  ldstr    aUnshareobject// "UnshareObject"
0x962eb  ldarg.3
0x962ec  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x962f1  ldarg.2
0x962f2  ldarg.3
0x962f3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SharingResult Microsoft.SharePoint.ServerStub.SPWebServerStub::UnshareObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x962f8  ret
0x962f9  ldarg.s  4
0x962fb  ldc.i4.0
0x962fc  stind.i1
0x962fd  ldarg.0
0x962fe  ldstr    aGetobjectshari_2// "GetObjectSharingSettings"
0x96303  ldarg.3
0x96304  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96309  ldarg.2
0x9630a  ldarg.3
0x9630b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ObjectSharingSettings Microsoft.SharePoint.ServerStub.SPWebServerStub::GetObjectSharingSettings_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96310  ret
0x96311  ldarg.s  4
0x96313  ldc.i4.0
0x96314  stind.i1
0x96315  ldarg.0
0x96316  ldstr    aCreateanonymou// "CreateAnonymousLink"
0x9631b  ldarg.3
0x9631c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96321  ldarg.2
0x96322  ldarg.3
0x96323  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateAnonymousLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96328  ret
0x96329  ldarg.s  4
0x9632b  ldc.i4.0
0x9632c  stind.i1
0x9632d  ldarg.0
0x9632e  ldstr    aCreateanonymou_0// "CreateAnonymousLinkWithExpiration"
0x96333  ldarg.3
0x96334  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96339  ldarg.2
0x9633a  ldarg.3
0x9633b  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateAnonymousLinkWithExpiration_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96340  ret
0x96341  ldarg.s  4
0x96343  ldc.i4.1
0x96344  stind.i1
0x96345  ldarg.0
0x96346  ldstr    aDeleteallanony// "DeleteAllAnonymousLinksForObject"
0x9634b  ldarg.3
0x9634c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96351  ldarg.2
0x96352  ldarg.3
0x96353  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DeleteAllAnonymousLinksForObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96358  ldnull
0x96359  ret
0x9635a  ldarg.s  4
0x9635c  ldc.i4.1
0x9635d  stind.i1
0x9635e  ldarg.0
0x9635f  ldstr    aDeleteanonymou// "DeleteAnonymousLinkForObject"
0x96364  ldarg.3
0x96365  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9636a  ldarg.2
0x9636b  ldarg.3
0x9636c  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DeleteAnonymousLinkForObject_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96371  ldnull
0x96372  ret
0x96373  ldarg.s  4
0x96375  ldc.i4.0
0x96376  stind.i1
0x96377  ldarg.0
0x96378  ldstr    aCreateorganiza// "CreateOrganizationSharingLink"
0x9637d  ldarg.3
0x9637e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96383  ldarg.2
0x96384  ldarg.3
0x96385  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::CreateOrganizationSharingLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x9638a  ret
0x9638b  ldarg.s  4
0x9638d  ldc.i4.1
0x9638e  stind.i1
0x9638f  ldarg.0
0x96390  ldstr    aDestroyorganiz// "DestroyOrganizationSharingLink"
0x96395  ldarg.3
0x96396  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x9639b  ldarg.2
0x9639c  ldarg.3
0x9639d  call     void Microsoft.SharePoint.ServerStub.SPWebServerStub::DestroyOrganizationSharingLink_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x963a2  ldnull
0x963a3  ret
0x963a4  ldarg.s  4
0x963a6  ldc.i4.0
0x963a7  stind.i1
0x963a8  ldarg.0
0x963a9  ldstr    aGetsharinglink_0// "GetSharingLinkKind"
0x963ae  ldarg.3
0x963af  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x963b4  ldarg.2
0x963b5  ldarg.3
0x963b6  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind Microsoft.SharePoint.ServerStub.SPWebServerStub::GetSharingLinkKind_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x963bb  box      [Microsoft.SharePoint]Microsoft.SharePoint.SharingLinkKind
0x963c0  ret
0x963c1  ldarg.s  4
0x963c3  ldc.i4.0
0x963c4  stind.i1
0x963c5  ldarg.0
0x963c6  ldstr    aGetweburlfromp// "GetWebUrlFromPageUrl"
0x963cb  ldarg.3
0x963cc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x963d1  ldarg.2
0x963d2  ldarg.3
0x963d3  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::GetWebUrlFromPageUrl_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x963d8  ret
0x963d9  ldarg.s  4
0x963db  ldc.i4.0
0x963dc  stind.i1
0x963dd  ldarg.0
0x963de  ldstr    aGetcontextwebi// "GetContextWebInformation"
0x963e3  ldarg.3
0x963e4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x963e9  ldarg.2
0x963ea  ldarg.3
0x963eb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPContextWebInformation Microsoft.SharePoint.ServerStub.SPWebServerStub::GetContextWebInformation_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x963f0  ret
0x963f1  ldarg.s  4
0x963f3  ldc.i4.0
0x963f4  stind.i1
0x963f5  ldarg.0
0x963f6  ldstr    aGetdocumentlib// "GetDocumentLibraries"
0x963fb  ldarg.3
0x963fc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96401  ldarg.2
0x96402  ldarg.3
0x96403  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::GetDocumentLibraries_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96408  ret
0x96409  ldarg.s  4
0x9640b  ldc.i4.0
0x9640c  stind.i1
0x9640d  ldarg.0
0x9640e  ldstr    aGetdocumentand// "GetDocumentAndMediaLibraries"
0x96413  ldarg.3
0x96414  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96419  ldarg.2
0x9641a  ldarg.3
0x9641b  call     class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation> Microsoft.SharePoint.ServerStub.SPWebServerStub::GetDocumentAndMediaLibraries_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96420  ret
0x96421  ldarg.s  4
0x96423  ldc.i4.0
0x96424  stind.i1
0x96425  ldarg.0
0x96426  ldstr    aDefaultdocumen_0// "DefaultDocumentLibraryUrl"
0x9642b  ldarg.3
0x9642c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96431  ldarg.2
0x96432  ldarg.3
0x96433  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPDocumentLibraryInformation Microsoft.SharePoint.ServerStub.SPWebServerStub::DefaultDocumentLibraryUrl_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96438  ret
0x96439  ldarg.s  4
0x9643b  ldc.i4.0
0x9643c  stind.i1
0x9643d  ldarg.0
0x9643e  ldstr    aGetcontextwebt// "GetContextWebThemeData"
0x96443  ldarg.3
0x96444  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x96449  ldarg.2
0x9644a  ldarg.3
0x9644b  call     string Microsoft.SharePoint.ServerStub.SPWebServerStub::GetContextWebThemeData_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x96450  ret
0x96451  ldarg.1
0x96452  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x96457  throw
```
