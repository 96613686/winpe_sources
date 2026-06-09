# Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::SetProperty

- ea: `0xdc00`
- end: `0xdd97`
- name: `Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::SetProperty`
- size: `407`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xdc00`

## string_xrefs

- `0xdcc4`: `WebRelativeFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xdc00  ldarg.s  4
0xdc02  brtrue.s loc_DC0F
0xdc04  ldstr    aProxycontext// "proxyContext"
0xdc09  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdc0e  throw
0xdc0f  ldarg.1
0xdc10  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo
0xdc15  stloc.0
0xdc16  ldloc.0
0xdc17  brtrue.s loc_DC24
0xdc19  ldstr    aTarget// "target"
0xdc1e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdc23  throw
0xdc24  ldarg.2
0xdc25  brtrue.s loc_DC32
0xdc27  ldstr    aPropname// "propName"
0xdc2c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdc31  throw
0xdc32  ldarg.3
0xdc33  brtrue.s loc_DC40
0xdc35  ldstr    aPropvalue// "propValue"
0xdc3a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdc3f  throw
0xdc40  ldarg.0
0xdc41  ldarg.2
0xdc42  ldarg.s  4
0xdc44  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdc49  starg.s  2
0xdc4b  ldarg.2
0xdc4c  dup
0xdc4d  stloc.1
0xdc4e  brfalse  loc_DD8B
0xdc53  volatile.
0xdc55  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027c-1
0xdc5a  brtrue.s loc_DCD6
0xdc5c  ldc.i4.s 9
0xdc5e  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xdc63  dup
0xdc64  ldstr    aCanvascontent1// "CanvasContent1"
0xdc69  ldc.i4.0
0xdc6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc6f  dup
0xdc70  ldstr    aContenttypeid// "ContentTypeId"
0xdc75  ldc.i4.1
0xdc76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc7b  dup
0xdc7c  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xdc81  ldc.i4.2
0xdc82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc87  dup
0xdc88  ldstr    aName// "Name"
0xdc8d  ldc.i4.3
0xdc8e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc93  dup
0xdc94  ldstr    aPagelayouttype// "PageLayoutType"
0xdc99  ldc.i4.4
0xdc9a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdc9f  dup
0xdca0  ldstr    aPromotedstate_0// "PromotedState"
0xdca5  ldc.i4.5
0xdca6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdcab  dup
0xdcac  ldstr    aSourceitemid// "SourceItemId"
0xdcb1  ldc.i4.6
0xdcb2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdcb7  dup
0xdcb8  ldstr    aTitle// "Title"
0xdcbd  ldc.i4.7
0xdcbe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdcc3  dup
0xdcc4  ldstr    aWebrelativefol// "WebRelativeFolderPath"
0xdcc9  ldc.i4.8
0xdcca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdccf  volatile.
0xdcd1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027c-1
0xdcd6  volatile.
0xdcd8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027c-1
0xdcdd  ldloc.1
0xdcde  ldloca.s 2
0xdce0  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xdce5  brfalse  loc_DD8B
0xdcea  ldloc.2
0xdceb  switch   loc_DD16, loc_DD23, loc_DD30, loc_DD3D, loc_DD4A, loc_DD57, loc_DD64, loc_DD71, loc_DD7E
0xdd14  br.s     loc_DD8B
0xdd16  ldloc.0
0xdd17  ldarg.3
0xdd18  callvirt T0x2B000001
0xdd1d  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_CanvasContent1(string)
0xdd22  ret
0xdd23  ldloc.0
0xdd24  ldarg.3
0xdd25  callvirt T0x2B000001
0xdd2a  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_ContentTypeId(string)
0xdd2f  ret
0xdd30  ldloc.0
0xdd31  ldarg.3
0xdd32  callvirt T0x2B000001
0xdd37  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_LayoutWebpartsContent(string)
0xdd3c  ret
0xdd3d  ldloc.0
0xdd3e  ldarg.3
0xdd3f  callvirt T0x2B000001
0xdd44  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_Name(string)
0xdd49  ret
0xdd4a  ldloc.0
0xdd4b  ldarg.3
0xdd4c  callvirt T0x2B000001
0xdd51  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_PageLayoutType(string)
0xdd56  ret
0xdd57  ldloc.0
0xdd58  ldarg.3
0xdd59  callvirt T0x2B000039
0xdd5e  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_PromotedState(valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState)
0xdd63  ret
0xdd64  ldloc.0
0xdd65  ldarg.3
0xdd66  callvirt T0x2B000002
0xdd6b  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_SourceItemId(int32)
0xdd70  ret
0xdd71  ldloc.0
0xdd72  ldarg.3
0xdd73  callvirt T0x2B000001
0xdd78  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_Title(string)
0xdd7d  ret
0xdd7e  ldloc.0
0xdd7f  ldarg.3
0xdd80  callvirt T0x2B000001
0xdd85  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::set_WebRelativeFolderPath(string)
0xdd8a  ret
0xdd8b  ldarg.0
0xdd8c  ldarg.1
0xdd8d  ldarg.2
0xdd8e  ldarg.3
0xdd8f  ldarg.s  4
0xdd91  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdd96  ret
```
