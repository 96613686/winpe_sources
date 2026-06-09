# Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetProperty

- ea: `0x5e200`
- end: `0x5e56b`
- name: `Microsoft.SharePoint.ServerStub.SPFolderServerStub::GetProperty`
- size: `875`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5e200`

## string_xrefs

- `0x5e2dd`: `ServerRelativePath`
- `0x5e4a8`: `ServerRelativePath`
- `0x5e311`: `TimeCreated`
- `0x5e4f4`: `TimeCreated`
- `0x5e345`: `WelcomePage`
- `0x5e54f`: `WelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0x5e200  ldarg.2
0x5e201  brtrue.s loc_5E20E
0x5e203  ldstr    aPropname// "propName"
0x5e208  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e20d  throw
0x5e20e  ldarg.3
0x5e20f  brtrue.s loc_5E21C
0x5e211  ldstr    aProxycontext// "proxyContext"
0x5e216  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e21b  throw
0x5e21c  ldarg.1
0x5e21d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x5e222  stloc.0
0x5e223  ldloc.0
0x5e224  brtrue.s loc_5E231
0x5e226  ldstr    aTarget// "target"
0x5e22b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e230  throw
0x5e231  ldarg.0
0x5e232  ldarg.2
0x5e233  ldarg.3
0x5e234  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e239  starg.s  2
0x5e23b  ldarg.2
0x5e23c  dup
0x5e23d  stloc.1
0x5e23e  brfalse  loc_5E561
0x5e243  volatile.
0x5e245  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c9-1
0x5e24a  brtrue   loc_5E358
0x5e24f  ldc.i4.s 0x14
0x5e251  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5e256  dup
0x5e257  ldstr    aActivities// "Activities"
0x5e25c  ldc.i4.0
0x5e25d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e262  dup
0x5e263  ldstr    aContenttypeord// "ContentTypeOrder"
0x5e268  ldc.i4.1
0x5e269  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e26e  dup
0x5e26f  ldstr    aExists// "Exists"
0x5e274  ldc.i4.2
0x5e275  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e27a  dup
0x5e27b  ldstr    aFiles// "Files"
0x5e280  ldc.i4.3
0x5e281  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e286  dup
0x5e287  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5e28c  ldc.i4.4
0x5e28d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e292  dup
0x5e293  ldstr    aListitemallfie// "ListItemAllFields"
0x5e298  ldc.i4.5
0x5e299  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e29e  dup
0x5e29f  ldstr    aItemcount// "ItemCount"
0x5e2a4  ldc.i4.6
0x5e2a5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2aa  dup
0x5e2ab  ldstr    aName// "Name"
0x5e2b0  ldc.i4.7
0x5e2b1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2b6  dup
0x5e2b7  ldstr    aParentfolder// "ParentFolder"
0x5e2bc  ldc.i4.8
0x5e2bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2c2  dup
0x5e2c3  ldstr    aProgid// "ProgID"
0x5e2c8  ldc.i4.s 9
0x5e2ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2cf  dup
0x5e2d0  ldstr    aProperties// "Properties"
0x5e2d5  ldc.i4.s 0xA
0x5e2d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2dc  dup
0x5e2dd  ldstr    aServerrelative_0// "ServerRelativePath"
0x5e2e2  ldc.i4.s 0xB
0x5e2e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2e9  dup
0x5e2ea  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5e2ef  ldc.i4.s 0xC
0x5e2f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e2f6  dup
0x5e2f7  ldstr    aStoragemetrics// "StorageMetrics"
0x5e2fc  ldc.i4.s 0xD
0x5e2fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e303  dup
0x5e304  ldstr    aFolders// "Folders"
0x5e309  ldc.i4.s 0xE
0x5e30b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e310  dup
0x5e311  ldstr    aTimecreated// "TimeCreated"
0x5e316  ldc.i4.s 0xF
0x5e318  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e31d  dup
0x5e31e  ldstr    aTimelastmodifi// "TimeLastModified"
0x5e323  ldc.i4.s 0x10
0x5e325  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e32a  dup
0x5e32b  ldstr    aUniquecontentt// "UniqueContentTypeOrder"
0x5e330  ldc.i4.s 0x11
0x5e332  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e337  dup
0x5e338  ldstr    aUniqueid_0// "UniqueId"
0x5e33d  ldc.i4.s 0x12
0x5e33f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e344  dup
0x5e345  ldstr    aWelcomepage// "WelcomePage"
0x5e34a  ldc.i4.s 0x13
0x5e34c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e351  volatile.
0x5e353  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c9-1
0x5e358  volatile.
0x5e35a  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010c9-1
0x5e35f  ldloc.1
0x5e360  ldloca.s 2
0x5e362  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5e367  brfalse  loc_5E561
0x5e36c  ldloc.2
0x5e36d  switch   loc_5E3C7, loc_5E3DA, loc_5E3ED, loc_5E405, loc_5E418, loc_5E430, loc_5E443, loc_5E45B, loc_5E46E, loc_5E481, loc_5E494, loc_5E4A7, loc_5E4BA, loc_5E4CD, loc_5E4E0, loc_5E4F3, loc_5E50B, loc_5E523, loc_5E536, loc_5E54E
0x5e3c2  br       loc_5E561
0x5e3c7  ldarg.0
0x5e3c8  ldstr    aActivities// "Activities"
0x5e3cd  ldarg.3
0x5e3ce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e3d3  ldloc.0
0x5e3d4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Activities()
0x5e3d9  ret
0x5e3da  ldarg.0
0x5e3db  ldstr    aContenttypeord// "ContentTypeOrder"
0x5e3e0  ldarg.3
0x5e3e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e3e6  ldloc.0
0x5e3e7  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId> [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ContentTypeOrder_Client()
0x5e3ec  ret
0x5e3ed  ldarg.0
0x5e3ee  ldstr    aExists// "Exists"
0x5e3f3  ldarg.3
0x5e3f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e3f9  ldloc.0
0x5e3fa  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Exists()
0x5e3ff  box      [mscorlib]System.Boolean
0x5e404  ret
0x5e405  ldarg.0
0x5e406  ldstr    aFiles// "Files"
0x5e40b  ldarg.3
0x5e40c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e411  ldloc.0
0x5e412  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Files()
0x5e417  ret
0x5e418  ldarg.0
0x5e419  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5e41e  ldarg.3
0x5e41f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e424  ldloc.0
0x5e425  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_IsWOPIEnabled()
0x5e42a  box      [mscorlib]System.Boolean
0x5e42f  ret
0x5e430  ldarg.0
0x5e431  ldstr    aListitemallfie// "ListItemAllFields"
0x5e436  ldarg.3
0x5e437  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e43c  ldloc.0
0x5e43d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Item()
0x5e442  ret
0x5e443  ldarg.0
0x5e444  ldstr    aItemcount// "ItemCount"
0x5e449  ldarg.3
0x5e44a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e44f  ldloc.0
0x5e450  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ItemCount()
0x5e455  box      [mscorlib]System.Int32
0x5e45a  ret
0x5e45b  ldarg.0
0x5e45c  ldstr    aName// "Name"
0x5e461  ldarg.3
0x5e462  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e467  ldloc.0
0x5e468  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Name()
0x5e46d  ret
0x5e46e  ldarg.0
0x5e46f  ldstr    aParentfolder// "ParentFolder"
0x5e474  ldarg.3
0x5e475  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e47a  ldloc.0
0x5e47b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ParentFolder()
0x5e480  ret
0x5e481  ldarg.0
0x5e482  ldstr    aProgid// "ProgID"
0x5e487  ldarg.3
0x5e488  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e48d  ldloc.0
0x5e48e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ProgID()
0x5e493  ret
0x5e494  ldarg.0
0x5e495  ldstr    aProperties// "Properties"
0x5e49a  ldarg.3
0x5e49b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4a0  ldloc.0
0x5e4a1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPPropertyValues [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Properties_Client()
0x5e4a6  ret
0x5e4a7  ldarg.0
0x5e4a8  ldstr    aServerrelative_0// "ServerRelativePath"
0x5e4ad  ldarg.3
0x5e4ae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4b3  ldloc.0
0x5e4b4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ServerRelativePath()
0x5e4b9  ret
0x5e4ba  ldarg.0
0x5e4bb  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5e4c0  ldarg.3
0x5e4c1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4c6  ldloc.0
0x5e4c7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ServerRelativeUrl()
0x5e4cc  ret
0x5e4cd  ldarg.0
0x5e4ce  ldstr    aStoragemetrics// "StorageMetrics"
0x5e4d3  ldarg.3
0x5e4d4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4d9  ldloc.0
0x5e4da  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPStorageMetrics [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_StorageMetrics()
0x5e4df  ret
0x5e4e0  ldarg.0
0x5e4e1  ldstr    aFolders// "Folders"
0x5e4e6  ldarg.3
0x5e4e7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4ec  ldloc.0
0x5e4ed  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFolderCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_SubFolders()
0x5e4f2  ret
0x5e4f3  ldarg.0
0x5e4f4  ldstr    aTimecreated// "TimeCreated"
0x5e4f9  ldarg.3
0x5e4fa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e4ff  ldloc.0
0x5e500  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_TimeCreated()
0x5e505  box      [mscorlib]System.DateTime
0x5e50a  ret
0x5e50b  ldarg.0
0x5e50c  ldstr    aTimelastmodifi// "TimeLastModified"
0x5e511  ldarg.3
0x5e512  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e517  ldloc.0
0x5e518  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_TimeLastModified()
0x5e51d  box      [mscorlib]System.DateTime
0x5e522  ret
0x5e523  ldarg.0
0x5e524  ldstr    aUniquecontentt// "UniqueContentTypeOrder"
0x5e529  ldarg.3
0x5e52a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e52f  ldloc.0
0x5e530  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId> [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_UniqueContentTypeOrder_Client()
0x5e535  ret
0x5e536  ldarg.0
0x5e537  ldstr    aUniqueid_0// "UniqueId"
0x5e53c  ldarg.3
0x5e53d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e542  ldloc.0
0x5e543  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_UniqueId()
0x5e548  box      [mscorlib]System.Guid
0x5e54d  ret
0x5e54e  ldarg.0
0x5e54f  ldstr    aWelcomepage// "WelcomePage"
0x5e554  ldarg.3
0x5e555  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e55a  ldloc.0
0x5e55b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_WelcomePage()
0x5e560  ret
0x5e561  ldarg.0
0x5e562  ldarg.1
0x5e563  ldarg.2
0x5e564  ldarg.3
0x5e565  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e56a  ret
```
