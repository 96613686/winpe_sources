# Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::GetProperty

- ea: `0xdaa0`
- end: `0xdbf6`
- name: `Microsoft.SharePoint.Publishing.SitePageCreationInfoValueTypeConverter::GetProperty`
- size: `342`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0xdaa0`

## string_xrefs

- `0xdb54`: `WebRelativeFolderPath`

## pseudocode

```c

```

## disassembly

```asm
0xdaa0  ldarg.3
0xdaa1  brtrue.s loc_DAAE
0xdaa3  ldstr    aProxycontext// "proxyContext"
0xdaa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdaad  throw
0xdaae  ldarg.1
0xdaaf  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo
0xdab4  stloc.0
0xdab5  ldloc.0
0xdab6  brtrue.s loc_DAC3
0xdab8  ldstr    aTarget// "target"
0xdabd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdac2  throw
0xdac3  ldarg.2
0xdac4  brtrue.s loc_DAD1
0xdac6  ldstr    aPropname// "propName"
0xdacb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xdad0  throw
0xdad1  ldarg.0
0xdad2  ldarg.2
0xdad3  ldarg.3
0xdad4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdad9  starg.s  2
0xdadb  ldarg.2
0xdadc  dup
0xdadd  stloc.1
0xdade  brfalse  loc_DBEC
0xdae3  volatile.
0xdae5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027b-1
0xdaea  brtrue.s loc_DB66
0xdaec  ldc.i4.s 9
0xdaee  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xdaf3  dup
0xdaf4  ldstr    aCanvascontent1// "CanvasContent1"
0xdaf9  ldc.i4.0
0xdafa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdaff  dup
0xdb00  ldstr    aContenttypeid// "ContentTypeId"
0xdb05  ldc.i4.1
0xdb06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb0b  dup
0xdb0c  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xdb11  ldc.i4.2
0xdb12  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb17  dup
0xdb18  ldstr    aName// "Name"
0xdb1d  ldc.i4.3
0xdb1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb23  dup
0xdb24  ldstr    aPagelayouttype// "PageLayoutType"
0xdb29  ldc.i4.4
0xdb2a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb2f  dup
0xdb30  ldstr    aPromotedstate_0// "PromotedState"
0xdb35  ldc.i4.5
0xdb36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb3b  dup
0xdb3c  ldstr    aSourceitemid// "SourceItemId"
0xdb41  ldc.i4.6
0xdb42  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb47  dup
0xdb48  ldstr    aTitle// "Title"
0xdb4d  ldc.i4.7
0xdb4e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb53  dup
0xdb54  ldstr    aWebrelativefol// "WebRelativeFolderPath"
0xdb59  ldc.i4.8
0xdb5a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xdb5f  volatile.
0xdb61  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027b-1
0xdb66  volatile.
0xdb68  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x600027b-1
0xdb6d  ldloc.1
0xdb6e  ldloca.s 2
0xdb70  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xdb75  brfalse.s loc_DBEC
0xdb77  ldloc.2
0xdb78  switch   loc_DBA3, loc_DBAA, loc_DBB1, loc_DBB8, loc_DBBF, loc_DBC6, loc_DBD2, loc_DBDE, loc_DBE5
0xdba1  br.s     loc_DBEC
0xdba3  ldloc.0
0xdba4  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_CanvasContent1()
0xdba9  ret
0xdbaa  ldloc.0
0xdbab  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_ContentTypeId()
0xdbb0  ret
0xdbb1  ldloc.0
0xdbb2  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_LayoutWebpartsContent()
0xdbb7  ret
0xdbb8  ldloc.0
0xdbb9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_Name()
0xdbbe  ret
0xdbbf  ldloc.0
0xdbc0  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_PageLayoutType()
0xdbc5  ret
0xdbc6  ldloc.0
0xdbc7  callvirt instance valuetype [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_PromotedState()
0xdbcc  box      [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.PromotedState
0xdbd1  ret
0xdbd2  ldloc.0
0xdbd3  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_SourceItemId()
0xdbd8  box      [mscorlib]System.Int32
0xdbdd  ret
0xdbde  ldloc.0
0xdbdf  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_Title()
0xdbe4  ret
0xdbe5  ldloc.0
0xdbe6  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageCreationInfo::get_WebRelativeFolderPath()
0xdbeb  ret
0xdbec  ldarg.0
0xdbed  ldarg.1
0xdbee  ldarg.2
0xdbef  ldarg.3
0xdbf0  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xdbf5  ret
```
