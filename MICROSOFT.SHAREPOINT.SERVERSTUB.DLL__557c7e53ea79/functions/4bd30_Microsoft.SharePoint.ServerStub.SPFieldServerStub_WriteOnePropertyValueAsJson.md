# Microsoft.SharePoint.ServerStub.SPFieldServerStub::WriteOnePropertyValueAsJson

- ea: `0x4bd30`
- end: `0x4cb77`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::WriteOnePropertyValueAsJson`
- size: `3655`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4e0d0`
- `0x4e8f0`
- `0x4fc60`
- `0x50700`
- `0x51130`
- `0x53800`
- `0x54540`
- `0x55e00`
- `0x561b0`

## callees

- `0x4bd30`

## string_xrefs

- `0x4be97`: `SchemaXml`
- `0x4c73b`: `SchemaXml`
- `0x4be56`: `JSLink`
- `0x4c5c9`: `JSLink`
- `0x4bea4`: `SchemaXmlWithResourceTokens`
- `0x4c785`: `SchemaXmlWithResourceTokens`
- `0x4bd80`: `ClientSideComponentId`
- `0x4c0d8`: `ClientSideComponentId`
- `0x4bd8c`: `ClientSideComponentProperties`
- `0x4c122`: `ClientSideComponentProperties`
- `0x4bd74`: `CanBeDeleted`
- `0x4c08e`: `CanBeDeleted`
- `0x4be7d`: `ReadOnlyField`
- `0x4c6a7`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4bd30  ldc.i4.0
0x4bd31  stloc.0
0x4bd32  ldarg.2
0x4bd33  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4bd38  stloc.1
0x4bd39  ldloc.1
0x4bd3a  brtrue.s loc_4BD47
0x4bd3c  ldstr    aTarget// "target"
0x4bd41  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4bd46  throw
0x4bd47  ldarg.3
0x4bd48  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x4bd4d  dup
0x4bd4e  stloc.2
0x4bd4f  brfalse  loc_4CB69
0x4bd54  volatile.
0x4bd56  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000de2-1
0x4bd5b  brtrue   loc_4BF60
0x4bd60  ldc.i4.s 0x27
0x4bd62  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4bd67  dup
0x4bd68  ldstr    aAutoindexed// "AutoIndexed"
0x4bd6d  ldc.i4.0
0x4bd6e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bd73  dup
0x4bd74  ldstr    aCanbedeleted// "CanBeDeleted"
0x4bd79  ldc.i4.1
0x4bd7a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bd7f  dup
0x4bd80  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4bd85  ldc.i4.2
0x4bd86  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bd8b  dup
0x4bd8c  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4bd91  ldc.i4.3
0x4bd92  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bd97  dup
0x4bd98  ldstr    aCustomformatte// "CustomFormatter"
0x4bd9d  ldc.i4.4
0x4bd9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bda3  dup
0x4bda4  ldstr    aDefaultformula// "DefaultFormula"
0x4bda9  ldc.i4.5
0x4bdaa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bdaf  dup
0x4bdb0  ldstr    aDefaultvalue// "DefaultValue"
0x4bdb5  ldc.i4.6
0x4bdb6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bdbb  dup
0x4bdbc  ldstr    aDescription// "Description"
0x4bdc1  ldc.i4.7
0x4bdc2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bdc7  dup
0x4bdc8  ldstr    aDescriptionres// "DescriptionResource"
0x4bdcd  ldc.i4.8
0x4bdce  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bdd3  dup
0x4bdd4  ldstr    aDirection// "Direction"
0x4bdd9  ldc.i4.s 9
0x4bddb  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bde0  dup
0x4bde1  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4bde6  ldc.i4.s 0xA
0x4bde8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bded  dup
0x4bdee  ldstr    aEntityproperty// "EntityPropertyName"
0x4bdf3  ldc.i4.s 0xB
0x4bdf5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bdfa  dup
0x4bdfb  ldstr    aFilterable// "Filterable"
0x4be00  ldc.i4.s 0xC
0x4be02  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be07  dup
0x4be08  ldstr    aFrombasetype// "FromBaseType"
0x4be0d  ldc.i4.s 0xD
0x4be0f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be14  dup
0x4be15  ldstr    aGroup// "Group"
0x4be1a  ldc.i4.s 0xE
0x4be1c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be21  dup
0x4be22  ldstr    aHidden// "Hidden"
0x4be27  ldc.i4.s 0xF
0x4be29  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be2e  dup
0x4be2f  ldstr    aId_0// "Id"
0x4be34  ldc.i4.s 0x10
0x4be36  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be3b  dup
0x4be3c  ldstr    aIndexed// "Indexed"
0x4be41  ldc.i4.s 0x11
0x4be43  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be48  dup
0x4be49  ldstr    aInternalname// "InternalName"
0x4be4e  ldc.i4.s 0x12
0x4be50  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be55  dup
0x4be56  ldstr    aJslink// "JSLink"
0x4be5b  ldc.i4.s 0x13
0x4be5d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be62  dup
0x4be63  ldstr    aNocrawl// "NoCrawl"
0x4be68  ldc.i4.s 0x14
0x4be6a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be6f  dup
0x4be70  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4be75  ldc.i4.s 0x15
0x4be77  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be7c  dup
0x4be7d  ldstr    aReadonlyfield// "ReadOnlyField"
0x4be82  ldc.i4.s 0x16
0x4be84  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be89  dup
0x4be8a  ldstr    aRequired// "Required"
0x4be8f  ldc.i4.s 0x17
0x4be91  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4be96  dup
0x4be97  ldstr    aSchemaxml// "SchemaXml"
0x4be9c  ldc.i4.s 0x18
0x4be9e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bea3  dup
0x4bea4  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4bea9  ldc.i4.s 0x19
0x4beab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4beb0  dup
0x4beb1  ldstr    aScope// "Scope"
0x4beb6  ldc.i4.s 0x1A
0x4beb8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bebd  dup
0x4bebe  ldstr    aSealed// "Sealed"
0x4bec3  ldc.i4.s 0x1B
0x4bec5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4beca  dup
0x4becb  ldstr    aShowinfiltersp// "ShowInFiltersPane"
0x4bed0  ldc.i4.s 0x1C
0x4bed2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bed7  dup
0x4bed8  ldstr    aSortable// "Sortable"
0x4bedd  ldc.i4.s 0x1D
0x4bedf  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bee4  dup
0x4bee5  ldstr    aStaticname// "StaticName"
0x4beea  ldc.i4.s 0x1E
0x4beec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bef1  dup
0x4bef2  ldstr    aTitle// "Title"
0x4bef7  ldc.i4.s 0x1F
0x4bef9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4befe  dup
0x4beff  ldstr    aTitleresource// "TitleResource"
0x4bf04  ldc.i4.s 0x20
0x4bf06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf0b  dup
0x4bf0c  ldstr    aFieldtypekind// "FieldTypeKind"
0x4bf11  ldc.i4.s 0x21
0x4bf13  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf18  dup
0x4bf19  ldstr    aTypeasstring// "TypeAsString"
0x4bf1e  ldc.i4.s 0x22
0x4bf20  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf25  dup
0x4bf26  ldstr    aTypedisplaynam// "TypeDisplayName"
0x4bf2b  ldc.i4.s 0x23
0x4bf2d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf32  dup
0x4bf33  ldstr    aTypeshortdescr// "TypeShortDescription"
0x4bf38  ldc.i4.s 0x24
0x4bf3a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf3f  dup
0x4bf40  ldstr    aValidationform// "ValidationFormula"
0x4bf45  ldc.i4.s 0x25
0x4bf47  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf4c  dup
0x4bf4d  ldstr    aValidationmess// "ValidationMessage"
0x4bf52  ldc.i4.s 0x26
0x4bf54  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4bf59  volatile.
0x4bf5b  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000de2-1
0x4bf60  volatile.
0x4bf62  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000de2-1
0x4bf67  ldloc.2
0x4bf68  ldloca.s 3
0x4bf6a  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4bf6f  brfalse  loc_4CB69
0x4bf74  ldloc.3
0x4bf75  switch   loc_4C01B, loc_4C065, loc_4C0AF, loc_4C0F9, loc_4C143, loc_4C18D, loc_4C1D7, loc_4C221, loc_4C26B, loc_4C2BC, loc_4C306, loc_4C350, loc_4C39A, loc_4C3E4, loc_4C42E, loc_4C478, loc_4C4C2, loc_4C50C, loc_4C556, loc_4C5A0, loc_4C5EA, loc_4C634, loc_4C67E, loc_4C6C8, loc_4C712, loc_4C75C, loc_4C7A6, loc_4C7F0, loc_4C83A, loc_4C884, loc_4C8CE, loc_4C918, loc_4C962, loc_4C9B3, loc_4C9FD, loc_4CA47, loc_4CA91, loc_4CADB, loc_4CB22
0x4c016  br       loc_4CB69
0x4c01b  ldarg.3
0x4c01c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c021  stloc.s  4
0x4c023  ldloca.s 4
0x4c025  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4c02a  brfalse.s loc_4C043
0x4c02c  ldarg.3
0x4c02d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c032  stloc.s  5
0x4c034  ldloca.s 5
0x4c036  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4c03b  brtrue.s loc_4C043
0x4c03d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4c042  throw
0x4c043  ldarg.0
0x4c044  ldstr    aAutoindexed// "AutoIndexed"
0x4c049  ldarg.s  4
0x4c04b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c050  ldc.i4.1
0x4c051  stloc.0
0x4c052  ldarg.1
0x4c053  ldloc.1
0x4c054  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_AutoIndexed()
0x4c059  ldarg.s  4
0x4c05b  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c060  br       loc_4CB75
0x4c065  ldarg.3
0x4c066  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c06b  stloc.s  6
0x4c06d  ldloca.s 6
0x4c06f  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4c074  brfalse.s loc_4C08D
0x4c076  ldarg.3
0x4c077  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c07c  stloc.s  7
0x4c07e  ldloca.s 7
0x4c080  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4c085  brtrue.s loc_4C08D
0x4c087  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4c08c  throw
0x4c08d  ldarg.0
0x4c08e  ldstr    aCanbedeleted// "CanBeDeleted"
0x4c093  ldarg.s  4
0x4c095  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c09a  ldc.i4.1
0x4c09b  stloc.0
0x4c09c  ldarg.1
0x4c09d  ldloc.1
0x4c09e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CanBeDeleted()
0x4c0a3  ldarg.s  4
0x4c0a5  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteBoolean(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, bool, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c0aa  br       loc_4CB75
0x4c0af  ldarg.3
0x4c0b0  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c0b5  stloc.s  8
0x4c0b7  ldloca.s 8
0x4c0b9  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4c0be  brfalse.s loc_4C0D7
0x4c0c0  ldarg.3
0x4c0c1  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c0c6  stloc.s  9
0x4c0c8  ldloca.s 9
0x4c0ca  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4c0cf  brtrue.s loc_4C0D7
0x4c0d1  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4c0d6  throw
0x4c0d7  ldarg.0
0x4c0d8  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4c0dd  ldarg.s  4
0x4c0df  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c0e4  ldc.i4.1
0x4c0e5  stloc.0
0x4c0e6  ldarg.1
0x4c0e7  ldloc.1
0x4c0e8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentId()
0x4c0ed  ldarg.s  4
0x4c0ef  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c0f4  br       loc_4CB75
0x4c0f9  ldarg.3
0x4c0fa  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c0ff  stloc.s  0xA
0x4c101  ldloca.s 0xA
0x4c103  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4c108  brfalse.s loc_4C121
0x4c10a  ldarg.3
0x4c10b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c110  stloc.s  0xB
0x4c112  ldloca.s 0xB
0x4c114  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4c119  brtrue.s loc_4C121
0x4c11b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4c120  throw
0x4c121  ldarg.0
0x4c122  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4c127  ldarg.s  4
0x4c129  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c12e  ldc.i4.1
0x4c12f  stloc.0
0x4c130  ldarg.1
0x4c131  ldloc.1
0x4c132  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentProperties()
0x4c137  ldarg.s  4
0x4c139  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4c13e  br       loc_4CB75
0x4c143  ldarg.3
0x4c144  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c149  stloc.s  0xC
0x4c14b  ldloca.s 0xC
0x4c14d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4c152  brfalse.s loc_4C16B
0x4c154  ldarg.3
0x4c155  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4c15a  stloc.s  0xD
  ... truncated ...
```
