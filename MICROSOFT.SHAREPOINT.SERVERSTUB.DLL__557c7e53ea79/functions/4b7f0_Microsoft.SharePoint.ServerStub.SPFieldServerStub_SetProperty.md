# Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetProperty

- ea: `0x4b7f0`
- end: `0x4bcd6`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::SetProperty`
- size: `1254`
- prototype: ``
- caller_count: `9`
- callee_count: `1`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x4df70`
- `0x4e810`
- `0x4fbb0`
- `0x50600`
- `0x51030`
- `0x535b0`
- `0x54380`
- `0x55d50`
- `0x56100`

## callees

- `0x4b7f0`

## string_xrefs

- `0x4b910`: `SchemaXml`
- `0x4bbcf`: `SchemaXml`
- `0x4b8cf`: `JSLink`
- `0x4bb43`: `JSLink`
- `0x4b849`: `ClientSideComponentId`
- `0x4ba0f`: `ClientSideComponentId`
- `0x4b855`: `ClientSideComponentProperties`
- `0x4ba2b`: `ClientSideComponentProperties`
- `0x4b8f6`: `ReadOnlyField`
- `0x4bb97`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4b7f0  ldarg.s  4
0x4b7f2  brtrue.s loc_4B7FF
0x4b7f4  ldstr    aProxycontext// "proxyContext"
0x4b7f9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b7fe  throw
0x4b7ff  ldarg.1
0x4b800  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4b805  stloc.0
0x4b806  ldloc.0
0x4b807  brtrue.s loc_4B814
0x4b809  ldstr    aTarget// "target"
0x4b80e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b813  throw
0x4b814  ldarg.2
0x4b815  brtrue.s loc_4B822
0x4b817  ldstr    aPropname// "propName"
0x4b81c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4b821  throw
0x4b822  ldarg.0
0x4b823  ldarg.2
0x4b824  ldarg.s  4
0x4b826  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4b82b  starg.s  2
0x4b82d  ldarg.2
0x4b82e  dup
0x4b82f  stloc.1
0x4b830  brfalse  loc_4BCCA
0x4b835  volatile.
0x4b837  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddf-1
0x4b83c  brtrue   loc_4B98B
0x4b841  ldc.i4.s 0x19
0x4b843  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x4b848  dup
0x4b849  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4b84e  ldc.i4.0
0x4b84f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b854  dup
0x4b855  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4b85a  ldc.i4.1
0x4b85b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b860  dup
0x4b861  ldstr    aCustomformatte// "CustomFormatter"
0x4b866  ldc.i4.2
0x4b867  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b86c  dup
0x4b86d  ldstr    aDefaultformula// "DefaultFormula"
0x4b872  ldc.i4.3
0x4b873  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b878  dup
0x4b879  ldstr    aDefaultvalue// "DefaultValue"
0x4b87e  ldc.i4.4
0x4b87f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b884  dup
0x4b885  ldstr    aDescription// "Description"
0x4b88a  ldc.i4.5
0x4b88b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b890  dup
0x4b891  ldstr    aDirection// "Direction"
0x4b896  ldc.i4.6
0x4b897  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b89c  dup
0x4b89d  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4b8a2  ldc.i4.7
0x4b8a3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8a8  dup
0x4b8a9  ldstr    aGroup// "Group"
0x4b8ae  ldc.i4.8
0x4b8af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8b4  dup
0x4b8b5  ldstr    aHidden// "Hidden"
0x4b8ba  ldc.i4.s 9
0x4b8bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8c1  dup
0x4b8c2  ldstr    aIndexed// "Indexed"
0x4b8c7  ldc.i4.s 0xA
0x4b8c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8ce  dup
0x4b8cf  ldstr    aJslink// "JSLink"
0x4b8d4  ldc.i4.s 0xB
0x4b8d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8db  dup
0x4b8dc  ldstr    aNocrawl// "NoCrawl"
0x4b8e1  ldc.i4.s 0xC
0x4b8e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8e8  dup
0x4b8e9  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4b8ee  ldc.i4.s 0xD
0x4b8f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b8f5  dup
0x4b8f6  ldstr    aReadonlyfield// "ReadOnlyField"
0x4b8fb  ldc.i4.s 0xE
0x4b8fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b902  dup
0x4b903  ldstr    aRequired// "Required"
0x4b908  ldc.i4.s 0xF
0x4b90a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b90f  dup
0x4b910  ldstr    aSchemaxml// "SchemaXml"
0x4b915  ldc.i4.s 0x10
0x4b917  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b91c  dup
0x4b91d  ldstr    aSealed// "Sealed"
0x4b922  ldc.i4.s 0x11
0x4b924  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b929  dup
0x4b92a  ldstr    aShowinfiltersp// "ShowInFiltersPane"
0x4b92f  ldc.i4.s 0x12
0x4b931  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b936  dup
0x4b937  ldstr    aStaticname// "StaticName"
0x4b93c  ldc.i4.s 0x13
0x4b93e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b943  dup
0x4b944  ldstr    aTitle// "Title"
0x4b949  ldc.i4.s 0x14
0x4b94b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b950  dup
0x4b951  ldstr    aFieldtypekind// "FieldTypeKind"
0x4b956  ldc.i4.s 0x15
0x4b958  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b95d  dup
0x4b95e  ldstr    aTypeasstring// "TypeAsString"
0x4b963  ldc.i4.s 0x16
0x4b965  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b96a  dup
0x4b96b  ldstr    aValidationform// "ValidationFormula"
0x4b970  ldc.i4.s 0x17
0x4b972  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b977  dup
0x4b978  ldstr    aValidationmess// "ValidationMessage"
0x4b97d  ldc.i4.s 0x18
0x4b97f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4b984  volatile.
0x4b986  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddf-1
0x4b98b  volatile.
0x4b98d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000ddf-1
0x4b992  ldloc.1
0x4b993  ldloca.s 2
0x4b995  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4b99a  brfalse  loc_4BCCA
0x4b99f  ldloc.2
0x4b9a0  switch   loc_4BA0E, loc_4BA2A, loc_4BA46, loc_4BA62, loc_4BA7E, loc_4BA9A, loc_4BAB6, loc_4BAD2, loc_4BAEE, loc_4BB0A, loc_4BB26, loc_4BB42, loc_4BB5E, loc_4BB7A, loc_4BB96, loc_4BBB2, loc_4BBCE, loc_4BBEA, loc_4BC06, loc_4BC22, loc_4BC3E, loc_4BC5A, loc_4BC76, loc_4BC92, loc_4BCAE
0x4ba09  br       loc_4BCCA
0x4ba0e  ldarg.0
0x4ba0f  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4ba14  ldarg.s  4
0x4ba16  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba1b  ldloc.0
0x4ba1c  ldarg.3
0x4ba1d  ldarg.s  4
0x4ba1f  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToGuid(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba24  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ClientSideComponentId(valuetype [mscorlib]System.Guid)
0x4ba29  ret
0x4ba2a  ldarg.0
0x4ba2b  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4ba30  ldarg.s  4
0x4ba32  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba37  ldloc.0
0x4ba38  ldarg.3
0x4ba39  ldarg.s  4
0x4ba3b  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba40  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ClientSideComponentProperties(string)
0x4ba45  ret
0x4ba46  ldarg.0
0x4ba47  ldstr    aCustomformatte// "CustomFormatter"
0x4ba4c  ldarg.s  4
0x4ba4e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba53  ldloc.0
0x4ba54  ldarg.3
0x4ba55  ldarg.s  4
0x4ba57  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba5c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_CustomFormatter(string)
0x4ba61  ret
0x4ba62  ldarg.0
0x4ba63  ldstr    aDefaultformula// "DefaultFormula"
0x4ba68  ldarg.s  4
0x4ba6a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba6f  ldloc.0
0x4ba70  ldarg.3
0x4ba71  ldarg.s  4
0x4ba73  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba78  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_DefaultFormula(string)
0x4ba7d  ret
0x4ba7e  ldarg.0
0x4ba7f  ldstr    aDefaultvalue// "DefaultValue"
0x4ba84  ldarg.s  4
0x4ba86  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba8b  ldloc.0
0x4ba8c  ldarg.3
0x4ba8d  ldarg.s  4
0x4ba8f  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4ba94  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_DefaultValue(string)
0x4ba99  ret
0x4ba9a  ldarg.0
0x4ba9b  ldstr    aDescription// "Description"
0x4baa0  ldarg.s  4
0x4baa2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4baa7  ldloc.0
0x4baa8  ldarg.3
0x4baa9  ldarg.s  4
0x4baab  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bab0  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Description(string)
0x4bab5  ret
0x4bab6  ldarg.0
0x4bab7  ldstr    aDirection// "Direction"
0x4babc  ldarg.s  4
0x4babe  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bac3  ldloc.0
0x4bac4  ldarg.3
0x4bac5  ldarg.s  4
0x4bac7  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bacc  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Direction(string)
0x4bad1  ret
0x4bad2  ldarg.0
0x4bad3  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4bad8  ldarg.s  4
0x4bada  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4badf  ldloc.0
0x4bae0  ldarg.3
0x4bae1  ldarg.s  4
0x4bae3  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bae8  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_EnforceUniqueValues(bool)
0x4baed  ret
0x4baee  ldarg.0
0x4baef  ldstr    aGroup// "Group"
0x4baf4  ldarg.s  4
0x4baf6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bafb  ldloc.0
0x4bafc  ldarg.3
0x4bafd  ldarg.s  4
0x4baff  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb04  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Group(string)
0x4bb09  ret
0x4bb0a  ldarg.0
0x4bb0b  ldstr    aHidden// "Hidden"
0x4bb10  ldarg.s  4
0x4bb12  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb17  ldloc.0
0x4bb18  ldarg.3
0x4bb19  ldarg.s  4
0x4bb1b  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb20  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Hidden(bool)
0x4bb25  ret
0x4bb26  ldarg.0
0x4bb27  ldstr    aIndexed// "Indexed"
0x4bb2c  ldarg.s  4
0x4bb2e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb33  ldloc.0
0x4bb34  ldarg.3
0x4bb35  ldarg.s  4
0x4bb37  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb3c  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_Indexed(bool)
0x4bb41  ret
0x4bb42  ldarg.0
0x4bb43  ldstr    aJslink// "JSLink"
0x4bb48  ldarg.s  4
0x4bb4a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb4f  ldloc.0
0x4bb50  ldarg.3
0x4bb51  ldarg.s  4
0x4bb53  call     string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToString(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb58  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_JSLink(string)
0x4bb5d  ret
0x4bb5e  ldarg.0
0x4bb5f  ldstr    aNocrawl// "NoCrawl"
0x4bb64  ldarg.s  4
0x4bb66  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb6b  ldloc.0
0x4bb6c  ldarg.3
0x4bb6d  ldarg.s  4
0x4bb6f  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb74  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_NoCrawl(bool)
0x4bb79  ret
0x4bb7a  ldarg.0
0x4bb7b  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4bb80  ldarg.s  4
0x4bb82  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb87  ldloc.0
0x4bb88  ldarg.3
0x4bb89  ldarg.s  4
0x4bb8b  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bb90  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_PinnedToFiltersPane(bool)
0x4bb95  ret
0x4bb96  ldarg.0
0x4bb97  ldstr    aReadonlyfield// "ReadOnlyField"
0x4bb9c  ldarg.s  4
0x4bb9e  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bba3  ldloc.0
0x4bba4  ldarg.3
0x4bba5  ldarg.s  4
0x4bba7  call     bool [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::ToBoolean(class [System.Xml]System.Xml.XmlNode, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bbac  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_ReadOnlyField(bool)
0x4bbb1  ret
0x4bbb2  ldarg.0
0x4bbb3  ldstr    aRequired// "Required"
0x4bbb8  ldarg.s  4
0x4bbba  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedSetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4bbbf  ldloc.0
0x4bbc0  ldarg.3
0x4bbc1  ldarg.s  4
  ... truncated ...
```
