# Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::GetProperty

- ea: `0x71d70`
- end: `0x7206a`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::GetProperty`
- size: `762`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x71d70`

## string_xrefs

- `0x71deb`: `DeletedBy`
- `0x71f3e`: `DeletedBy`
- `0x71df7`: `DeletedByEmail`
- `0x71f51`: `DeletedByEmail`
- `0x71e03`: `DeletedByName`
- `0x71f64`: `DeletedByName`
- `0x71e0f`: `DeletedDate`
- `0x71f77`: `DeletedDate`
- `0x71e1b`: `DeletedDateLocalFormatted`
- `0x71f8f`: `DeletedDateLocalFormatted`
- `0x71e33`: `DirNamePath`
- `0x71fb5`: `DirNamePath`
- `0x71e74`: `LeafNamePath`
- `0x72023`: `LeafNamePath`

## pseudocode

```c

```

## disassembly

```asm
0x71d70  ldarg.2
0x71d71  brtrue.s loc_71D7E
0x71d73  ldstr    aPropname// "propName"
0x71d78  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71d7d  throw
0x71d7e  ldarg.3
0x71d7f  brtrue.s loc_71D8C
0x71d81  ldstr    aProxycontext// "proxyContext"
0x71d86  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71d8b  throw
0x71d8c  ldarg.1
0x71d8d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem
0x71d92  stloc.0
0x71d93  ldloc.0
0x71d94  brtrue.s loc_71DA1
0x71d96  ldstr    aTarget// "target"
0x71d9b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x71da0  throw
0x71da1  ldarg.0
0x71da2  ldarg.2
0x71da3  ldarg.3
0x71da4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71da9  starg.s  2
0x71dab  ldarg.2
0x71dac  dup
0x71dad  stloc.1
0x71dae  brfalse  loc_72060
0x71db3  volatile.
0x71db5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013e8-1
0x71dba  brtrue   loc_71EA1
0x71dbf  ldc.i4.s 0x11
0x71dc1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x71dc6  dup
0x71dc7  ldstr    aAuthor_0// "Author"
0x71dcc  ldc.i4.0
0x71dcd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71dd2  dup
0x71dd3  ldstr    aAuthoremail// "AuthorEmail"
0x71dd8  ldc.i4.1
0x71dd9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71dde  dup
0x71ddf  ldstr    aAuthorname// "AuthorName"
0x71de4  ldc.i4.2
0x71de5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71dea  dup
0x71deb  ldstr    aDeletedby// "DeletedBy"
0x71df0  ldc.i4.3
0x71df1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71df6  dup
0x71df7  ldstr    aDeletedbyemail// "DeletedByEmail"
0x71dfc  ldc.i4.4
0x71dfd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e02  dup
0x71e03  ldstr    aDeletedbyname// "DeletedByName"
0x71e08  ldc.i4.5
0x71e09  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e0e  dup
0x71e0f  ldstr    aDeleteddate// "DeletedDate"
0x71e14  ldc.i4.6
0x71e15  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e1a  dup
0x71e1b  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x71e20  ldc.i4.7
0x71e21  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e26  dup
0x71e27  ldstr    aDirname// "DirName"
0x71e2c  ldc.i4.8
0x71e2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e32  dup
0x71e33  ldstr    aDirnamepath// "DirNamePath"
0x71e38  ldc.i4.s 9
0x71e3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e3f  dup
0x71e40  ldstr    aId_0// "Id"
0x71e45  ldc.i4.s 0xA
0x71e47  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e4c  dup
0x71e4d  ldstr    aItemstate// "ItemState"
0x71e52  ldc.i4.s 0xB
0x71e54  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e59  dup
0x71e5a  ldstr    aItemtype// "ItemType"
0x71e5f  ldc.i4.s 0xC
0x71e61  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e66  dup
0x71e67  ldstr    aLeafname_0// "LeafName"
0x71e6c  ldc.i4.s 0xD
0x71e6e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e73  dup
0x71e74  ldstr    aLeafnamepath// "LeafNamePath"
0x71e79  ldc.i4.s 0xE
0x71e7b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e80  dup
0x71e81  ldstr    aSize_0// "Size"
0x71e86  ldc.i4.s 0xF
0x71e88  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e8d  dup
0x71e8e  ldstr    aTitle// "Title"
0x71e93  ldc.i4.s 0x10
0x71e95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x71e9a  volatile.
0x71e9c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013e8-1
0x71ea1  volatile.
0x71ea3  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013e8-1
0x71ea8  ldloc.1
0x71ea9  ldloca.s 2
0x71eab  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x71eb0  brfalse  loc_72060
0x71eb5  ldloc.2
0x71eb6  switch   loc_71F04, loc_71F17, loc_71F2A, loc_71F3D, loc_71F50, loc_71F63, loc_71F76, loc_71F8E, loc_71FA1, loc_71FB4, loc_71FC7, loc_71FDF, loc_71FF7, loc_7200F, loc_72022, loc_72035, loc_7204D
0x71eff  br       loc_72060
0x71f04  ldarg.0
0x71f05  ldstr    aAuthor_0// "Author"
0x71f0a  ldarg.3
0x71f0b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f10  ldloc.0
0x71f11  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Author()
0x71f16  ret
0x71f17  ldarg.0
0x71f18  ldstr    aAuthoremail// "AuthorEmail"
0x71f1d  ldarg.3
0x71f1e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f23  ldloc.0
0x71f24  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorEmail()
0x71f29  ret
0x71f2a  ldarg.0
0x71f2b  ldstr    aAuthorname// "AuthorName"
0x71f30  ldarg.3
0x71f31  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f36  ldloc.0
0x71f37  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorName()
0x71f3c  ret
0x71f3d  ldarg.0
0x71f3e  ldstr    aDeletedby// "DeletedBy"
0x71f43  ldarg.3
0x71f44  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f49  ldloc.0
0x71f4a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedBy()
0x71f4f  ret
0x71f50  ldarg.0
0x71f51  ldstr    aDeletedbyemail// "DeletedByEmail"
0x71f56  ldarg.3
0x71f57  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f5c  ldloc.0
0x71f5d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByEmail()
0x71f62  ret
0x71f63  ldarg.0
0x71f64  ldstr    aDeletedbyname// "DeletedByName"
0x71f69  ldarg.3
0x71f6a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f6f  ldloc.0
0x71f70  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByName()
0x71f75  ret
0x71f76  ldarg.0
0x71f77  ldstr    aDeleteddate// "DeletedDate"
0x71f7c  ldarg.3
0x71f7d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f82  ldloc.0
0x71f83  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedDate()
0x71f88  box      [mscorlib]System.DateTime
0x71f8d  ret
0x71f8e  ldarg.0
0x71f8f  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x71f94  ldarg.3
0x71f95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71f9a  ldloc.0
0x71f9b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedDateLocalFormatted()
0x71fa0  ret
0x71fa1  ldarg.0
0x71fa2  ldstr    aDirname// "DirName"
0x71fa7  ldarg.3
0x71fa8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71fad  ldloc.0
0x71fae  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DirName()
0x71fb3  ret
0x71fb4  ldarg.0
0x71fb5  ldstr    aDirnamepath// "DirNamePath"
0x71fba  ldarg.3
0x71fbb  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71fc0  ldloc.0
0x71fc1  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DirNamePath()
0x71fc6  ret
0x71fc7  ldarg.0
0x71fc8  ldstr    aId_0// "Id"
0x71fcd  ldarg.3
0x71fce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71fd3  ldloc.0
0x71fd4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ID()
0x71fd9  box      [mscorlib]System.Guid
0x71fde  ret
0x71fdf  ldarg.0
0x71fe0  ldstr    aItemstate// "ItemState"
0x71fe5  ldarg.3
0x71fe6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x71feb  ldloc.0
0x71fec  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemState [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ItemState()
0x71ff1  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemState
0x71ff6  ret
0x71ff7  ldarg.0
0x71ff8  ldstr    aItemtype// "ItemType"
0x71ffd  ldarg.3
0x71ffe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72003  ldloc.0
0x72004  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemType [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_ItemType()
0x72009  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItemType
0x7200e  ret
0x7200f  ldarg.0
0x72010  ldstr    aLeafname_0// "LeafName"
0x72015  ldarg.3
0x72016  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7201b  ldloc.0
0x7201c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_LeafName()
0x72021  ret
0x72022  ldarg.0
0x72023  ldstr    aLeafnamepath// "LeafNamePath"
0x72028  ldarg.3
0x72029  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7202e  ldloc.0
0x7202f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPResourcePath [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_LeafNamePath()
0x72034  ret
0x72035  ldarg.0
0x72036  ldstr    aSize_0// "Size"
0x7203b  ldarg.3
0x7203c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72041  ldloc.0
0x72042  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Size()
0x72047  box      [mscorlib]System.Int64
0x7204c  ret
0x7204d  ldarg.0
0x7204e  ldstr    aTitle// "Title"
0x72053  ldarg.3
0x72054  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72059  ldloc.0
0x7205a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Title()
0x7205f  ret
0x72060  ldarg.0
0x72061  ldarg.1
0x72062  ldarg.2
0x72063  ldarg.3
0x72064  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72069  ret
```
