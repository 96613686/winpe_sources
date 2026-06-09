# Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::WriteOnePropertyValueAsJson

- ea: `0x8ad0`
- end: `0x8e01`
- name: `Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetViewServerStub::WriteOnePropertyValueAsJson`
- size: `817`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8ad0`

## pseudocode

```c

```

## disassembly

```asm
0x8ad0  ldc.i4.0
0x8ad1  stloc.0
0x8ad2  ldarg.2
0x8ad3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView
0x8ad8  stloc.1
0x8ad9  ldloc.1
0x8ada  brtrue.s loc_8AE7
0x8adc  ldstr    aTarget// "target"
0x8ae1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8ae6  throw
0x8ae7  ldarg.3
0x8ae8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x8aed  dup
0x8aee  stloc.2
0x8aef  brfalse  loc_8DF3
0x8af4  volatile.
0x8af6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000150-1
0x8afb  brtrue.s loc_8B6A
0x8afd  ldc.i4.8
0x8afe  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x8b03  dup
0x8b04  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8b09  ldc.i4.0
0x8b0a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b0f  dup
0x8b10  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8b15  ldc.i4.1
0x8b16  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b1b  dup
0x8b1c  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8b21  ldc.i4.2
0x8b22  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b27  dup
0x8b28  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8b2d  ldc.i4.3
0x8b2e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b33  dup
0x8b34  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8b39  ldc.i4.4
0x8b3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b3f  dup
0x8b40  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8b45  ldc.i4.5
0x8b46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b4b  dup
0x8b4c  ldstr    aWebid// "WebId"
0x8b51  ldc.i4.6
0x8b52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b57  dup
0x8b58  ldstr    aWebtitle// "WebTitle"
0x8b5d  ldc.i4.7
0x8b5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x8b63  volatile.
0x8b65  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000150-1
0x8b6a  volatile.
0x8b6c  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000150-1
0x8b71  ldloc.2
0x8b72  ldloca.s 3
0x8b74  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x8b79  brfalse  loc_8DF3
0x8b7e  ldloc.3
0x8b7f  switch   loc_8BA9, loc_8BF3, loc_8C3D, loc_8C87, loc_8CD1, loc_8D1B, loc_8D65, loc_8DAC
0x8ba4  br       loc_8DF3
0x8ba9  ldarg.3
0x8baa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8baf  stloc.s  4
0x8bb1  ldloca.s 4
0x8bb3  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8bb8  brfalse.s loc_8BD1
0x8bba  ldarg.3
0x8bbb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8bc0  stloc.s  5
0x8bc2  ldloca.s 5
0x8bc4  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8bc9  brtrue.s loc_8BD1
0x8bcb  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8bd0  throw
0x8bd1  ldarg.0
0x8bd2  ldstr    aExcludedepreca// "ExcludeDeprecatedTerms"
0x8bd7  ldarg.s  4
0x8bd9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bde  ldc.i4.1
0x8bdf  stloc.0
0x8be0  ldarg.1
0x8be1  ldloc.1
0x8be2  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeDeprecatedTerms()
0x8be7  ldarg.s  4
0x8be9  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8bee  br       loc_8DFF
0x8bf3  ldarg.3
0x8bf4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8bf9  stloc.s  6
0x8bfb  ldloca.s 6
0x8bfd  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8c02  brfalse.s loc_8C1B
0x8c04  ldarg.3
0x8c05  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8c0a  stloc.s  7
0x8c0c  ldloca.s 7
0x8c0e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8c13  brtrue.s loc_8C1B
0x8c15  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8c1a  throw
0x8c1b  ldarg.0
0x8c1c  ldstr    aExcludetermsby// "ExcludeTermsByPermissions"
0x8c21  ldarg.s  4
0x8c23  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c28  ldc.i4.1
0x8c29  stloc.0
0x8c2a  ldarg.1
0x8c2b  ldloc.1
0x8c2c  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeTermsByPermissions()
0x8c31  ldarg.s  4
0x8c33  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c38  br       loc_8DFF
0x8c3d  ldarg.3
0x8c3e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8c43  stloc.s  8
0x8c45  ldloca.s 8
0x8c47  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8c4c  brfalse.s loc_8C65
0x8c4e  ldarg.3
0x8c4f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8c54  stloc.s  9
0x8c56  ldloca.s 9
0x8c58  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8c5d  brtrue.s loc_8C65
0x8c5f  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8c64  throw
0x8c65  ldarg.0
0x8c66  ldstr    aExcludetermsby_0// "ExcludeTermsByProvider"
0x8c6b  ldarg.s  4
0x8c6d  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c72  ldc.i4.1
0x8c73  stloc.0
0x8c74  ldarg.1
0x8c75  ldloc.1
0x8c76  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ExcludeTermsByProvider()
0x8c7b  ldarg.s  4
0x8c7d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8c82  br       loc_8DFF
0x8c87  ldarg.3
0x8c88  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8c8d  stloc.s  0xA
0x8c8f  ldloca.s 0xA
0x8c91  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8c96  brfalse.s loc_8CAF
0x8c98  ldarg.3
0x8c99  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8c9e  stloc.s  0xB
0x8ca0  ldloca.s 0xB
0x8ca2  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8ca7  brtrue.s loc_8CAF
0x8ca9  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8cae  throw
0x8caf  ldarg.0
0x8cb0  ldstr    aServerrelative// "ServerRelativeSiteUrl"
0x8cb5  ldarg.s  4
0x8cb7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8cbc  ldc.i4.1
0x8cbd  stloc.0
0x8cbe  ldarg.1
0x8cbf  ldloc.1
0x8cc0  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ServerRelativeSiteUrl()
0x8cc5  ldarg.s  4
0x8cc7  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8ccc  br       loc_8DFF
0x8cd1  ldarg.3
0x8cd2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8cd7  stloc.s  0xC
0x8cd9  ldloca.s 0xC
0x8cdb  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8ce0  brfalse.s loc_8CF9
0x8ce2  ldarg.3
0x8ce3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8ce8  stloc.s  0xD
0x8cea  ldloca.s 0xD
0x8cec  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8cf1  brtrue.s loc_8CF9
0x8cf3  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8cf8  throw
0x8cf9  ldarg.0
0x8cfa  ldstr    aServerrelative_0// "ServerRelativeWebUrl"
0x8cff  ldarg.s  4
0x8d01  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d06  ldc.i4.1
0x8d07  stloc.0
0x8d08  ldarg.1
0x8d09  ldloc.1
0x8d0a  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_ServerRelativeWebUrl()
0x8d0f  ldarg.s  4
0x8d11  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d16  br       loc_8DFF
0x8d1b  ldarg.3
0x8d1c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d21  stloc.s  0xE
0x8d23  ldloca.s 0xE
0x8d25  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d2a  brfalse.s loc_8D43
0x8d2c  ldarg.3
0x8d2d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d32  stloc.s  0xF
0x8d34  ldloca.s 0xF
0x8d36  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d3b  brtrue.s loc_8D43
0x8d3d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d42  throw
0x8d43  ldarg.0
0x8d44  ldstr    aSitemapprovide_0// "SiteMapProviderName"
0x8d49  ldarg.s  4
0x8d4b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d50  ldc.i4.1
0x8d51  stloc.0
0x8d52  ldarg.1
0x8d53  ldloc.1
0x8d54  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_SiteMapProviderName()
0x8d59  ldarg.s  4
0x8d5b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d60  br       loc_8DFF
0x8d65  ldarg.3
0x8d66  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d6b  stloc.s  0x10
0x8d6d  ldloca.s 0x10
0x8d6f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8d74  brfalse.s loc_8D8D
0x8d76  ldarg.3
0x8d77  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8d7c  stloc.s  0x11
0x8d7e  ldloca.s 0x11
0x8d80  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8d85  brtrue.s loc_8D8D
0x8d87  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8d8c  throw
0x8d8d  ldarg.0
0x8d8e  ldstr    aWebid// "WebId"
0x8d93  ldarg.s  4
0x8d95  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8d9a  ldc.i4.1
0x8d9b  stloc.0
0x8d9c  ldarg.1
0x8d9d  ldloc.1
0x8d9e  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_WebId()
0x8da3  ldarg.s  4
0x8da5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8daa  br.s     loc_8DFF
0x8dac  ldarg.3
0x8dad  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8db2  stloc.s  0x12
0x8db4  ldloca.s 0x12
0x8db6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x8dbb  brfalse.s loc_8DD4
0x8dbd  ldarg.3
0x8dbe  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x8dc3  stloc.s  0x13
0x8dc5  ldloca.s 0x13
0x8dc7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x8dcc  brtrue.s loc_8DD4
0x8dce  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x8dd3  throw
0x8dd4  ldarg.0
0x8dd5  ldstr    aWebtitle// "WebTitle"
0x8dda  ldarg.s  4
0x8ddc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8de1  ldc.i4.1
0x8de2  stloc.0
0x8de3  ldarg.1
0x8de4  ldloc.1
0x8de5  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.Navigation.NavigationTermSetView::get_WebTitle()
0x8dea  ldarg.s  4
0x8dec  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8df1  br.s     loc_8DFF
0x8df3  ldarg.0
0x8df4  ldarg.1
0x8df5  ldarg.2
0x8df6  ldarg.3
0x8df7  ldarg.s  4
0x8df9  call     instance bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteOnePropertyValueAsJson(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x8dfe  stloc.0
0x8dff  ldloc.0
0x8e00  ret
```
