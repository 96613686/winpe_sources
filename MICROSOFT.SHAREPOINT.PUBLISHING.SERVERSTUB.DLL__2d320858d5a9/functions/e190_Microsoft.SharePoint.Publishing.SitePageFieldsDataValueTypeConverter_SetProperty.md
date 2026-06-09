# Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::SetProperty

- ea: `0xe190`
- end: `0xe2cc`
- name: `Microsoft.SharePoint.Publishing.SitePageFieldsDataValueTypeConverter::SetProperty`
- size: `316`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0xe190`

## string_xrefs

- `0xe20b`: `CanvasJson1`

## pseudocode

```c

```

## disassembly

```asm
0xe190  ldarg.s  4
0xe192  brtrue.s loc_E19F
0xe194  ldstr    aProxycontext// "proxyContext"
0xe199  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe19e  throw
0xe19f  ldarg.1
0xe1a0  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData
0xe1a5  stloc.0
0xe1a6  ldloc.0
0xe1a7  brtrue.s loc_E1B4
0xe1a9  ldstr    aTarget// "target"
0xe1ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe1b3  throw
0xe1b4  ldarg.2
0xe1b5  brtrue.s loc_E1C2
0xe1b7  ldstr    aPropname// "propName"
0xe1bc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe1c1  throw
0xe1c2  ldarg.3
0xe1c3  brtrue.s loc_E1D0
0xe1c5  ldstr    aPropvalue// "propValue"
0xe1ca  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe1cf  throw
0xe1d0  ldarg.0
0xe1d1  ldarg.2
0xe1d2  ldarg.s  4
0xe1d4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe1d9  starg.s  2
0xe1db  ldarg.2
0xe1dc  dup
0xe1dd  stloc.1
0xe1de  brfalse  loc_E2C0
0xe1e3  volatile.
0xe1e5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000287-1
0xe1ea  brtrue.s loc_E241
0xe1ec  ldc.i4.6
0xe1ed  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xe1f2  dup
0xe1f3  ldstr    aBannerimageurl// "BannerImageUrl"
0xe1f8  ldc.i4.0
0xe1f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe1fe  dup
0xe1ff  ldstr    aCanvascontent1// "CanvasContent1"
0xe204  ldc.i4.1
0xe205  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe20a  dup
0xe20b  ldstr    aCanvasjson1// "CanvasJson1"
0xe210  ldc.i4.2
0xe211  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe216  dup
0xe217  ldstr    aLayoutwebparts// "LayoutWebpartsContent"
0xe21c  ldc.i4.3
0xe21d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe222  dup
0xe223  ldstr    aModified// "Modified"
0xe228  ldc.i4.4
0xe229  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe22e  dup
0xe22f  ldstr    aTitle// "Title"
0xe234  ldc.i4.5
0xe235  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xe23a  volatile.
0xe23c  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000287-1
0xe241  volatile.
0xe243  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000287-1
0xe248  ldloc.1
0xe249  ldloca.s 2
0xe24b  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xe250  brfalse.s loc_E2C0
0xe252  ldloc.2
0xe253  switch   loc_E272, loc_E27F, loc_E28C, loc_E299, loc_E2A6, loc_E2B3
0xe270  br.s     loc_E2C0
0xe272  ldloc.0
0xe273  ldarg.3
0xe274  callvirt T0x2B000001
0xe279  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_BannerImageUrl(string)
0xe27e  ret
0xe27f  ldloc.0
0xe280  ldarg.3
0xe281  callvirt T0x2B000001
0xe286  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_CanvasContent1(string)
0xe28b  ret
0xe28c  ldloc.0
0xe28d  ldarg.3
0xe28e  callvirt T0x2B000001
0xe293  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_CanvasJson1(string)
0xe298  ret
0xe299  ldloc.0
0xe29a  ldarg.3
0xe29b  callvirt T0x2B000001
0xe2a0  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_LayoutWebpartsContent(string)
0xe2a5  ret
0xe2a6  ldloc.0
0xe2a7  ldarg.3
0xe2a8  callvirt T0x2B00002B
0xe2ad  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_Modified(valuetype [mscorlib]System.DateTime)
0xe2b2  ret
0xe2b3  ldloc.0
0xe2b4  ldarg.3
0xe2b5  callvirt T0x2B000001
0xe2ba  callvirt instance void [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.SitePageFieldsData::set_Title(string)
0xe2bf  ret
0xe2c0  ldarg.0
0xe2c1  ldarg.1
0xe2c2  ldarg.2
0xe2c3  ldarg.3
0xe2c4  ldarg.s  4
0xe2c6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ValueTypeConverter::SetProperty(object, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientValue, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0xe2cb  ret
```
