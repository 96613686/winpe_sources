# Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::GetProperty

- ea: `0xe080`
- end: `0xe18b`
- name: `Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::GetProperty`
- size: `267`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe080`

## string_xrefs

- `0xe0eb`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0xe080  ldarg.3
0xe081  brtrue.s loc_E08E
0xe083  ldstr    aProxycontext// "proxyContext"
0xe088  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe08d  throw
0xe08e  ldarg.1
0xe08f  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData
0xe094  stloc.0
0xe095  ldloc.0
0xe096  brtrue.s loc_E0A3
0xe098  ldstr    aTarget// "target"
0xe09d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe0a2  throw
0xe0a3  ldarg.2
0xe0a4  brtrue.s loc_E0B1
0xe0a6  ldstr    aPropname// "propName"
0xe0ab  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe0b0  throw
0xe0b1  ldarg.0
0xe0b2  ldarg.2
0xe0b3  ldarg.3
0xe0b4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe0b9  starg.s  2
0xe0bb  ldarg.2
0xe0bc  dup
0xe0bd  stloc.1
0xe0be  brfalse  loc_E181
0xe0c3  volatile.
0xe0c5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000286-1
0xe0ca  brtrue.s loc_E121
0xe0cc  ldc.i4.6
0xe0cd  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xe0d2  dup
0xe0d3  ldstr    aBannerimageurl// "BannerImageUrl"
0xe0d8  ldc.i4.0
0xe0d9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe0de  dup
0xe0df  ldstr    aCanvascontent1// "CanvasContent1"
0xe0e4  ldc.i4.1
0xe0e5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe0ea  dup
0xe0eb  ldstr    aCanvasjson1// "CanvasJson1"
0xe0f0  ldc.i4.2
0xe0f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe0f6  dup
0xe0f7  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xe0fc  ldc.i4.3
0xe0fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe102  dup
0xe103  ldstr    aModified// "Modified"
0xe108  ldc.i4.4
0xe109  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe10e  dup
0xe10f  ldstr    aTitle// "Title"
0xe114  ldc.i4.5
0xe115  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe11a  volatile.
0xe11c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000286-1
0xe121  volatile.
0xe123  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000286-1
0xe128  ldloc.1
0xe129  ldloca.s 2
0xe12b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xe130  brfalse.s loc_E181
0xe132  ldloc.2
0xe133  switch   loc_E152, loc_E159, loc_E160, loc_E167, loc_E16E, loc_E17A
0xe150  br.s     loc_E181
0xe152  ldloc.0
0xe153  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_BannerImageUrl()
0xe158  ret
0xe159  ldloc.0
0xe15a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_CanvasContent1()
0xe15f  ret
0xe160  ldloc.0
0xe161  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_CanvasJson1()
0xe166  ret
0xe167  ldloc.0
0xe168  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_LayoutWebpartsContent()
0xe16d  ret
0xe16e  ldloc.0
0xe16f  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_Modified()
0xe174  box      [mscorlib]System.DateTime
0xe179  ret
0xe17a  ldloc.0
0xe17b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::get_Title()
0xe180  ret
0xe181  ldarg.0
0xe182  ldarg.1
0xe183  ldarg.2
0xe184  ldarg.3
0xe185  call     instance object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe18a  ret
```
