# System.Web.UI.WebControls.WebParts.WebPartManager::SaveCustomPersonalizationState

- ea: `0x109e60`
- end: `0x10a36a`
- name: `System.Web.UI.WebControls.WebParts.WebPartManager::SaveCustomPersonalizationState`
- size: `1290`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: ``

## callers

- `0x10a530`

## callees

- `0x5f1b0`
- `0x611a0`
- `0x66560`
- `0x665a0`
- `0x66640`
- `0x7fb40`
- `0xf8b70`
- `0xfb9d0`
- `0xfbca0`
- `0xfd8c0`
- `0xfd900`
- `0xfd920`
- `0xfd940`
- `0x100d10`
- `0x100d70`
- `0x100d90`
- `0x100fa0`
- `0x102b80`
- `0x102bb0`
- `0x102c00`
- `0x102c40`
- `0x102cd0`
- `0x102d00`
- `0x102d30`
- `0x104d80`
- `0x104e50`
- `0x104f20`
- `0x104fa0`
- `0x109e60`
- `0x10a780`
- `0x10a7a0`
- `0x10a7d0`
- `0x10bba0`
- `0x10caa0`

## string_xrefs

- `0x10a1ec`: `DeletedConnectionsShared`
- `0x10a201`: `DeletedConnectionsUser`

## pseudocode

```c

```

## disassembly

