# Microsoft.SharePoint.ServerStub.SPConnectorServerStub::InvokeStaticMethod

- ea: `0x41420`
- end: `0x416b5`
- name: `Microsoft.SharePoint.ServerStub.SPConnectorServerStub::InvokeStaticMethod`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callees

- `0x410f0`
- `0x41120`
- `0x41130`
- `0x41150`
- `0x41180`
- `0x411b0`
- `0x41200`
- `0x41250`
- `0x412a0`
- `0x412e0`
- `0x41320`
- `0x41350`
- `0x41380`
- `0x413c0`
- `0x41420`

## string_xrefs

- `0x41454`: `DeleteListItem`
- `0x41563`: `DeleteListItem`
- `0x4149c`: `GetUpdatedListItems`
- `0x415f3`: `GetUpdatedListItems`
- `0x414a8`: `GetDeletedListItems`
- `0x4160b`: `GetDeletedListItems`
- `0x414da`: `CreateListItem`
- `0x4166b`: `CreateListItem`
- `0x414e7`: `UpdateListItem`
- `0x41683`: `UpdateListItem`

## pseudocode

```c

```

## disassembly

```asm
0x41420  ldarg.3
0x41421  brtrue.s loc_4142E
0x41423  ldstr    aProxycontext// "proxyContext"
0x41428  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4142d  throw
0x4142e  ldarg.0
0x4142f  ldarg.1
0x41430  ldarg.3
0x41431  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41436  starg.s  1
0x41438  ldarg.1
0x41439  dup
0x4143a  stloc.0
0x4143b  brfalse  loc_416AE
0x41440  volatile.
0x41442  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c40-1
0x41447  brtrue   loc_41507
0x4144c  ldc.i4.s 0xE
0x4144e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x41453  dup
0x41454  ldstr    aDeletelistitem// "DeleteListItem"
0x41459  ldc.i4.0
0x4145a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4145f  dup
0x41460  ldstr    aGettables// "GetTables"
0x41465  ldc.i4.1
0x41466  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4146b  dup
0x4146c  ldstr    aGettablemetada// "GetTableMetadata"
0x41471  ldc.i4.2
0x41472  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41477  dup
0x41478  ldstr    aGetlistitem// "GetListItem"
0x4147d  ldc.i4.3
0x4147e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41483  dup
0x41484  ldstr    aGetlistitems// "GetListItems"
0x41489  ldc.i4.4
0x4148a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4148f  dup
0x41490  ldstr    aGetnewlistitem// "GetNewListItems"
0x41495  ldc.i4.5
0x41496  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4149b  dup
0x4149c  ldstr    aGetupdatedlist// "GetUpdatedListItems"
0x414a1  ldc.i4.6
0x414a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414a7  dup
0x414a8  ldstr    aGetdeletedlist// "GetDeletedListItems"
0x414ad  ldc.i4.7
0x414ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414b3  dup
0x414b4  ldstr    aGetentityvalue// "GetEntityValues"
0x414b9  ldc.i4.8
0x414ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414bf  dup
0x414c0  ldstr    aResolveentityv// "ResolveEntityValue"
0x414c5  ldc.i4.s 9
0x414c7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414cc  dup
0x414cd  ldstr    aGetentities// "GetEntities"
0x414d2  ldc.i4.s 0xA
0x414d4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414d9  dup
0x414da  ldstr    aCreatelistitem// "CreateListItem"
0x414df  ldc.i4.s 0xB
0x414e1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414e6  dup
0x414e7  ldstr    aUpdatelistitem// "UpdateListItem"
0x414ec  ldc.i4.s 0xC
0x414ee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x414f3  dup
0x414f4  ldstr    aSetapprovalsta// "SetApprovalStatus"
0x414f9  ldc.i4.s 0xD
0x414fb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x41500  volatile.
0x41502  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c40-1
0x41507  volatile.
0x41509  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c40-1
0x4150e  ldloc.0
0x4150f  ldloca.s 1
0x41511  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x41516  brfalse  loc_416AE
0x4151b  ldloc.1
0x4151c  switch   loc_4155E, loc_41576, loc_4158E, loc_415A6, loc_415BE, loc_415D6, loc_415EE, loc_41606, loc_4161E, loc_41636, loc_4164E, loc_41666, loc_4167E, loc_41696
0x41559  br       loc_416AE
0x4155e  ldarg.s  4
0x41560  ldc.i4.0
0x41561  stind.i1
0x41562  ldarg.0
0x41563  ldstr    aDeletelistitem// "DeleteListItem"
0x41568  ldarg.3
0x41569  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4156e  ldarg.2
0x4156f  ldarg.3
0x41570  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::DeleteListItem_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41575  ret
0x41576  ldarg.s  4
0x41578  ldc.i4.0
0x41579  stind.i1
0x4157a  ldarg.0
0x4157b  ldstr    aGettables// "GetTables"
0x41580  ldarg.3
0x41581  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41586  ldarg.2
0x41587  ldarg.3
0x41588  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetTables_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4158d  ret
0x4158e  ldarg.s  4
0x41590  ldc.i4.0
0x41591  stind.i1
0x41592  ldarg.0
0x41593  ldstr    aGettablemetada// "GetTableMetadata"
0x41598  ldarg.3
0x41599  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4159e  ldarg.2
0x4159f  ldarg.3
0x415a0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetTableMetadata_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x415a5  ret
0x415a6  ldarg.s  4
0x415a8  ldc.i4.0
0x415a9  stind.i1
0x415aa  ldarg.0
0x415ab  ldstr    aGetlistitem// "GetListItem"
0x415b0  ldarg.3
0x415b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x415b6  ldarg.2
0x415b7  ldarg.3
0x415b8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetListItem_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x415bd  ret
0x415be  ldarg.s  4
0x415c0  ldc.i4.0
0x415c1  stind.i1
0x415c2  ldarg.0
0x415c3  ldstr    aGetlistitems// "GetListItems"
0x415c8  ldarg.3
0x415c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x415ce  ldarg.2
0x415cf  ldarg.3
0x415d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetListItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x415d5  ret
0x415d6  ldarg.s  4
0x415d8  ldc.i4.0
0x415d9  stind.i1
0x415da  ldarg.0
0x415db  ldstr    aGetnewlistitem// "GetNewListItems"
0x415e0  ldarg.3
0x415e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x415e6  ldarg.2
0x415e7  ldarg.3
0x415e8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetNewListItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x415ed  ret
0x415ee  ldarg.s  4
0x415f0  ldc.i4.0
0x415f1  stind.i1
0x415f2  ldarg.0
0x415f3  ldstr    aGetupdatedlist// "GetUpdatedListItems"
0x415f8  ldarg.3
0x415f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x415fe  ldarg.2
0x415ff  ldarg.3
0x41600  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetUpdatedListItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41605  ret
0x41606  ldarg.s  4
0x41608  ldc.i4.0
0x41609  stind.i1
0x4160a  ldarg.0
0x4160b  ldstr    aGetdeletedlist// "GetDeletedListItems"
0x41610  ldarg.3
0x41611  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41616  ldarg.2
0x41617  ldarg.3
0x41618  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetDeletedListItems_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4161d  ret
0x4161e  ldarg.s  4
0x41620  ldc.i4.0
0x41621  stind.i1
0x41622  ldarg.0
0x41623  ldstr    aGetentityvalue// "GetEntityValues"
0x41628  ldarg.3
0x41629  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4162e  ldarg.2
0x4162f  ldarg.3
0x41630  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetEntityValues_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41635  ret
0x41636  ldarg.s  4
0x41638  ldc.i4.0
0x41639  stind.i1
0x4163a  ldarg.0
0x4163b  ldstr    aResolveentityv// "ResolveEntityValue"
0x41640  ldarg.3
0x41641  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41646  ldarg.2
0x41647  ldarg.3
0x41648  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::ResolveEntityValue_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4164d  ret
0x4164e  ldarg.s  4
0x41650  ldc.i4.0
0x41651  stind.i1
0x41652  ldarg.0
0x41653  ldstr    aGetentities// "GetEntities"
0x41658  ldarg.3
0x41659  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4165e  ldarg.2
0x4165f  ldarg.3
0x41660  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::GetEntities_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41665  ret
0x41666  ldarg.s  4
0x41668  ldc.i4.0
0x41669  stind.i1
0x4166a  ldarg.0
0x4166b  ldstr    aCreatelistitem// "CreateListItem"
0x41670  ldarg.3
0x41671  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x41676  ldarg.2
0x41677  ldarg.3
0x41678  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::CreateListItem_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x4167d  ret
0x4167e  ldarg.s  4
0x41680  ldc.i4.0
0x41681  stind.i1
0x41682  ldarg.0
0x41683  ldstr    aUpdatelistitem// "UpdateListItem"
0x41688  ldarg.3
0x41689  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4168e  ldarg.2
0x4168f  ldarg.3
0x41690  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::UpdateListItem_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x41695  ret
0x41696  ldarg.s  4
0x41698  ldc.i4.0
0x41699  stind.i1
0x4169a  ldarg.0
0x4169b  ldstr    aSetapprovalsta// "SetApprovalStatus"
0x416a0  ldarg.3
0x416a1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedMethod(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x416a6  ldarg.2
0x416a7  ldarg.3
0x416a8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPConnectorResult Microsoft.SharePoint.ServerStub.SPConnectorServerStub::SetApprovalStatus_MethodProxy(class [System.Xml]System.Xml.XmlNodeList xmlargs, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x416ad  ret
0x416ae  ldarg.1
0x416af  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x416b4  throw
```
