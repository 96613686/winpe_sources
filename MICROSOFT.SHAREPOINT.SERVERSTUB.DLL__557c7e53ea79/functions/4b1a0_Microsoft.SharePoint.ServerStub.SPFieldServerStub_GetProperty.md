# Microsoft.SharePoint.ServerStub.SPFieldServerStub::GetProperty

- ea: `0x4b1a0`
- end: `0x4b7ee`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::GetProperty`
- size: `1614`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4de00`
- `0x4e750`
- `0x4fb40`
- `0x50510`
- `0x50f70`
- `0x533a0`
- `0x541e0`
- `0x55ce0`
- `0x56090`

## callees

- `0x4b1a0`

## string_xrefs

- `0x4b326`: `SchemaXml`
- `0x4b6b4`: `SchemaXml`
- `0x4b2e5`: `JSLink`
- `0x4b641`: `JSLink`
- `0x4b333`: `SchemaXmlWithResourceTokens`
- `0x4b6c7`: `SchemaXmlWithResourceTokens`
- `0x4b20f`: `ClientSideComponentId`
- `0x4b4db`: `ClientSideComponentId`
- `0x4b21b`: `ClientSideComponentProperties`
- `0x4b4f3`: `ClientSideComponentProperties`
- `0x4b203`: `CanBeDeleted`
- `0x4b4c3`: `CanBeDeleted`
- `0x4b30c`: `ReadOnlyField`
- `0x4b684`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4b1a0  ldarg.2
0x4b1a1  brtrue.s loc_4B1AE
0x4b1a3  ldstr    aPropname// "propName"
0x4b1a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b1ad  throw
0x4b1ae  ldarg.3
0x4b1af  brtrue.s loc_4B1BC
0x4b1b1  ldstr    aProxycontext// "proxyContext"
0x4b1b6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b1bb  throw
0x4b1bc  ldarg.1
0x4b1bd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4b1c2  stloc.0
0x4b1c3  ldloc.0
0x4b1c4  brtrue.s loc_4B1D1
0x4b1c6  ldstr    aTarget// "target"
0x4b1cb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b1d0  throw
0x4b1d1  ldarg.0
0x4b1d2  ldarg.2
0x4b1d3  ldarg.3
0x4b1d4  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b1d9  starg.s  2
0x4b1db  ldarg.2
0x4b1dc  dup
0x4b1dd  stloc.1
0x4b1de  brfalse  loc_4B7E4
0x4b1e3  volatile.
0x4b1e5  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000dde-1
0x4b1ea  brtrue   loc_4B3EF
0x4b1ef  ldc.i4.s 0x27
0x4b1f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4b1f6  dup
0x4b1f7  ldstr    aAutoindexed// "AutoIndexed"
0x4b1fc  ldc.i4.0
0x4b1fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b202  dup
0x4b203  ldstr    aCanbedeleted// "CanBeDeleted"
0x4b208  ldc.i4.1
0x4b209  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b20e  dup
0x4b20f  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4b214  ldc.i4.2
0x4b215  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b21a  dup
0x4b21b  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4b220  ldc.i4.3
0x4b221  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b226  dup
0x4b227  ldstr    aCustomformatte// "CustomFormatter"
0x4b22c  ldc.i4.4
0x4b22d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b232  dup
0x4b233  ldstr    aDefaultformula// "DefaultFormula"
0x4b238  ldc.i4.5
0x4b239  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b23e  dup
0x4b23f  ldstr    aDefaultvalue// "DefaultValue"
0x4b244  ldc.i4.6
0x4b245  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b24a  dup
0x4b24b  ldstr    aDescription// "Description"
0x4b250  ldc.i4.7
0x4b251  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b256  dup
0x4b257  ldstr    aDescriptionres// "DescriptionResource"
0x4b25c  ldc.i4.8
0x4b25d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b262  dup
0x4b263  ldstr    aDirection// "Direction"
0x4b268  ldc.i4.s 9
0x4b26a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b26f  dup
0x4b270  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4b275  ldc.i4.s 0xA
0x4b277  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b27c  dup
0x4b27d  ldstr    aEntityproperty// "EntityPropertyName"
0x4b282  ldc.i4.s 0xB
0x4b284  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b289  dup
0x4b28a  ldstr    aFilterable// "Filterable"
0x4b28f  ldc.i4.s 0xC
0x4b291  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b296  dup
0x4b297  ldstr    aFrombasetype// "FromBaseType"
0x4b29c  ldc.i4.s 0xD
0x4b29e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2a3  dup
0x4b2a4  ldstr    aGroup// "Group"
0x4b2a9  ldc.i4.s 0xE
0x4b2ab  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2b0  dup
0x4b2b1  ldstr    aHidden// "Hidden"
0x4b2b6  ldc.i4.s 0xF
0x4b2b8  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2bd  dup
0x4b2be  ldstr    aId_0// "Id"
0x4b2c3  ldc.i4.s 0x10
0x4b2c5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2ca  dup
0x4b2cb  ldstr    aIndexed// "Indexed"
0x4b2d0  ldc.i4.s 0x11
0x4b2d2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2d7  dup
0x4b2d8  ldstr    aInternalname// "InternalName"
0x4b2dd  ldc.i4.s 0x12
0x4b2df  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2e4  dup
0x4b2e5  ldstr    aJslink// "JSLink"
0x4b2ea  ldc.i4.s 0x13
0x4b2ec  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2f1  dup
0x4b2f2  ldstr    aNocrawl// "NoCrawl"
0x4b2f7  ldc.i4.s 0x14
0x4b2f9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b2fe  dup
0x4b2ff  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4b304  ldc.i4.s 0x15
0x4b306  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b30b  dup
0x4b30c  ldstr    aReadonlyfield// "ReadOnlyField"
0x4b311  ldc.i4.s 0x16
0x4b313  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b318  dup
0x4b319  ldstr    aRequired// "Required"
0x4b31e  ldc.i4.s 0x17
0x4b320  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b325  dup
0x4b326  ldstr    aSchemaxml// "SchemaXml"
0x4b32b  ldc.i4.s 0x18
0x4b32d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b332  dup
0x4b333  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4b338  ldc.i4.s 0x19
0x4b33a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b33f  dup
0x4b340  ldstr    aScope// "Scope"
0x4b345  ldc.i4.s 0x1A
0x4b347  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b34c  dup
0x4b34d  ldstr    aSealed// "Sealed"
0x4b352  ldc.i4.s 0x1B
0x4b354  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b359  dup
0x4b35a  ldstr    aShowinfiltersp// "ShowInFiltersPane"
0x4b35f  ldc.i4.s 0x1C
0x4b361  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b366  dup
0x4b367  ldstr    aSortable// "Sortable"
0x4b36c  ldc.i4.s 0x1D
0x4b36e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b373  dup
0x4b374  ldstr    aStaticname// "StaticName"
0x4b379  ldc.i4.s 0x1E
0x4b37b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b380  dup
0x4b381  ldstr    aTitle// "Title"
0x4b386  ldc.i4.s 0x1F
0x4b388  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b38d  dup
0x4b38e  ldstr    aTitleresource// "TitleResource"
0x4b393  ldc.i4.s 0x20
0x4b395  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b39a  dup
0x4b39b  ldstr    aFieldtypekind// "FieldTypeKind"
0x4b3a0  ldc.i4.s 0x21
0x4b3a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3a7  dup
0x4b3a8  ldstr    aTypeasstring// "TypeAsString"
0x4b3ad  ldc.i4.s 0x22
0x4b3af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3b4  dup
0x4b3b5  ldstr    aTypedisplaynam// "TypeDisplayName"
0x4b3ba  ldc.i4.s 0x23
0x4b3bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3c1  dup
0x4b3c2  ldstr    aTypeshortdescr// "TypeShortDescription"
0x4b3c7  ldc.i4.s 0x24
0x4b3c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3ce  dup
0x4b3cf  ldstr    aValidationform// "ValidationFormula"
0x4b3d4  ldc.i4.s 0x25
0x4b3d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3db  dup
0x4b3dc  ldstr    aValidationmess// "ValidationMessage"
0x4b3e1  ldc.i4.s 0x26
0x4b3e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b3e8  volatile.
0x4b3ea  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000dde-1
0x4b3ef  volatile.
0x4b3f1  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000dde-1
0x4b3f6  ldloc.1
0x4b3f7  ldloca.s 2
0x4b3f9  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4b3fe  brfalse  loc_4B7E4
0x4b403  ldloc.2
0x4b404  switch   loc_4B4AA, loc_4B4C2, loc_4B4DA, loc_4B4F2, loc_4B505, loc_4B518, loc_4B52B, loc_4B53E, loc_4B551, loc_4B564, loc_4B577, loc_4B58F, loc_4B5A2, loc_4B5BA, loc_4B5D2, loc_4B5E5, loc_4B5FD, loc_4B615, loc_4B62D, loc_4B640, loc_4B653, loc_4B66B, loc_4B683, loc_4B69B, loc_4B6B3, loc_4B6C6, loc_4B6D9, loc_4B6EC, loc_4B704, loc_4B71C, loc_4B734, loc_4B747, loc_4B75A, loc_4B76D, loc_4B785, loc_4B798, loc_4B7AB, loc_4B7BE, loc_4B7D1
0x4b4a5  br       loc_4B7E4
0x4b4aa  ldarg.0
0x4b4ab  ldstr    aAutoindexed// "AutoIndexed"
0x4b4b0  ldarg.3
0x4b4b1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b4b6  ldloc.0
0x4b4b7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_AutoIndexed()
0x4b4bc  box      [mscorlib]System.Boolean
0x4b4c1  ret
0x4b4c2  ldarg.0
0x4b4c3  ldstr    aCanbedeleted// "CanBeDeleted"
0x4b4c8  ldarg.3
0x4b4c9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b4ce  ldloc.0
0x4b4cf  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CanBeDeleted()
0x4b4d4  box      [mscorlib]System.Boolean
0x4b4d9  ret
0x4b4da  ldarg.0
0x4b4db  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4b4e0  ldarg.3
0x4b4e1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b4e6  ldloc.0
0x4b4e7  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentId()
0x4b4ec  box      [mscorlib]System.Guid
0x4b4f1  ret
0x4b4f2  ldarg.0
0x4b4f3  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4b4f8  ldarg.3
0x4b4f9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b4fe  ldloc.0
0x4b4ff  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ClientSideComponentProperties()
0x4b504  ret
0x4b505  ldarg.0
0x4b506  ldstr    aCustomformatte// "CustomFormatter"
0x4b50b  ldarg.3
0x4b50c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b511  ldloc.0
0x4b512  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_CustomFormatter()
0x4b517  ret
0x4b518  ldarg.0
0x4b519  ldstr    aDefaultformula// "DefaultFormula"
0x4b51e  ldarg.3
0x4b51f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b524  ldloc.0
0x4b525  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultFormula()
0x4b52a  ret
0x4b52b  ldarg.0
0x4b52c  ldstr    aDefaultvalue// "DefaultValue"
0x4b531  ldarg.3
0x4b532  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b537  ldloc.0
0x4b538  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultValue()
0x4b53d  ret
0x4b53e  ldarg.0
0x4b53f  ldstr    aDescription// "Description"
0x4b544  ldarg.3
0x4b545  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b54a  ldloc.0
0x4b54b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Description()
0x4b550  ret
0x4b551  ldarg.0
0x4b552  ldstr    aDescriptionres// "DescriptionResource"
0x4b557  ldarg.3
0x4b558  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b55d  ldloc.0
0x4b55e  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DescriptionResource()
0x4b563  ret
0x4b564  ldarg.0
0x4b565  ldstr    aDirection// "Direction"
0x4b56a  ldarg.3
0x4b56b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b570  ldloc.0
0x4b571  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Direction()
0x4b576  ret
0x4b577  ldarg.0
0x4b578  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4b57d  ldarg.3
0x4b57e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b583  ldloc.0
0x4b584  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_EnforceUniqueValues()
0x4b589  box      [mscorlib]System.Boolean
0x4b58e  ret
0x4b58f  ldarg.0
0x4b590  ldstr    aEntityproperty// "EntityPropertyName"
0x4b595  ldarg.3
0x4b596  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b59b  ldloc.0
0x4b59c  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_EntityPropertyName()
0x4b5a1  ret
0x4b5a2  ldarg.0
0x4b5a3  ldstr    aFilterable// "Filterable"
0x4b5a8  ldarg.3
0x4b5a9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b5ae  ldloc.0
0x4b5af  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_Filterable()
0x4b5b4  box      [mscorlib]System.Boolean
0x4b5b9  ret
0x4b5ba  ldarg.0
0x4b5bb  ldstr    aFrombasetype// "FromBaseType"
0x4b5c0  ldarg.3
0x4b5c1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b5c6  ldloc.0
  ... truncated ...
```
