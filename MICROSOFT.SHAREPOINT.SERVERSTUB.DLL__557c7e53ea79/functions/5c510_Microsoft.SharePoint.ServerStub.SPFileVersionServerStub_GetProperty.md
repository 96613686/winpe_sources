# Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::GetProperty

- ea: `0x5c510`
- end: `0x5c6e7`
- name: `Microsoft.SharePoint.ServerStub.SPFileVersionServerStub::GetProperty`
- size: `471`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x5c510`

## string_xrefs

- `0x5c570`: `Created`
- `0x5c62d`: `Created`
- `0x5c57c`: `CreatedBy`
- `0x5c645`: `CreatedBy`
- `0x5c564`: `CheckInComment`
- `0x5c61a`: `CheckInComment`

## pseudocode

```c

```

## disassembly

```asm
0x5c510  ldarg.2
0x5c511  brtrue.s loc_5C51E
0x5c513  ldstr    aPropname// "propName"
0x5c518  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5c51d  throw
0x5c51e  ldarg.3
0x5c51f  brtrue.s loc_5C52C
0x5c521  ldstr    aProxycontext// "proxyContext"
0x5c526  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5c52b  throw
0x5c52c  ldarg.1
0x5c52d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion
0x5c532  stloc.0
0x5c533  ldloc.0
0x5c534  brtrue.s loc_5C541
0x5c536  ldstr    aTarget// "target"
0x5c53b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5c540  throw
0x5c541  ldarg.0
0x5c542  ldarg.2
0x5c543  ldarg.3
0x5c544  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c549  starg.s  2
0x5c54b  ldarg.2
0x5c54c  dup
0x5c54d  stloc.1
0x5c54e  brfalse  loc_5C6DD
0x5c553  volatile.
0x5c555  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001068-1
0x5c55a  brtrue.s loc_5C5D6
0x5c55c  ldc.i4.s 9
0x5c55e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x5c563  dup
0x5c564  ldstr    aCheckincomment_0// "CheckInComment"
0x5c569  ldc.i4.0
0x5c56a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c56f  dup
0x5c570  ldstr    aCreated// "Created"
0x5c575  ldc.i4.1
0x5c576  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c57b  dup
0x5c57c  ldstr    aCreatedby// "CreatedBy"
0x5c581  ldc.i4.2
0x5c582  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c587  dup
0x5c588  ldstr    aId_1// "ID"
0x5c58d  ldc.i4.3
0x5c58e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c593  dup
0x5c594  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5c599  ldc.i4.4
0x5c59a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c59f  dup
0x5c5a0  ldstr    aLength// "Length"
0x5c5a5  ldc.i4.5
0x5c5a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c5ab  dup
0x5c5ac  ldstr    aSize_0// "Size"
0x5c5b1  ldc.i4.6
0x5c5b2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c5b7  dup
0x5c5b8  ldstr    aUrl// "Url"
0x5c5bd  ldc.i4.7
0x5c5be  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c5c3  dup
0x5c5c4  ldstr    aVersionlabel_0// "VersionLabel"
0x5c5c9  ldc.i4.8
0x5c5ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x5c5cf  volatile.
0x5c5d1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001068-1
0x5c5d6  volatile.
0x5c5d8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6001068-1
0x5c5dd  ldloc.1
0x5c5de  ldloca.s 2
0x5c5e0  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x5c5e5  brfalse  loc_5C6DD
0x5c5ea  ldloc.2
0x5c5eb  switch   loc_5C619, loc_5C62C, loc_5C644, loc_5C657, loc_5C66F, loc_5C687, loc_5C69F, loc_5C6B7, loc_5C6CA
0x5c614  br       loc_5C6DD
0x5c619  ldarg.0
0x5c61a  ldstr    aCheckincomment_0// "CheckInComment"
0x5c61f  ldarg.3
0x5c620  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c625  ldloc.0
0x5c626  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_CheckInComment()
0x5c62b  ret
0x5c62c  ldarg.0
0x5c62d  ldstr    aCreated// "Created"
0x5c632  ldarg.3
0x5c633  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c638  ldloc.0
0x5c639  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Created()
0x5c63e  box      [mscorlib]System.DateTime
0x5c643  ret
0x5c644  ldarg.0
0x5c645  ldstr    aCreatedby// "CreatedBy"
0x5c64a  ldarg.3
0x5c64b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c650  ldloc.0
0x5c651  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_CreatedBy_Client()
0x5c656  ret
0x5c657  ldarg.0
0x5c658  ldstr    aId_1// "ID"
0x5c65d  ldarg.3
0x5c65e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c663  ldloc.0
0x5c664  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_ID()
0x5c669  box      [mscorlib]System.Int32
0x5c66e  ret
0x5c66f  ldarg.0
0x5c670  ldstr    aIscurrentversi// "IsCurrentVersion"
0x5c675  ldarg.3
0x5c676  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c67b  ldloc.0
0x5c67c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_IsCurrentVersion()
0x5c681  box      [mscorlib]System.Boolean
0x5c686  ret
0x5c687  ldarg.0
0x5c688  ldstr    aLength// "Length"
0x5c68d  ldarg.3
0x5c68e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c693  ldloc.0
0x5c694  callvirt instance int64 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Length()
0x5c699  box      [mscorlib]System.Int64
0x5c69e  ret
0x5c69f  ldarg.0
0x5c6a0  ldstr    aSize_0// "Size"
0x5c6a5  ldarg.3
0x5c6a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c6ab  ldloc.0
0x5c6ac  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Size_Client()
0x5c6b1  box      [mscorlib]System.Int32
0x5c6b6  ret
0x5c6b7  ldarg.0
0x5c6b8  ldstr    aUrl// "Url"
0x5c6bd  ldarg.3
0x5c6be  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c6c3  ldloc.0
0x5c6c4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_Url()
0x5c6c9  ret
0x5c6ca  ldarg.0
0x5c6cb  ldstr    aVersionlabel_0// "VersionLabel"
0x5c6d0  ldarg.3
0x5c6d1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c6d6  ldloc.0
0x5c6d7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPFileVersion::get_VersionLabel()
0x5c6dc  ret
0x5c6dd  ldarg.0
0x5c6de  ldarg.1
0x5c6df  ldarg.2
0x5c6e0  ldarg.3
0x5c6e1  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x5c6e6  ret
```
