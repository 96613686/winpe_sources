# Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::WriteOnePropertyValueAsJson

- ea: `0x720a0`
- end: `0x72715`
- name: `Microsoft.SharePoint.ServerStub.SPRecycleBinItemServerStub::WriteOnePropertyValueAsJson`
- size: `1653`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x720a0`

## string_xrefs

- `0x720fc`: `DeletedBy`
- `0x72323`: `DeletedBy`
- `0x72108`: `DeletedByEmail`
- `0x72374`: `DeletedByEmail`
- `0x72114`: `DeletedByName`
- `0x723be`: `DeletedByName`
- `0x72120`: `DeletedDate`
- `0x72408`: `DeletedDate`
- `0x7212c`: `DeletedDateLocalFormatted`
- `0x72452`: `DeletedDateLocalFormatted`
- `0x72144`: `DirNamePath`
- `0x724e6`: `DirNamePath`
- `0x72185`: `LeafNamePath`
- `0x72658`: `LeafNamePath`

## pseudocode

```c

```

## disassembly

```asm
0x720a0  ldc.i4.0
0x720a1  stloc.0
0x720a2  ldarg.2
0x720a3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem
0x720a8  stloc.1
0x720a9  ldloc.1
0x720aa  brtrue.s loc_720B7
0x720ac  ldstr    aTarget// "target"
0x720b1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x720b6  throw
0x720b7  ldarg.3
0x720b8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x720bd  dup
0x720be  stloc.2
0x720bf  brfalse  loc_72707
0x720c4  volatile.
0x720c6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013ea-1
0x720cb  brtrue   loc_721B2
0x720d0  ldc.i4.s 0x11
0x720d2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x720d7  dup
0x720d8  ldstr    aAuthor_0// "Author"
0x720dd  ldc.i4.0
0x720de  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x720e3  dup
0x720e4  ldstr    aAuthoremail// "AuthorEmail"
0x720e9  ldc.i4.1
0x720ea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x720ef  dup
0x720f0  ldstr    aAuthorname// "AuthorName"
0x720f5  ldc.i4.2
0x720f6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x720fb  dup
0x720fc  ldstr    aDeletedby// "DeletedBy"
0x72101  ldc.i4.3
0x72102  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72107  dup
0x72108  ldstr    aDeletedbyemail// "DeletedByEmail"
0x7210d  ldc.i4.4
0x7210e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72113  dup
0x72114  ldstr    aDeletedbyname// "DeletedByName"
0x72119  ldc.i4.5
0x7211a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7211f  dup
0x72120  ldstr    aDeleteddate// "DeletedDate"
0x72125  ldc.i4.6
0x72126  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7212b  dup
0x7212c  ldstr    aDeleteddateloc// "DeletedDateLocalFormatted"
0x72131  ldc.i4.7
0x72132  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72137  dup
0x72138  ldstr    aDirname// "DirName"
0x7213d  ldc.i4.8
0x7213e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72143  dup
0x72144  ldstr    aDirnamepath// "DirNamePath"
0x72149  ldc.i4.s 9
0x7214b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72150  dup
0x72151  ldstr    aId_0// "Id"
0x72156  ldc.i4.s 0xA
0x72158  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7215d  dup
0x7215e  ldstr    aItemstate// "ItemState"
0x72163  ldc.i4.s 0xB
0x72165  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7216a  dup
0x7216b  ldstr    aItemtype// "ItemType"
0x72170  ldc.i4.s 0xC
0x72172  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72177  dup
0x72178  ldstr    aLeafname_0// "LeafName"
0x7217d  ldc.i4.s 0xD
0x7217f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72184  dup
0x72185  ldstr    aLeafnamepath// "LeafNamePath"
0x7218a  ldc.i4.s 0xE
0x7218c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x72191  dup
0x72192  ldstr    aSize_0// "Size"
0x72197  ldc.i4.s 0xF
0x72199  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x7219e  dup
0x7219f  ldstr    aTitle// "Title"
0x721a4  ldc.i4.s 0x10
0x721a6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x721ab  volatile.
0x721ad  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013ea-1
0x721b2  volatile.
0x721b4  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60013ea-1
0x721b9  ldloc.2
0x721ba  ldloca.s 3
0x721bc  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x721c1  brfalse  loc_72707
0x721c6  ldloc.3
0x721c7  switch   loc_72215, loc_72266, loc_722B0, loc_722FA, loc_7234B, loc_72395, loc_723DF, loc_72429, loc_72473, loc_724BD, loc_72507, loc_72551, loc_7259B, loc_725E5, loc_7262F, loc_72679, loc_726C0
0x72210  br       loc_72707
0x72215  ldarg.3
0x72216  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7221b  stloc.s  4
0x7221d  ldloca.s 4
0x7221f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x72224  brfalse.s loc_7223D
0x72226  ldarg.3
0x72227  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7222c  stloc.s  5
0x7222e  ldloca.s 5
0x72230  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x72235  brfalse.s loc_7223D
0x72237  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x7223c  throw
0x7223d  ldarg.0
0x7223e  ldstr    aAuthor_0// "Author"
0x72243  ldarg.s  4
0x72245  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7224a  ldc.i4.1
0x7224b  stloc.0
0x7224c  ldarg.0
0x7224d  ldarg.1
0x7224e  ldloc.1
0x7224f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_Author()
0x72254  ldarg.3
0x72255  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x7225a  ldarg.s  4
0x7225c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72261  br       loc_72713
0x72266  ldarg.3
0x72267  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7226c  stloc.s  6
0x7226e  ldloca.s 6
0x72270  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x72275  brfalse.s loc_7228E
0x72277  ldarg.3
0x72278  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7227d  stloc.s  7
0x7227f  ldloca.s 7
0x72281  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x72286  brtrue.s loc_7228E
0x72288  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x7228d  throw
0x7228e  ldarg.0
0x7228f  ldstr    aAuthoremail// "AuthorEmail"
0x72294  ldarg.s  4
0x72296  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7229b  ldc.i4.1
0x7229c  stloc.0
0x7229d  ldarg.1
0x7229e  ldloc.1
0x7229f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorEmail()
0x722a4  ldarg.s  4
0x722a6  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x722ab  br       loc_72713
0x722b0  ldarg.3
0x722b1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x722b6  stloc.s  8
0x722b8  ldloca.s 8
0x722ba  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x722bf  brfalse.s loc_722D8
0x722c1  ldarg.3
0x722c2  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x722c7  stloc.s  9
0x722c9  ldloca.s 9
0x722cb  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x722d0  brtrue.s loc_722D8
0x722d2  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x722d7  throw
0x722d8  ldarg.0
0x722d9  ldstr    aAuthorname// "AuthorName"
0x722de  ldarg.s  4
0x722e0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x722e5  ldc.i4.1
0x722e6  stloc.0
0x722e7  ldarg.1
0x722e8  ldloc.1
0x722e9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_AuthorName()
0x722ee  ldarg.s  4
0x722f0  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x722f5  br       loc_72713
0x722fa  ldarg.3
0x722fb  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x72300  stloc.s  0xA
0x72302  ldloca.s 0xA
0x72304  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x72309  brfalse.s loc_72322
0x7230b  ldarg.3
0x7230c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x72311  stloc.s  0xB
0x72313  ldloca.s 0xB
0x72315  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x7231a  brfalse.s loc_72322
0x7231c  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x72321  throw
0x72322  ldarg.0
0x72323  ldstr    aDeletedby// "DeletedBy"
0x72328  ldarg.s  4
0x7232a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x7232f  ldc.i4.1
0x72330  stloc.0
0x72331  ldarg.0
0x72332  ldarg.1
0x72333  ldloc.1
0x72334  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedBy()
0x72339  ldarg.3
0x7233a  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x7233f  ldarg.s  4
0x72341  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72346  br       loc_72713
0x7234b  ldarg.3
0x7234c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x72351  stloc.s  0xC
0x72353  ldloca.s 0xC
0x72355  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x7235a  brfalse.s loc_72373
0x7235c  ldarg.3
0x7235d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x72362  stloc.s  0xD
0x72364  ldloca.s 0xD
0x72366  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x7236b  brtrue.s loc_72373
0x7236d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x72372  throw
0x72373  ldarg.0
0x72374  ldstr    aDeletedbyemail// "DeletedByEmail"
0x72379  ldarg.s  4
0x7237b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72380  ldc.i4.1
0x72381  stloc.0
0x72382  ldarg.1
0x72383  ldloc.1
0x72384  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByEmail()
0x72389  ldarg.s  4
0x7238b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72390  br       loc_72713
0x72395  ldarg.3
0x72396  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7239b  stloc.s  0xE
0x7239d  ldloca.s 0xE
0x7239f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x723a4  brfalse.s loc_723BD
0x723a6  ldarg.3
0x723a7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x723ac  stloc.s  0xF
0x723ae  ldloca.s 0xF
0x723b0  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x723b5  brtrue.s loc_723BD
0x723b7  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x723bc  throw
0x723bd  ldarg.0
0x723be  ldstr    aDeletedbyname// "DeletedByName"
0x723c3  ldarg.s  4
0x723c5  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x723ca  ldc.i4.1
0x723cb  stloc.0
0x723cc  ldarg.1
0x723cd  ldloc.1
0x723ce  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedByName()
0x723d3  ldarg.s  4
0x723d5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x723da  br       loc_72713
0x723df  ldarg.3
0x723e0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x723e5  stloc.s  0x10
0x723e7  ldloca.s 0x10
0x723e9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x723ee  brfalse.s loc_72407
0x723f0  ldarg.3
0x723f1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x723f6  stloc.s  0x11
0x723f8  ldloca.s 0x11
0x723fa  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x723ff  brtrue.s loc_72407
0x72401  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x72406  throw
0x72407  ldarg.0
0x72408  ldstr    aDeleteddate// "DeletedDate"
0x7240d  ldarg.s  4
0x7240f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72414  ldc.i4.1
0x72415  stloc.0
0x72416  ldarg.1
0x72417  ldloc.1
0x72418  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.SharePoint]Microsoft.SharePoint.SPRecycleBinItem::get_DeletedDate()
0x7241d  ldarg.s  4
0x7241f  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteDateTime(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.DateTime, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x72424  br       loc_72713
0x72429  ldarg.3
0x7242a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x7242f  stloc.s  0x12
0x72431  ldloca.s 0x12
0x72433  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x72438  brfalse.s loc_72451
0x7243a  ldarg.3
0x7243b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x72440  stloc.s  0x13
0x72442  ldloca.s 0x13
0x72444  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x72449  brtrue.s loc_72451
0x7244b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
  ... truncated ...
```
