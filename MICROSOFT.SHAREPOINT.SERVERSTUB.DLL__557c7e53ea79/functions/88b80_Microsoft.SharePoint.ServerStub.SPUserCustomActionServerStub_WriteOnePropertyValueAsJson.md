# Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::WriteOnePropertyValueAsJson

- ea: `0x88b80`
- end: `0x89361`
- name: `Microsoft.SharePoint.ServerStub.SPUserCustomActionServerStub::WriteOnePropertyValueAsJson`
- size: `2017`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x88b80`

## string_xrefs

- `0x88bb8`: `ClientSideComponentId`
- `0x88d62`: `ClientSideComponentId`
- `0x88bc4`: `ClientSideComponentProperties`
- `0x88dac`: `ClientSideComponentProperties`
- `0x88bd0`: `CommandUIExtension`
- `0x88df6`: `CommandUIExtension`

## pseudocode

```c

```

## disassembly

```asm
0x88b80  ldc.i4.0
0x88b81  stloc.0
0x88b82  ldarg.2
0x88b83  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction
0x88b88  stloc.1
0x88b89  ldloc.1
0x88b8a  brtrue.s loc_88B97
0x88b8c  ldstr    aTarget// "target"
0x88b91  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x88b96  throw
0x88b97  ldarg.3
0x88b98  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x88b9d  dup
0x88b9e  stloc.2
0x88b9f  brfalse  loc_89353
0x88ba4  volatile.
0x88ba6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e6-1
0x88bab  brtrue   loc_88CC6
0x88bb0  ldc.i4.s 0x15
0x88bb2  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x88bb7  dup
0x88bb8  ldstr    aClientsidecomp// "ClientSideComponentId"
0x88bbd  ldc.i4.0
0x88bbe  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88bc3  dup
0x88bc4  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x88bc9  ldc.i4.1
0x88bca  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88bcf  dup
0x88bd0  ldstr    aCommanduiexten// "CommandUIExtension"
0x88bd5  ldc.i4.2
0x88bd6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88bdb  dup
0x88bdc  ldstr    aDescription// "Description"
0x88be1  ldc.i4.3
0x88be2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88be7  dup
0x88be8  ldstr    aDescriptionres// "DescriptionResource"
0x88bed  ldc.i4.4
0x88bee  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88bf3  dup
0x88bf4  ldstr    aGroup// "Group"
0x88bf9  ldc.i4.5
0x88bfa  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88bff  dup
0x88c00  ldstr    aId_0// "Id"
0x88c05  ldc.i4.6
0x88c06  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c0b  dup
0x88c0c  ldstr    aImageurl// "ImageUrl"
0x88c11  ldc.i4.7
0x88c12  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c17  dup
0x88c18  ldstr    aLocation// "Location"
0x88c1d  ldc.i4.8
0x88c1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c23  dup
0x88c24  ldstr    aName// "Name"
0x88c29  ldc.i4.s 9
0x88c2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c30  dup
0x88c31  ldstr    aRegistrationid// "RegistrationId"
0x88c36  ldc.i4.s 0xA
0x88c38  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c3d  dup
0x88c3e  ldstr    aRegistrationty// "RegistrationType"
0x88c43  ldc.i4.s 0xB
0x88c45  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c4a  dup
0x88c4b  ldstr    aRights// "Rights"
0x88c50  ldc.i4.s 0xC
0x88c52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c57  dup
0x88c58  ldstr    aScope// "Scope"
0x88c5d  ldc.i4.s 0xD
0x88c5f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c64  dup
0x88c65  ldstr    aScriptblock// "ScriptBlock"
0x88c6a  ldc.i4.s 0xE
0x88c6c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c71  dup
0x88c72  ldstr    aScriptsrc// "ScriptSrc"
0x88c77  ldc.i4.s 0xF
0x88c79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c7e  dup
0x88c7f  ldstr    aSequence// "Sequence"
0x88c84  ldc.i4.s 0x10
0x88c86  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c8b  dup
0x88c8c  ldstr    aTitle// "Title"
0x88c91  ldc.i4.s 0x11
0x88c93  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88c98  dup
0x88c99  ldstr    aTitleresource// "TitleResource"
0x88c9e  ldc.i4.s 0x12
0x88ca0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88ca5  dup
0x88ca6  ldstr    aUrl// "Url"
0x88cab  ldc.i4.s 0x13
0x88cad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88cb2  dup
0x88cb3  ldstr    aVersionofuserc// "VersionOfUserCustomAction"
0x88cb8  ldc.i4.s 0x14
0x88cba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x88cbf  volatile.
0x88cc1  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e6-1
0x88cc6  volatile.
0x88cc8  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x60016e6-1
0x88ccd  ldloc.2
0x88cce  ldloca.s 3
0x88cd0  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x88cd5  brfalse  loc_89353
0x88cda  ldloc.3
0x88cdb  switch   loc_88D39, loc_88D83, loc_88DCD, loc_88E17, loc_88E61, loc_88EB2, loc_88EFC, loc_88F46, loc_88F90, loc_88FDA, loc_89024, loc_8906E, loc_890B8, loc_89102, loc_8914C, loc_89196, loc_891E0, loc_8922A, loc_89274, loc_892C5, loc_8930C
0x88d34  br       loc_89353
0x88d39  ldarg.3
0x88d3a  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88d3f  stloc.s  4
0x88d41  ldloca.s 4
0x88d43  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88d48  brfalse.s loc_88D61
0x88d4a  ldarg.3
0x88d4b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88d50  stloc.s  5
0x88d52  ldloca.s 5
0x88d54  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88d59  brtrue.s loc_88D61
0x88d5b  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88d60  throw
0x88d61  ldarg.0
0x88d62  ldstr    aClientsidecomp// "ClientSideComponentId"
0x88d67  ldarg.s  4
0x88d69  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88d6e  ldc.i4.1
0x88d6f  stloc.0
0x88d70  ldarg.1
0x88d71  ldloc.1
0x88d72  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentId()
0x88d77  ldarg.s  4
0x88d79  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88d7e  br       loc_8935F
0x88d83  ldarg.3
0x88d84  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88d89  stloc.s  6
0x88d8b  ldloca.s 6
0x88d8d  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88d92  brfalse.s loc_88DAB
0x88d94  ldarg.3
0x88d95  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88d9a  stloc.s  7
0x88d9c  ldloca.s 7
0x88d9e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88da3  brtrue.s loc_88DAB
0x88da5  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88daa  throw
0x88dab  ldarg.0
0x88dac  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x88db1  ldarg.s  4
0x88db3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88db8  ldc.i4.1
0x88db9  stloc.0
0x88dba  ldarg.1
0x88dbb  ldloc.1
0x88dbc  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_ClientSideComponentProperties()
0x88dc1  ldarg.s  4
0x88dc3  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88dc8  br       loc_8935F
0x88dcd  ldarg.3
0x88dce  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88dd3  stloc.s  8
0x88dd5  ldloca.s 8
0x88dd7  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88ddc  brfalse.s loc_88DF5
0x88dde  ldarg.3
0x88ddf  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88de4  stloc.s  9
0x88de6  ldloca.s 9
0x88de8  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88ded  brtrue.s loc_88DF5
0x88def  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88df4  throw
0x88df5  ldarg.0
0x88df6  ldstr    aCommanduiexten// "CommandUIExtension"
0x88dfb  ldarg.s  4
0x88dfd  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88e02  ldc.i4.1
0x88e03  stloc.0
0x88e04  ldarg.1
0x88e05  ldloc.1
0x88e06  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_CommandUIExtension()
0x88e0b  ldarg.s  4
0x88e0d  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88e12  br       loc_8935F
0x88e17  ldarg.3
0x88e18  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88e1d  stloc.s  0xA
0x88e1f  ldloca.s 0xA
0x88e21  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88e26  brfalse.s loc_88E3F
0x88e28  ldarg.3
0x88e29  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88e2e  stloc.s  0xB
0x88e30  ldloca.s 0xB
0x88e32  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88e37  brtrue.s loc_88E3F
0x88e39  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88e3e  throw
0x88e3f  ldarg.0
0x88e40  ldstr    aDescription// "Description"
0x88e45  ldarg.s  4
0x88e47  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88e4c  ldc.i4.1
0x88e4d  stloc.0
0x88e4e  ldarg.1
0x88e4f  ldloc.1
0x88e50  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Description()
0x88e55  ldarg.s  4
0x88e57  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88e5c  br       loc_8935F
0x88e61  ldarg.3
0x88e62  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88e67  stloc.s  0xC
0x88e69  ldloca.s 0xC
0x88e6b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88e70  brfalse.s loc_88E89
0x88e72  ldarg.3
0x88e73  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88e78  stloc.s  0xD
0x88e7a  ldloca.s 0xD
0x88e7c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88e81  brfalse.s loc_88E89
0x88e83  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88e88  throw
0x88e89  ldarg.0
0x88e8a  ldstr    aDescriptionres// "DescriptionResource"
0x88e8f  ldarg.s  4
0x88e91  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88e96  ldc.i4.1
0x88e97  stloc.0
0x88e98  ldarg.0
0x88e99  ldarg.1
0x88e9a  ldloc.1
0x88e9b  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_DescriptionResource()
0x88ea0  ldarg.3
0x88ea1  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x88ea6  ldarg.s  4
0x88ea8  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88ead  br       loc_8935F
0x88eb2  ldarg.3
0x88eb3  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88eb8  stloc.s  0xE
0x88eba  ldloca.s 0xE
0x88ebc  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88ec1  brfalse.s loc_88EDA
0x88ec3  ldarg.3
0x88ec4  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88ec9  stloc.s  0xF
0x88ecb  ldloca.s 0xF
0x88ecd  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88ed2  brtrue.s loc_88EDA
0x88ed4  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88ed9  throw
0x88eda  ldarg.0
0x88edb  ldstr    aGroup// "Group"
0x88ee0  ldarg.s  4
0x88ee2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88ee7  ldc.i4.1
0x88ee8  stloc.0
0x88ee9  ldarg.1
0x88eea  ldloc.1
0x88eeb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Group()
0x88ef0  ldarg.s  4
0x88ef2  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88ef7  br       loc_8935F
0x88efc  ldarg.3
0x88efd  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88f02  stloc.s  0x10
0x88f04  ldloca.s 0x10
0x88f06  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x88f0b  brfalse.s loc_88F24
0x88f0d  ldarg.3
0x88f0e  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x88f13  stloc.s  0x11
0x88f15  ldloca.s 0x11
0x88f17  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x88f1c  brtrue.s loc_88F24
0x88f1e  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x88f23  throw
0x88f24  ldarg.0
0x88f25  ldstr    aId_0// "Id"
0x88f2a  ldarg.s  4
0x88f2c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88f31  ldc.i4.1
0x88f32  stloc.0
0x88f33  ldarg.1
0x88f34  ldloc.1
0x88f35  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPUserCustomAction::get_Id()
0x88f3a  ldarg.s  4
0x88f3c  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteGuid(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, valuetype [mscorlib]System.Guid, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x88f41  br       loc_8935F
  ... truncated ...
```
