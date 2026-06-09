# Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::WriteOnePropertyValueAsJson

- ea: `0x39f0`
- end: `0x40b2`
- name: `Microsoft.SharePoint.Publishing.EmbedDataV1ServerStub::WriteOnePropertyValueAsJson`
- size: `1730`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x39f0`

## string_xrefs

- `0x3a58`: `EmbedServiceResponseCode`
- `0x3cc7`: `EmbedServiceResponseCode`

## pseudocode

```c

```

## disassembly

```asm
0x39f0  ldc.i4.0
0x39f1  stloc.0
0x39f2  ldarg.2
0x39f3  isinst   [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1
0x39f8  stloc.1
0x39f9  ldloc.1
0x39fa  brtrue.s loc_3A07
0x39fc  ldstr    aTarget// "target"
0x3a01  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3a06  throw
0x3a07  ldarg.3
0x3a08  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x3a0d  dup
0x3a0e  stloc.2
0x3a0f  brfalse  loc_40A4
0x3a14  volatile.
0x3a16  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000097-1
0x3a1b  brtrue   loc_3B0F
0x3a20  ldc.i4.s 0x12
0x3a22  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x3a27  dup
0x3a28  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x3a2d  ldc.i4.0
0x3a2e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a33  dup
0x3a34  ldstr    aCreatorname// "CreatorName"
0x3a39  ldc.i4.1
0x3a3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a3f  dup
0x3a40  ldstr    aDatepublisheda// "DatePublishedAt"
0x3a45  ldc.i4.2
0x3a46  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a4b  dup
0x3a4c  ldstr    aDescription// "Description"
0x3a51  ldc.i4.3
0x3a52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a57  dup
0x3a58  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x3a5d  ldc.i4.4
0x3a5e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a63  dup
0x3a64  ldstr    aErrormessage// "ErrorMessage"
0x3a69  ldc.i4.5
0x3a6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a6f  dup
0x3a70  ldstr    aHtml// "Html"
0x3a75  ldc.i4.6
0x3a76  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a7b  dup
0x3a7c  ldstr    aListid// "ListId"
0x3a81  ldc.i4.7
0x3a82  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a87  dup
0x3a88  ldstr    aPublishername// "PublisherName"
0x3a8d  ldc.i4.8
0x3a8e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3a93  dup
0x3a94  ldstr    aResponsecode// "ResponseCode"
0x3a99  ldc.i4.s 9
0x3a9b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3aa0  dup
0x3aa1  ldstr    aSiteid// "SiteId"
0x3aa6  ldc.i4.s 0xA
0x3aa8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3aad  dup
0x3aae  ldstr    aThumbnailurl// "ThumbnailUrl"
0x3ab3  ldc.i4.s 0xB
0x3ab5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3aba  dup
0x3abb  ldstr    aTitle// "Title"
0x3ac0  ldc.i4.s 0xC
0x3ac2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ac7  dup
0x3ac8  ldstr    aType// "Type"
0x3acd  ldc.i4.s 0xD
0x3acf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ad4  dup
0x3ad5  ldstr    aUniqueid// "UniqueId"
0x3ada  ldc.i4.s 0xE
0x3adc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3ae1  dup
0x3ae2  ldstr    aUrl// "Url"
0x3ae7  ldc.i4.s 0xF
0x3ae9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3aee  dup
0x3aef  ldstr    aVideoid// "VideoId"
0x3af4  ldc.i4.s 0x10
0x3af6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3afb  dup
0x3afc  ldstr    aWebid// "WebId"
0x3b01  ldc.i4.s 0x11
0x3b03  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x3b08  volatile.
0x3b0a  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000097-1
0x3b0f  volatile.
0x3b11  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{281BADDB-0765-4B85-A9B8-88F468DFB6C0}::$$method0x6000097-1
0x3b16  ldloc.2
0x3b17  ldloca.s 3
0x3b19  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x3b1e  brfalse  loc_40A4
0x3b23  ldloc.3
0x3b24  switch   loc_3B76, loc_3BC0, loc_3C0A, loc_3C54, loc_3C9E, loc_3CE8, loc_3D32, loc_3D7C, loc_3DC6, loc_3E10, loc_3E5A, loc_3EA4, loc_3EEE, loc_3F38, loc_3F82, loc_3FCC, loc_4016, loc_405D
0x3b71  br       loc_40A4
0x3b76  ldarg.3
0x3b77  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3b7c  stloc.s  4
0x3b7e  ldloca.s 4
0x3b80  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3b85  brfalse.s loc_3B9E
0x3b87  ldarg.3
0x3b88  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3b8d  stloc.s  5
0x3b8f  ldloca.s 5
0x3b91  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3b96  brtrue.s loc_3B9E
0x3b98  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3b9d  throw
0x3b9e  ldarg.0
0x3b9f  ldstr    aAllowhttpsembe// "AllowHttpsEmbed"
0x3ba4  ldarg.s  4
0x3ba6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3bab  ldc.i4.1
0x3bac  stloc.0
0x3bad  ldarg.1
0x3bae  ldloc.1
0x3baf  callvirt instance bool [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_AllowHttpsEmbed()
0x3bb4  ldarg.s  4
0x3bb6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3bbb  br       loc_40B0
0x3bc0  ldarg.3
0x3bc1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3bc6  stloc.s  6
0x3bc8  ldloca.s 6
0x3bca  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3bcf  brfalse.s loc_3BE8
0x3bd1  ldarg.3
0x3bd2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3bd7  stloc.s  7
0x3bd9  ldloca.s 7
0x3bdb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3be0  brtrue.s loc_3BE8
0x3be2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3be7  throw
0x3be8  ldarg.0
0x3be9  ldstr    aCreatorname// "CreatorName"
0x3bee  ldarg.s  4
0x3bf0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3bf5  ldc.i4.1
0x3bf6  stloc.0
0x3bf7  ldarg.1
0x3bf8  ldloc.1
0x3bf9  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_CreatorName()
0x3bfe  ldarg.s  4
0x3c00  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3c05  br       loc_40B0
0x3c0a  ldarg.3
0x3c0b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3c10  stloc.s  8
0x3c12  ldloca.s 8
0x3c14  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3c19  brfalse.s loc_3C32
0x3c1b  ldarg.3
0x3c1c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3c21  stloc.s  9
0x3c23  ldloca.s 9
0x3c25  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3c2a  brtrue.s loc_3C32
0x3c2c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3c31  throw
0x3c32  ldarg.0
0x3c33  ldstr    aDatepublisheda// "DatePublishedAt"
0x3c38  ldarg.s  4
0x3c3a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3c3f  ldc.i4.1
0x3c40  stloc.0
0x3c41  ldarg.1
0x3c42  ldloc.1
0x3c43  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_DatePublishedAt()
0x3c48  ldarg.s  4
0x3c4a  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3c4f  br       loc_40B0
0x3c54  ldarg.3
0x3c55  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3c5a  stloc.s  0xA
0x3c5c  ldloca.s 0xA
0x3c5e  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3c63  brfalse.s loc_3C7C
0x3c65  ldarg.3
0x3c66  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3c6b  stloc.s  0xB
0x3c6d  ldloca.s 0xB
0x3c6f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3c74  brtrue.s loc_3C7C
0x3c76  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3c7b  throw
0x3c7c  ldarg.0
0x3c7d  ldstr    aDescription// "Description"
0x3c82  ldarg.s  4
0x3c84  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3c89  ldc.i4.1
0x3c8a  stloc.0
0x3c8b  ldarg.1
0x3c8c  ldloc.1
0x3c8d  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Description()
0x3c92  ldarg.s  4
0x3c94  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3c99  br       loc_40B0
0x3c9e  ldarg.3
0x3c9f  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3ca4  stloc.s  0xC
0x3ca6  ldloca.s 0xC
0x3ca8  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3cad  brfalse.s loc_3CC6
0x3caf  ldarg.3
0x3cb0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3cb5  stloc.s  0xD
0x3cb7  ldloca.s 0xD
0x3cb9  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3cbe  brtrue.s loc_3CC6
0x3cc0  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3cc5  throw
0x3cc6  ldarg.0
0x3cc7  ldstr    aEmbedservicere// "EmbedServiceResponseCode"
0x3ccc  ldarg.s  4
0x3cce  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3cd3  ldc.i4.1
0x3cd4  stloc.0
0x3cd5  ldarg.1
0x3cd6  ldloc.1
0x3cd7  callvirt instance int32 [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_EmbedServiceResponseCode()
0x3cdc  ldarg.s  4
0x3cde  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteInt32(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, int32, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3ce3  br       loc_40B0
0x3ce8  ldarg.3
0x3ce9  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3cee  stloc.s  0xE
0x3cf0  ldloca.s 0xE
0x3cf2  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3cf7  brfalse.s loc_3D10
0x3cf9  ldarg.3
0x3cfa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3cff  stloc.s  0xF
0x3d01  ldloca.s 0xF
0x3d03  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3d08  brtrue.s loc_3D10
0x3d0a  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3d0f  throw
0x3d10  ldarg.0
0x3d11  ldstr    aErrormessage// "ErrorMessage"
0x3d16  ldarg.s  4
0x3d18  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3d1d  ldc.i4.1
0x3d1e  stloc.0
0x3d1f  ldarg.1
0x3d20  ldloc.1
0x3d21  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_ErrorMessage()
0x3d26  ldarg.s  4
0x3d28  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3d2d  br       loc_40B0
0x3d32  ldarg.3
0x3d33  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3d38  stloc.s  0x10
0x3d3a  ldloca.s 0x10
0x3d3c  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3d41  brfalse.s loc_3D5A
0x3d43  ldarg.3
0x3d44  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3d49  stloc.s  0x11
0x3d4b  ldloca.s 0x11
0x3d4d  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3d52  brtrue.s loc_3D5A
0x3d54  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3d59  throw
0x3d5a  ldarg.0
0x3d5b  ldstr    aHtml// "Html"
0x3d60  ldarg.s  4
0x3d62  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3d67  ldc.i4.1
0x3d68  stloc.0
0x3d69  ldarg.1
0x3d6a  ldloc.1
0x3d6b  callvirt instance string [Microsoft.SharePoint.Publishing]Microsoft.SharePoint.Publishing.EmbedDataV1::get_Html()
0x3d70  ldarg.s  4
0x3d72  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x3d77  br       loc_40B0
0x3d7c  ldarg.3
0x3d7d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3d82  stloc.s  0x12
0x3d84  ldloca.s 0x12
0x3d86  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x3d8b  brfalse.s loc_3DA4
0x3d8d  ldarg.3
0x3d8e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x3d93  stloc.s  0x13
0x3d95  ldloca.s 0x13
0x3d97  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x3d9c  brtrue.s loc_3DA4
0x3d9e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x3da3  throw
0x3da4  ldarg.0
  ... truncated ...
```
