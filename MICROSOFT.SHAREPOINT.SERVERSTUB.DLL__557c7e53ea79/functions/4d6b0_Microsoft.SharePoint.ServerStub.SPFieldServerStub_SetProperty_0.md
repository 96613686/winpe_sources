# Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetProperty_0

- ea: `0x4d6b0`
- end: `0x4db64`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetProperty_0`
- size: `1204`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4e530`
- `0x4eb60`
- `0x4fda0`
- `0x50a00`
- `0x513a0`
- `0x53eb0`
- `0x54a30`
- `0x55f40`
- `0x562f0`

## callees

- `0x4d6b0`

## string_xrefs

- `0x4d7d0`: `SchemaXml`
- `0x4da6f`: `SchemaXml`
- `0x4d78f`: `JSLink`
- `0x4d9ed`: `JSLink`
- `0x4d709`: `ClientSideComponentId`
- `0x4d8cf`: `ClientSideComponentId`
- `0x4d715`: `ClientSideComponentProperties`
- `0x4d8e9`: `ClientSideComponentProperties`
- `0x4d7b6`: `ReadOnlyField`
- `0x4da3b`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4d6b0  ldarg.s  4
0x4d6b2  brtrue.s loc_4D6BF
0x4d6b4  ldstr    aProxycontext// "proxyContext"
0x4d6b9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d6be  throw
0x4d6bf  ldarg.1
0x4d6c0  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4d6c5  stloc.0
0x4d6c6  ldloc.0
0x4d6c7  brtrue.s loc_4D6D4
0x4d6c9  ldstr    aTarget// "target"
0x4d6ce  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d6d3  throw
0x4d6d4  ldarg.2
0x4d6d5  brtrue.s loc_4D6E2
0x4d6d7  ldstr    aPropname// "propName"
0x4d6dc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d6e1  throw
0x4d6e2  ldarg.0
0x4d6e3  ldarg.2
0x4d6e4  ldarg.s  4
0x4d6e6  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d6eb  starg.s  2
0x4d6ed  ldarg.2
0x4d6ee  dup
0x4d6ef  stloc.1
0x4d6f0  brfalse  loc_4DB58
0x4d6f5  volatile.
0x4d6f7  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df1-1
0x4d6fc  brtrue   loc_4D84B
0x4d701  ldc.i4.s 0x19
0x4d703  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4d708  dup
0x4d709  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4d70e  ldc.i4.0
0x4d70f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d714  dup
0x4d715  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4d71a  ldc.i4.1
0x4d71b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d720  dup
0x4d721  ldstr    aCustomformatte// "CustomFormatter"
0x4d726  ldc.i4.2
0x4d727  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d72c  dup
0x4d72d  ldstr    aDefaultformula// "DefaultFormula"
0x4d732  ldc.i4.3
0x4d733  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d738  dup
0x4d739  ldstr    aDefaultvalue// "DefaultValue"
0x4d73e  ldc.i4.4
0x4d73f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d744  dup
0x4d745  ldstr    aDescription// "Description"
0x4d74a  ldc.i4.5
0x4d74b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d750  dup
0x4d751  ldstr    aDirection// "Direction"
0x4d756  ldc.i4.6
0x4d757  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d75c  dup
0x4d75d  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4d762  ldc.i4.7
0x4d763  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d768  dup
0x4d769  ldstr    aGroup// "Group"
0x4d76e  ldc.i4.8
0x4d76f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d774  dup
0x4d775  ldstr    aHidden// "Hidden"
0x4d77a  ldc.i4.s 9
0x4d77c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d781  dup
0x4d782  ldstr    aIndexed// "Indexed"
0x4d787  ldc.i4.s 0xA
0x4d789  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d78e  dup
0x4d78f  ldstr    aJslink// "JSLink"
0x4d794  ldc.i4.s 0xB
0x4d796  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d79b  dup
0x4d79c  ldstr    aNocrawl// "NoCrawl"
0x4d7a1  ldc.i4.s 0xC
0x4d7a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7a8  dup
0x4d7a9  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4d7ae  ldc.i4.s 0xD
0x4d7b0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7b5  dup
0x4d7b6  ldstr    aReadonlyfield// "ReadOnlyField"
0x4d7bb  ldc.i4.s 0xE
0x4d7bd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7c2  dup
0x4d7c3  ldstr    aRequired// "Required"
0x4d7c8  ldc.i4.s 0xF
0x4d7ca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7cf  dup
0x4d7d0  ldstr    aSchemaxml// "SchemaXml"
0x4d7d5  ldc.i4.s 0x10
0x4d7d7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7dc  dup
0x4d7dd  ldstr    aSealed// "Sealed"
0x4d7e2  ldc.i4.s 0x11
0x4d7e4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7e9  dup
0x4d7ea  ldstr    aShowinfiltersp// "ShowInFiltersPane"
0x4d7ef  ldc.i4.s 0x12
0x4d7f1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d7f6  dup
0x4d7f7  ldstr    aStaticname// "StaticName"
0x4d7fc  ldc.i4.s 0x13
0x4d7fe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d803  dup
0x4d804  ldstr    aTitle// "Title"
0x4d809  ldc.i4.s 0x14
0x4d80b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d810  dup
0x4d811  ldstr    aFieldtypekind// "FieldTypeKind"
0x4d816  ldc.i4.s 0x15
0x4d818  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d81d  dup
0x4d81e  ldstr    aTypeasstring// "TypeAsString"
0x4d823  ldc.i4.s 0x16
0x4d825  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d82a  dup
0x4d82b  ldstr    aValidationform// "ValidationFormula"
0x4d830  ldc.i4.s 0x17
0x4d832  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d837  dup
0x4d838  ldstr    aValidationmess// "ValidationMessage"
0x4d83d  ldc.i4.s 0x18
0x4d83f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4d844  volatile.
0x4d846  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df1-1
0x4d84b  volatile.
0x4d84d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000df1-1
0x4d852  ldloc.1
0x4d853  ldloca.s 2
0x4d855  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4d85a  brfalse  loc_4DB58
0x4d85f  ldloc.2
0x4d860  switch   loc_4D8CE, loc_4D8E8, loc_4D902, loc_4D91C, loc_4D936, loc_4D950, loc_4D96A, loc_4D984, loc_4D99E, loc_4D9B8, loc_4D9D2, loc_4D9EC, loc_4DA06, loc_4DA20, loc_4DA3A, loc_4DA54, loc_4DA6E, loc_4DA88, loc_4DAA2, loc_4DABC, loc_4DAD6, loc_4DAF0, loc_4DB0A, loc_4DB24, loc_4DB3E
0x4d8c9  br       loc_4DB58
0x4d8ce  ldarg.0
0x4d8cf  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4d8d4  ldarg.s  4
0x4d8d6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d8db  ldloc.0
0x4d8dc  ldarg.3
0x4d8dd  callvirt T0x2B00002D
0x4d8e2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ClientSideComponentId(valuetype [mscorlib]System.Guid)
0x4d8e7  ret
0x4d8e8  ldarg.0
0x4d8e9  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4d8ee  ldarg.s  4
0x4d8f0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d8f5  ldloc.0
0x4d8f6  ldarg.3
0x4d8f7  callvirt T0x2B000008
0x4d8fc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ClientSideComponentProperties(string)
0x4d901  ret
0x4d902  ldarg.0
0x4d903  ldstr    aCustomformatte// "CustomFormatter"
0x4d908  ldarg.s  4
0x4d90a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d90f  ldloc.0
0x4d910  ldarg.3
0x4d911  callvirt T0x2B000008
0x4d916  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_CustomFormatter(string)
0x4d91b  ret
0x4d91c  ldarg.0
0x4d91d  ldstr    aDefaultformula// "DefaultFormula"
0x4d922  ldarg.s  4
0x4d924  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d929  ldloc.0
0x4d92a  ldarg.3
0x4d92b  callvirt T0x2B000008
0x4d930  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_DefaultFormula(string)
0x4d935  ret
0x4d936  ldarg.0
0x4d937  ldstr    aDefaultvalue// "DefaultValue"
0x4d93c  ldarg.s  4
0x4d93e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d943  ldloc.0
0x4d944  ldarg.3
0x4d945  callvirt T0x2B000008
0x4d94a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_DefaultValue(string)
0x4d94f  ret
0x4d950  ldarg.0
0x4d951  ldstr    aDescription// "Description"
0x4d956  ldarg.s  4
0x4d958  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d95d  ldloc.0
0x4d95e  ldarg.3
0x4d95f  callvirt T0x2B000008
0x4d964  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Description(string)
0x4d969  ret
0x4d96a  ldarg.0
0x4d96b  ldstr    aDirection// "Direction"
0x4d970  ldarg.s  4
0x4d972  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d977  ldloc.0
0x4d978  ldarg.3
0x4d979  callvirt T0x2B000008
0x4d97e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Direction(string)
0x4d983  ret
0x4d984  ldarg.0
0x4d985  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4d98a  ldarg.s  4
0x4d98c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d991  ldloc.0
0x4d992  ldarg.3
0x4d993  callvirt T0x2B00000A
0x4d998  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_EnforceUniqueValues(bool)
0x4d99d  ret
0x4d99e  ldarg.0
0x4d99f  ldstr    aGroup// "Group"
0x4d9a4  ldarg.s  4
0x4d9a6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d9ab  ldloc.0
0x4d9ac  ldarg.3
0x4d9ad  callvirt T0x2B000008
0x4d9b2  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Group(string)
0x4d9b7  ret
0x4d9b8  ldarg.0
0x4d9b9  ldstr    aHidden// "Hidden"
0x4d9be  ldarg.s  4
0x4d9c0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d9c5  ldloc.0
0x4d9c6  ldarg.3
0x4d9c7  callvirt T0x2B00000A
0x4d9cc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Hidden(bool)
0x4d9d1  ret
0x4d9d2  ldarg.0
0x4d9d3  ldstr    aIndexed// "Indexed"
0x4d9d8  ldarg.s  4
0x4d9da  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d9df  ldloc.0
0x4d9e0  ldarg.3
0x4d9e1  callvirt T0x2B00000A
0x4d9e6  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Indexed(bool)
0x4d9eb  ret
0x4d9ec  ldarg.0
0x4d9ed  ldstr    aJslink// "JSLink"
0x4d9f2  ldarg.s  4
0x4d9f4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4d9f9  ldloc.0
0x4d9fa  ldarg.3
0x4d9fb  callvirt T0x2B000008
0x4da00  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_JSLink(string)
0x4da05  ret
0x4da06  ldarg.0
0x4da07  ldstr    aNocrawl// "NoCrawl"
0x4da0c  ldarg.s  4
0x4da0e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4da13  ldloc.0
0x4da14  ldarg.3
0x4da15  callvirt T0x2B00000A
0x4da1a  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_NoCrawl(bool)
0x4da1f  ret
0x4da20  ldarg.0
0x4da21  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4da26  ldarg.s  4
0x4da28  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4da2d  ldloc.0
0x4da2e  ldarg.3
0x4da2f  callvirt T0x2B00000A
0x4da34  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_PinnedToFiltersPane(bool)
0x4da39  ret
0x4da3a  ldarg.0
0x4da3b  ldstr    aReadonlyfield// "ReadOnlyField"
0x4da40  ldarg.s  4
0x4da42  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4da47  ldloc.0
0x4da48  ldarg.3
0x4da49  callvirt T0x2B00000A
0x4da4e  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ReadOnlyField(bool)
0x4da53  ret
0x4da54  ldarg.0
0x4da55  ldstr    aRequired// "Required"
0x4da5a  ldarg.s  4
0x4da5c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4da61  ldloc.0
0x4da62  ldarg.3
0x4da63  callvirt T0x2B00000A
0x4da68  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Required(bool)
0x4da6d  ret
0x4da6e  ldarg.0
0x4da6f  ldstr    aSchemaxml// "SchemaXml"
0x4da74  ldarg.s  4
0x4da76  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4da7b  ldloc.0
0x4da7c  ldarg.3
0x4da7d  callvirt T0x2B000008
0x4da82  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_SchemaXml(string)
0x4da87  ret
0x4da88  ldarg.0
0x4da89  ldstr    aSealed// "Sealed"
0x4da8e  ldarg.s  4
0x4da90  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
  ... truncated ...
```