```asm
0x109e60  ldarg.0
0x109e61  call     instance class System.Web.UI.WebControls.WebParts.WebPartPersonalization System.Web.UI.WebControls.WebParts.WebPartManager::get_Personalization()
0x109e66  callvirt instance valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope System.Web.UI.WebControls.WebParts.WebPartPersonalization::get_Scope()
0x109e6b  stloc.0
0x109e6c  ldarg.0
0x109e6d  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x109e72  callvirt instance int32 System.Web.UI.ControlCollection::get_Count()
0x109e77  stloc.1
0x109e78  ldloc.1
0x109e79  ldc.i4.0
0x109e7a  ble      loc_109F27
0x109e7f  ldloc.1
0x109e80  ldc.i4.4
0x109e81  mul
0x109e82  newarr   [mscorlib]System.Object
0x109e87  stloc.s  8
0x109e89  ldc.i4.0
0x109e8a  stloc.s  9
0x109e8c  br.s     loc_109EF6
0x109e8e  ldarg.0
0x109e8f  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x109e94  ldloc.s  9
0x109e96  callvirt instance class System.Web.UI.Control System.Web.UI.ControlCollection::get_Item(int32 index)
0x109e9b  castclass System.Web.UI.WebControls.WebParts.WebPart
0x109ea0  stloc.s  0xA
0x109ea2  ldloc.s  8
0x109ea4  ldc.i4.4
0x109ea5  ldloc.s  9
0x109ea7  mul
0x109ea8  ldloc.s  0xA
0x109eaa  callvirt instance string System.Web.UI.Control::get_ID()
0x109eaf  stelem.ref
0x109eb0  ldloc.s  8
0x109eb2  ldc.i4.4
0x109eb3  ldloc.s  9
0x109eb5  mul
0x109eb6  ldc.i4.1
0x109eb7  add
0x109eb8  ldarg.0
0x109eb9  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x109ebe  ldloc.s  0xA
0x109ec0  callvirt instance string System.Web.UI.WebControls.WebParts.WebPartManagerInternals::GetZoneID(class System.Web.UI.WebControls.WebParts.WebPart webPart)
0x109ec5  stelem.ref
0x109ec6  ldloc.s  8
0x109ec8  ldc.i4.4
0x109ec9  ldloc.s  9
0x109ecb  mul
0x109ecc  ldc.i4.2
0x109ecd  add
0x109ece  ldloc.s  0xA
0x109ed0  callvirt instance int32 System.Web.UI.WebControls.WebParts.WebPart::get_ZoneIndex()
0x109ed5  box      [mscorlib]System.Int32
0x109eda  stelem.ref
0x109edb  ldloc.s  8
0x109edd  ldc.i4.4
0x109ede  ldloc.s  9
0x109ee0  mul
0x109ee1  ldc.i4.3
0x109ee2  add
0x109ee3  ldloc.s  0xA
0x109ee5  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsClosed()
0x109eea  box      [mscorlib]System.Boolean
0x109eef  stelem.ref
0x109ef0  ldloc.s  9
0x109ef2  ldc.i4.1
0x109ef3  add
0x109ef4  stloc.s  9
0x109ef6  ldloc.s  9
0x109ef8  ldloc.1
0x109ef9  blt.s    loc_109E8E
0x109efb  ldloc.0
0x109efc  ldc.i4.1
0x109efd  bne.un.s loc_109F14
0x109eff  ldarg.1
0x109f00  ldstr    aWebpartstatesh// "WebPartStateShared"
0x109f05  ldloc.s  8
0x109f07  ldc.i4.1
0x109f08  newobj   instance void System.Web.UI.WebControls.WebParts.PersonalizationEntry::.ctor(object value, valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope scope)
0x109f0d  callvirt instance void System.Web.UI.WebControls.WebParts.PersonalizationDictionary::set_Item(string key, class System.Web.UI.WebControls.WebParts.PersonalizationEntry value)
0x109f12  br.s     loc_109F27
0x109f14  ldarg.1
0x109f15  ldstr    aWebpartstateus// "WebPartStateUser"
0x109f1a  ldloc.s  8
0x109f1c  ldc.i4.0
0x109f1d  newobj   instance void System.Web.UI.WebControls.WebParts.PersonalizationEntry::.ctor(object value, valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope scope)
0x109f22  callvirt instance void System.Web.UI.WebControls.WebParts.PersonalizationDictionary::set_Item(string key, class System.Web.UI.WebControls.WebParts.PersonalizationEntry value)
0x109f27  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x109f2c  stloc.2
0x109f2d  ldarg.0
0x109f2e  callvirt instance class System.Web.UI.ControlCollection System.Web.UI.Control::get_Controls()
0x109f33  callvirt instance class [mscorlib]System.Collections.IEnumerator System.Web.UI.ControlCollection::GetEnumerator()
0x109f38  stloc.s  0xB
0x109f3a  br.s     loc_109F75
0x109f3c  ldloc.s  0xB
0x109f3e  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x109f43  castclass System.Web.UI.WebControls.WebParts.WebPart
0x109f48  stloc.s  0xC
0x109f4a  ldloc.s  0xC
0x109f4c  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsStatic()
0x109f51  brtrue.s loc_109F75
0x109f53  ldloc.0
0x109f54  brtrue.s loc_109F5F
0x109f56  ldloc.s  0xC
0x109f58  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsShared()
0x109f5d  brfalse.s loc_109F6C
0x109f5f  ldloc.0
0x109f60  ldc.i4.1
0x109f61  bne.un.s loc_109F75
0x109f63  ldloc.s  0xC
0x109f65  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPart::get_IsShared()
0x109f6a  brfalse.s loc_109F75
0x109f6c  ldloc.2
0x109f6d  ldloc.s  0xC
0x109f6f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x109f74  pop
0x109f75  ldloc.s  0xB
0x109f77  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x109f7c  brtrue.s loc_109F3C
0x109f7e  leave.s  loc_109F95
0x109f80  ldloc.s  0xB
0x109f82  isinst   [mscorlib]System.IDisposable
0x109f87  stloc.s  0xD
0x109f89  ldloc.s  0xD
0x109f8b  brfalse.s loc_109F94
0x109f8d  ldloc.s  0xD
0x109f8f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x109f94  endfinally
0x109f95  ldloc.2
0x109f96  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x109f9b  stloc.3
0x109f9c  ldloc.3
0x109f9d  ldc.i4.0
0x109f9e  ble      loc_10A0EB
0x109fa3  ldloc.3
0x109fa4  ldc.i4.4
0x109fa5  mul
0x109fa6  newarr   [mscorlib]System.Object
0x109fab  stloc.s  0xE
0x109fad  ldc.i4.0
0x109fae  stloc.s  0xF
0x109fb0  br       loc_10A0B7
0x109fb5  ldloc.2
0x109fb6  ldloc.s  0xF
0x109fb8  callvirt instance object [mscorlib]System.Collections.ArrayList::get_Item(int32)
0x109fbd  castclass System.Web.UI.WebControls.WebParts.WebPart
0x109fc2  stloc.s  0x10
0x109fc4  ldnull
0x109fc5  stloc.s  0x13
0x109fc7  ldnull
0x109fc8  stloc.s  0x14
0x109fca  ldloc.s  0x10
0x109fcc  isinst   System.Web.UI.WebControls.WebParts.ProxyWebPart
0x109fd1  stloc.s  0x15
0x109fd3  ldloc.s  0x15
0x109fd5  brfalse.s loc_109FFD
0x109fd7  ldloc.s  0x15
0x109fd9  callvirt instance string System.Web.UI.WebControls.WebParts.ProxyWebPart::get_OriginalID()
0x109fde  stloc.s  0x11
0x109fe0  ldloc.s  0x15
0x109fe2  callvirt instance string System.Web.UI.WebControls.WebParts.ProxyWebPart::get_OriginalTypeName()
0x109fe7  stloc.s  0x12
0x109fe9  ldloc.s  0x15
0x109feb  callvirt instance string System.Web.UI.WebControls.WebParts.ProxyWebPart::get_OriginalPath()
0x109ff0  stloc.s  0x13
0x109ff2  ldloc.s  0x15
0x109ff4  callvirt instance string System.Web.UI.WebControls.WebParts.ProxyWebPart::get_GenericWebPartID()
0x109ff9  stloc.s  0x14
0x109ffb  br.s     loc_10A075
0x109ffd  ldloc.s  0x10
0x109fff  isinst   System.Web.UI.WebControls.WebParts.GenericWebPart
0x10a004  stloc.s  0x16
0x10a006  ldloc.s  0x16
0x10a008  brfalse.s loc_10A05E
0x10a00a  ldloc.s  0x16
0x10a00c  callvirt instance class System.Web.UI.Control System.Web.UI.WebControls.WebParts.GenericWebPart::get_ChildControl()
0x10a011  stloc.s  0x17
0x10a013  ldloc.s  0x17
0x10a015  isinst   System.Web.UI.UserControl
0x10a01a  stloc.s  0x18
0x10a01c  ldloc.s  0x17
0x10a01e  callvirt instance string System.Web.UI.Control::get_ID()
0x10a023  stloc.s  0x11
0x10a025  ldloc.s  0x18
0x10a027  brfalse.s loc_10A045
0x10a029  ldtoken  System.Web.UI.UserControl
0x10a02e  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x10a033  call     string System.Web.UI.WebControls.WebParts.WebPartUtil::SerializeType(class [mscorlib]System.Type type)
0x10a038  stloc.s  0x12
0x10a03a  ldloc.s  0x18
0x10a03c  callvirt instance string System.Web.UI.TemplateControl::get_AppRelativeVirtualPath()
0x10a041  stloc.s  0x13
0x10a043  br.s     loc_10A053
0x10a045  ldloc.s  0x17
0x10a047  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10a04c  call     string System.Web.UI.WebControls.WebParts.WebPartUtil::SerializeType(class [mscorlib]System.Type type)
0x10a051  stloc.s  0x12
0x10a053  ldloc.s  0x16
0x10a055  callvirt instance string System.Web.UI.Control::get_ID()
0x10a05a  stloc.s  0x14
0x10a05c  br.s     loc_10A075
0x10a05e  ldloc.s  0x10
0x10a060  callvirt instance string System.Web.UI.Control::get_ID()
0x10a065  stloc.s  0x11
0x10a067  ldloc.s  0x10
0x10a069  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x10a06e  call     string System.Web.UI.WebControls.WebParts.WebPartUtil::SerializeType(class [mscorlib]System.Type type)
0x10a073  stloc.s  0x12
0x10a075  ldloc.s  0xE
0x10a077  ldc.i4.4
0x10a078  ldloc.s  0xF
0x10a07a  mul
0x10a07b  ldloc.s  0x11
0x10a07d  stelem.ref
0x10a07e  ldloc.s  0xE
0x10a080  ldc.i4.4
0x10a081  ldloc.s  0xF
0x10a083  mul
0x10a084  ldc.i4.1
0x10a085  add
0x10a086  ldloc.s  0x12
0x10a088  stelem.ref
0x10a089  ldloc.s  0x13
0x10a08b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10a090  brtrue.s loc_10A09D
0x10a092  ldloc.s  0xE
0x10a094  ldc.i4.4
0x10a095  ldloc.s  0xF
0x10a097  mul
0x10a098  ldc.i4.2
0x10a099  add
0x10a09a  ldloc.s  0x13
0x10a09c  stelem.ref
0x10a09d  ldloc.s  0x14
0x10a09f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10a0a4  brtrue.s loc_10A0B1
0x10a0a6  ldloc.s  0xE
0x10a0a8  ldc.i4.4
0x10a0a9  ldloc.s  0xF
0x10a0ab  mul
0x10a0ac  ldc.i4.3
0x10a0ad  add
0x10a0ae  ldloc.s  0x14
0x10a0b0  stelem.ref
0x10a0b1  ldloc.s  0xF
0x10a0b3  ldc.i4.1
0x10a0b4  add
0x10a0b5  stloc.s  0xF
0x10a0b7  ldloc.s  0xF
0x10a0b9  ldloc.3
0x10a0ba  blt      loc_109FB5
0x10a0bf  ldloc.0
0x10a0c0  ldc.i4.1
0x10a0c1  bne.un.s loc_10A0D8
0x10a0c3  ldarg.1
0x10a0c4  ldstr    aDynamicwebpart// "DynamicWebPartsShared"
0x10a0c9  ldloc.s  0xE
0x10a0cb  ldc.i4.1
0x10a0cc  newobj   instance void System.Web.UI.WebControls.WebParts.PersonalizationEntry::.ctor(object value, valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope scope)
0x10a0d1  callvirt instance void System.Web.UI.WebControls.WebParts.PersonalizationDictionary::set_Item(string key, class System.Web.UI.WebControls.WebParts.PersonalizationEntry value)
0x10a0d6  br.s     loc_10A0EB
0x10a0d8  ldarg.1
0x10a0d9  ldstr    aDynamicwebpart_0// "DynamicWebPartsUser"
0x10a0de  ldloc.s  0xE
0x10a0e0  ldc.i4.0
0x10a0e1  newobj   instance void System.Web.UI.WebControls.WebParts.PersonalizationEntry::.ctor(object value, valuetype System.Web.UI.WebControls.WebParts.PersonalizationScope scope)
0x10a0e6  callvirt instance void System.Web.UI.WebControls.WebParts.PersonalizationDictionary::set_Item(string key, class System.Web.UI.WebControls.WebParts.PersonalizationEntry value)
0x10a0eb  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x10a0f0  stloc.s  4
0x10a0f2  ldarg.0
0x10a0f3  call     instance class System.Web.UI.WebControls.WebParts.WebPartConnectionCollection System.Web.UI.WebControls.WebParts.WebPartManager::get_StaticConnections()
0x10a0f8  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x10a0fd  stloc.s  0x19
0x10a0ff  br.s     loc_10A128
0x10a101  ldloc.s  0x19
0x10a103  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x10a108  castclass System.Web.UI.WebControls.WebParts.WebPartConnection
0x10a10d  stloc.s  0x1A
0x10a10f  ldarg.0
0x10a110  call     instance class System.Web.UI.WebControls.WebParts.WebPartManagerInternals System.Web.UI.WebControls.WebParts.WebPartManager::get_Internals()
0x10a115  ldloc.s  0x1A
0x10a117  callvirt instance bool System.Web.UI.WebControls.WebParts.WebPartManagerInternals::ConnectionDeleted(class System.Web.UI.WebControls.WebParts.WebPartConnection connection)
0x10a11c  brfalse.s loc_10A128
0x10a11e  ldloc.s  4
0x10a120  ldloc.s  0x1A
0x10a122  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x10a127  pop
0x10a128  ldloc.s  0x19
0x10a12a  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x10a12f  brtrue.s loc_10A101
0x10a131  leave.s  loc_10A148
0x10a133  ldloc.s  0x19
0x10a135  isinst   [mscorlib]System.IDisposable
0x10a13a  stloc.s  0xD
0x10a13c  ldloc.s  0xD
0x10a13e  brfalse.s loc_10A147
0x10a140  ldloc.s  0xD
0x10a142  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x10a147  endfinally
0x10a148  ldarg.0
0x10a149  call     instance class System.Web.UI.WebControls.WebParts.WebPartConnectionCollection System.Web.UI.WebControls.WebParts.WebPartManager::get_DynamicConnections()
  ... truncated ...
```
