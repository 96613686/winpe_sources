# Microsoft.SharePoint.ServerStub.SPFolderServerStub::WriteOnePropertyValueAsJson

- ea: `0x5e670`
- end: `0x5ee19`
- name: `Microsoft.SharePoint.ServerStub.SPFolderServerStub::WriteOnePropertyValueAsJson`
- size: `1961`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x5e670`

## string_xrefs

- `0x5e72e`: `ServerRelativePath`
- `0x5eb92`: `ServerRelativePath`
- `0x5e762`: `TimeCreated`
- `0x5ecc8`: `TimeCreated`
- `0x5e796`: `WelcomePage`
- `0x5eded`: `WelcomePage`

## pseudocode

```c

```

## disassembly

```asm
0x5e670  ldc.i4.0
0x5e671  stloc.0
0x5e672  ldarg.2
0x5e673  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder
0x5e678  stloc.1
0x5e679  ldloc.1
0x5e67a  brtrue.s loc_5E687
0x5e67c  ldstr    aTarget// "target"
0x5e681  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5e686  throw
0x5e687  ldarg.3
0x5e688  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x5e68d  dup
0x5e68e  stloc.2
0x5e68f  brfalse  loc_5EE0B
0x5e694  volatile.
0x5e696  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010cd-1
0x5e69b  brtrue   loc_5E7A9
0x5e6a0  ldc.i4.s 0x14
0x5e6a2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5e6a7  dup
0x5e6a8  ldstr    aActivities// "Activities"
0x5e6ad  ldc.i4.0
0x5e6ae  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6b3  dup
0x5e6b4  ldstr    aContenttypeord// "ContentTypeOrder"
0x5e6b9  ldc.i4.1
0x5e6ba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6bf  dup
0x5e6c0  ldstr    aExists// "Exists"
0x5e6c5  ldc.i4.2
0x5e6c6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6cb  dup
0x5e6cc  ldstr    aFiles// "Files"
0x5e6d1  ldc.i4.3
0x5e6d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6d7  dup
0x5e6d8  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5e6dd  ldc.i4.4
0x5e6de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6e3  dup
0x5e6e4  ldstr    aListitemallfie// "ListItemAllFields"
0x5e6e9  ldc.i4.5
0x5e6ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6ef  dup
0x5e6f0  ldstr    aItemcount// "ItemCount"
0x5e6f5  ldc.i4.6
0x5e6f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e6fb  dup
0x5e6fc  ldstr    aName// "Name"
0x5e701  ldc.i4.7
0x5e702  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e707  dup
0x5e708  ldstr    aParentfolder// "ParentFolder"
0x5e70d  ldc.i4.8
0x5e70e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e713  dup
0x5e714  ldstr    aProgid// "ProgID"
0x5e719  ldc.i4.s 9
0x5e71b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e720  dup
0x5e721  ldstr    aProperties// "Properties"
0x5e726  ldc.i4.s 0xA
0x5e728  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e72d  dup
0x5e72e  ldstr    aServerrelative_0// "ServerRelativePath"
0x5e733  ldc.i4.s 0xB
0x5e735  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e73a  dup
0x5e73b  ldstr    aServerrelative_1// "ServerRelativeUrl"
0x5e740  ldc.i4.s 0xC
0x5e742  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e747  dup
0x5e748  ldstr    aStoragemetrics// "StorageMetrics"
0x5e74d  ldc.i4.s 0xD
0x5e74f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e754  dup
0x5e755  ldstr    aFolders// "Folders"
0x5e75a  ldc.i4.s 0xE
0x5e75c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e761  dup
0x5e762  ldstr    aTimecreated// "TimeCreated"
0x5e767  ldc.i4.s 0xF
0x5e769  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e76e  dup
0x5e76f  ldstr    aTimelastmodifi// "TimeLastModified"
0x5e774  ldc.i4.s 0x10
0x5e776  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e77b  dup
0x5e77c  ldstr    aUniquecontentt// "UniqueContentTypeOrder"
0x5e781  ldc.i4.s 0x11
0x5e783  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e788  dup
0x5e789  ldstr    aUniqueid_0// "UniqueId"
0x5e78e  ldc.i4.s 0x12
0x5e790  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e795  dup
0x5e796  ldstr    aWelcomepage// "WelcomePage"
0x5e79b  ldc.i4.s 0x13
0x5e79d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5e7a2  volatile.
0x5e7a4  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010cd-1
0x5e7a9  volatile.
0x5e7ab  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60010cd-1
0x5e7b0  ldloc.2
0x5e7b1  ldloca.s 3
0x5e7b3  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5e7b8  brfalse  loc_5EE0B
0x5e7bd  ldloc.3
0x5e7be  switch   loc_5E818, loc_5E869, loc_5E8B3, loc_5E8FD, loc_5E94E, loc_5E998, loc_5E9E9, loc_5EA33, loc_5EA7D, loc_5EACE, loc_5EB18, loc_5EB69, loc_5EBB3, loc_5EBFD, loc_5EC4E, loc_5EC9F, loc_5ECE9, loc_5ED33, loc_5ED7D, loc_5EDC4
0x5e813  br       loc_5EE0B
0x5e818  ldarg.3
0x5e819  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e81e  stloc.s  4
0x5e820  ldloca.s 4
0x5e822  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e827  brfalse.s loc_5E840
0x5e829  ldarg.3
0x5e82a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e82f  stloc.s  5
0x5e831  ldloca.s 5
0x5e833  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e838  brfalse.s loc_5E840
0x5e83a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e83f  throw
0x5e840  ldarg.0
0x5e841  ldstr    aActivities// "Activities"
0x5e846  ldarg.s  4
0x5e848  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e84d  ldc.i4.1
0x5e84e  stloc.0
0x5e84f  ldarg.0
0x5e850  ldarg.1
0x5e851  ldloc.1
0x5e852  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Activities.SPActivityEntitySet [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Activities()
0x5e857  ldarg.3
0x5e858  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5e85d  ldarg.s  4
0x5e85f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e864  br       loc_5EE17
0x5e869  ldarg.3
0x5e86a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e86f  stloc.s  6
0x5e871  ldloca.s 6
0x5e873  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e878  brfalse.s loc_5E891
0x5e87a  ldarg.3
0x5e87b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e880  stloc.s  7
0x5e882  ldloca.s 7
0x5e884  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e889  brtrue.s loc_5E891
0x5e88b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e890  throw
0x5e891  ldarg.0
0x5e892  ldstr    aContenttypeord// "ContentTypeOrder"
0x5e897  ldarg.s  4
0x5e899  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e89e  ldc.i4.1
0x5e89f  stloc.0
0x5e8a0  ldarg.1
0x5e8a1  ldloc.1
0x5e8a2  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId> [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ContentTypeOrder_Client()
0x5e8a7  ldarg.s  4
0x5e8a9  call     T0x2B0001C7
0x5e8ae  br       loc_5EE17
0x5e8b3  ldarg.3
0x5e8b4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e8b9  stloc.s  8
0x5e8bb  ldloca.s 8
0x5e8bd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e8c2  brfalse.s loc_5E8DB
0x5e8c4  ldarg.3
0x5e8c5  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e8ca  stloc.s  9
0x5e8cc  ldloca.s 9
0x5e8ce  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e8d3  brtrue.s loc_5E8DB
0x5e8d5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e8da  throw
0x5e8db  ldarg.0
0x5e8dc  ldstr    aExists// "Exists"
0x5e8e1  ldarg.s  4
0x5e8e3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e8e8  ldc.i4.1
0x5e8e9  stloc.0
0x5e8ea  ldarg.1
0x5e8eb  ldloc.1
0x5e8ec  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Exists()
0x5e8f1  ldarg.s  4
0x5e8f3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e8f8  br       loc_5EE17
0x5e8fd  ldarg.3
0x5e8fe  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e903  stloc.s  0xA
0x5e905  ldloca.s 0xA
0x5e907  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e90c  brfalse.s loc_5E925
0x5e90e  ldarg.3
0x5e90f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e914  stloc.s  0xB
0x5e916  ldloca.s 0xB
0x5e918  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e91d  brfalse.s loc_5E925
0x5e91f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e924  throw
0x5e925  ldarg.0
0x5e926  ldstr    aFiles// "Files"
0x5e92b  ldarg.s  4
0x5e92d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e932  ldc.i4.1
0x5e933  stloc.0
0x5e934  ldarg.0
0x5e935  ldarg.1
0x5e936  ldloc.1
0x5e937  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFileCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Files()
0x5e93c  ldarg.3
0x5e93d  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5e942  ldarg.s  4
0x5e944  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e949  br       loc_5EE17
0x5e94e  ldarg.3
0x5e94f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e954  stloc.s  0xC
0x5e956  ldloca.s 0xC
0x5e958  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e95d  brfalse.s loc_5E976
0x5e95f  ldarg.3
0x5e960  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e965  stloc.s  0xD
0x5e967  ldloca.s 0xD
0x5e969  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e96e  brtrue.s loc_5E976
0x5e970  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e975  throw
0x5e976  ldarg.0
0x5e977  ldstr    aIswopienabled// "IsWOPIEnabled"
0x5e97c  ldarg.s  4
0x5e97e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e983  ldc.i4.1
0x5e984  stloc.0
0x5e985  ldarg.1
0x5e986  ldloc.1
0x5e987  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_IsWOPIEnabled()
0x5e98c  ldarg.s  4
0x5e98e  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e993  br       loc_5EE17
0x5e998  ldarg.3
0x5e999  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e99e  stloc.s  0xE
0x5e9a0  ldloca.s 0xE
0x5e9a2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e9a7  brfalse.s loc_5E9C0
0x5e9a9  ldarg.3
0x5e9aa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e9af  stloc.s  0xF
0x5e9b1  ldloca.s 0xF
0x5e9b3  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5e9b8  brfalse.s loc_5E9C0
0x5e9ba  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5e9bf  throw
0x5e9c0  ldarg.0
0x5e9c1  ldstr    aListitemallfie// "ListItemAllFields"
0x5e9c6  ldarg.s  4
0x5e9c8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e9cd  ldc.i4.1
0x5e9ce  stloc.0
0x5e9cf  ldarg.0
0x5e9d0  ldarg.1
0x5e9d1  ldloc.1
0x5e9d2  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPListItem [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_Item()
0x5e9d7  ldarg.3
0x5e9d8  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x5e9dd  ldarg.s  4
0x5e9df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5e9e4  br       loc_5EE17
0x5e9e9  ldarg.3
0x5e9ea  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5e9ef  stloc.s  0x10
0x5e9f1  ldloca.s 0x10
0x5e9f3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x5e9f8  brfalse.s loc_5EA11
0x5e9fa  ldarg.3
0x5e9fb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x5ea00  stloc.s  0x11
0x5ea02  ldloca.s 0x11
0x5ea04  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x5ea09  brtrue.s loc_5EA11
0x5ea0b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x5ea10  throw
0x5ea11  ldarg.0
0x5ea12  ldstr    aItemcount// "ItemCount"
0x5ea17  ldarg.s  4
0x5ea19  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5ea1e  ldc.i4.1
0x5ea1f  stloc.0
0x5ea20  ldarg.1
0x5ea21  ldloc.1
0x5ea22  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFolder::get_ItemCount()
0x5ea27  ldarg.s  4
  ... truncated ...
```
