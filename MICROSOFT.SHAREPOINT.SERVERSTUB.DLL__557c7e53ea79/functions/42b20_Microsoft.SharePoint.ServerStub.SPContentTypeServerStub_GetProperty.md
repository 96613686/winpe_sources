# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::GetProperty

- ea: `0x42b20`
- end: `0x42fc5`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::GetProperty`
- size: `1189`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x42b20`

## string_xrefs

- `0x42bb3`: `DocumentTemplateUrl`
- `0x42de0`: `DocumentTemplateUrl`
- `0x42c99`: `SchemaXml`
- `0x42f45`: `SchemaXml`
- `0x42ba7`: `DocumentTemplate`
- `0x42dcd`: `DocumentTemplate`
- `0x42b8f`: `DisplayFormTemplateName`
- `0x42da7`: `DisplayFormTemplateName`
- `0x42bbf`: `EditFormTemplateName`
- `0x42df3`: `EditFormTemplateName`
- `0x42bd7`: `FieldLinks`
- `0x42e19`: `FieldLinks`
- `0x42c17`: `JSLink`
- `0x42e82`: `JSLink`
- `0x42c65`: `NewFormTemplateName`
- `0x42ef4`: `NewFormTemplateName`
- `0x42c8c`: `ReadOnly`
- `0x42f2d`: `ReadOnly`
- `0x42ca6`: `SchemaXmlWithResourceTokens`
- `0x42f58`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x42b20  ldarg.2
0x42b21  brtrue.s loc_42B2E
0x42b23  ldstr    aPropname// "propName"
0x42b28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42b2d  throw
0x42b2e  ldarg.3
0x42b2f  brtrue.s loc_42B3C
0x42b31  ldstr    aProxycontext// "proxyContext"
0x42b36  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42b3b  throw
0x42b3c  ldarg.1
0x42b3d  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x42b42  stloc.0
0x42b43  ldloc.0
0x42b44  brtrue.s loc_42B51
0x42b46  ldstr    aTarget// "target"
0x42b4b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x42b50  throw
0x42b51  ldarg.0
0x42b52  ldarg.2
0x42b53  ldarg.3
0x42b54  call     instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::GetMemberName(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42b59  starg.s  2
0x42b5b  ldarg.2
0x42b5c  dup
0x42b5d  stloc.1
0x42b5e  brfalse  loc_42FBB
0x42b63  volatile.
0x42b65  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c90-1
0x42b6a  brtrue   loc_42CED
0x42b6f  ldc.i4.s 0x1D
0x42b71  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x42b76  dup
0x42b77  ldstr    aDescription// "Description"
0x42b7c  ldc.i4.0
0x42b7d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42b82  dup
0x42b83  ldstr    aDescriptionres// "DescriptionResource"
0x42b88  ldc.i4.1
0x42b89  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42b8e  dup
0x42b8f  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x42b94  ldc.i4.2
0x42b95  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42b9a  dup
0x42b9b  ldstr    aDisplayformurl// "DisplayFormUrl"
0x42ba0  ldc.i4.3
0x42ba1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42ba6  dup
0x42ba7  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x42bac  ldc.i4.4
0x42bad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bb2  dup
0x42bb3  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x42bb8  ldc.i4.5
0x42bb9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bbe  dup
0x42bbf  ldstr    aEditformtempla// "EditFormTemplateName"
0x42bc4  ldc.i4.6
0x42bc5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bca  dup
0x42bcb  ldstr    aEditformurl// "EditFormUrl"
0x42bd0  ldc.i4.7
0x42bd1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bd6  dup
0x42bd7  ldstr    aFieldlinks// "FieldLinks"
0x42bdc  ldc.i4.8
0x42bdd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42be2  dup
0x42be3  ldstr    aFields// "Fields"
0x42be8  ldc.i4.s 9
0x42bea  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bef  dup
0x42bf0  ldstr    aGroup// "Group"
0x42bf5  ldc.i4.s 0xA
0x42bf7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42bfc  dup
0x42bfd  ldstr    aHidden// "Hidden"
0x42c02  ldc.i4.s 0xB
0x42c04  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c09  dup
0x42c0a  ldstr    aId_0// "Id"
0x42c0f  ldc.i4.s 0xC
0x42c11  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c16  dup
0x42c17  ldstr    aJslink// "JSLink"
0x42c1c  ldc.i4.s 0xD
0x42c1e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c23  dup
0x42c24  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x42c29  ldc.i4.s 0xE
0x42c2b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c30  dup
0x42c31  ldstr    aMobileeditform// "MobileEditFormUrl"
0x42c36  ldc.i4.s 0xF
0x42c38  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c3d  dup
0x42c3e  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x42c43  ldc.i4.s 0x10
0x42c45  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c4a  dup
0x42c4b  ldstr    aName// "Name"
0x42c50  ldc.i4.s 0x11
0x42c52  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c57  dup
0x42c58  ldstr    aNameresource// "NameResource"
0x42c5d  ldc.i4.s 0x12
0x42c5f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c64  dup
0x42c65  ldstr    aNewformtemplat// "NewFormTemplateName"
0x42c6a  ldc.i4.s 0x13
0x42c6c  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c71  dup
0x42c72  ldstr    aNewformurl// "NewFormUrl"
0x42c77  ldc.i4.s 0x14
0x42c79  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c7e  dup
0x42c7f  ldstr    aParent// "Parent"
0x42c84  ldc.i4.s 0x15
0x42c86  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c8b  dup
0x42c8c  ldstr    aReadonly// "ReadOnly"
0x42c91  ldc.i4.s 0x16
0x42c93  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42c98  dup
0x42c99  ldstr    aSchemaxml// "SchemaXml"
0x42c9e  ldc.i4.s 0x17
0x42ca0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42ca5  dup
0x42ca6  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x42cab  ldc.i4.s 0x18
0x42cad  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42cb2  dup
0x42cb3  ldstr    aScope// "Scope"
0x42cb8  ldc.i4.s 0x19
0x42cba  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42cbf  dup
0x42cc0  ldstr    aSealed// "Sealed"
0x42cc5  ldc.i4.s 0x1A
0x42cc7  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42ccc  dup
0x42ccd  ldstr    aStringid// "StringId"
0x42cd2  ldc.i4.s 0x1B
0x42cd4  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42cd9  dup
0x42cda  ldstr    aWorkflowassoci// "WorkflowAssociations"
0x42cdf  ldc.i4.s 0x1C
0x42ce1  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x42ce6  volatile.
0x42ce8  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c90-1
0x42ced  volatile.
0x42cef  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c90-1
0x42cf4  ldloc.1
0x42cf5  ldloca.s 2
0x42cf7  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x42cfc  brfalse  loc_42FBB
0x42d01  ldloc.2
0x42d02  switch   loc_42D80, loc_42D93, loc_42DA6, loc_42DB9, loc_42DCC, loc_42DDF, loc_42DF2, loc_42E05, loc_42E18, loc_42E2B, loc_42E3E, loc_42E51, loc_42E69, loc_42E81, loc_42E94, loc_42EA7, loc_42EBA, loc_42ECD, loc_42EE0, loc_42EF3, loc_42F06, loc_42F19, loc_42F2C, loc_42F44, loc_42F57, loc_42F6A, loc_42F7D, loc_42F95, loc_42FA8
0x42d7b  br       loc_42FBB
0x42d80  ldarg.0
0x42d81  ldstr    aDescription// "Description"
0x42d86  ldarg.3
0x42d87  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42d8c  ldloc.0
0x42d8d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Description()
0x42d92  ret
0x42d93  ldarg.0
0x42d94  ldstr    aDescriptionres// "DescriptionResource"
0x42d99  ldarg.3
0x42d9a  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42d9f  ldloc.0
0x42da0  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DescriptionResource()
0x42da5  ret
0x42da6  ldarg.0
0x42da7  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x42dac  ldarg.3
0x42dad  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42db2  ldloc.0
0x42db3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormTemplateName()
0x42db8  ret
0x42db9  ldarg.0
0x42dba  ldstr    aDisplayformurl// "DisplayFormUrl"
0x42dbf  ldarg.3
0x42dc0  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42dc5  ldloc.0
0x42dc6  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormUrl()
0x42dcb  ret
0x42dcc  ldarg.0
0x42dcd  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x42dd2  ldarg.3
0x42dd3  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42dd8  ldloc.0
0x42dd9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DocumentTemplate()
0x42dde  ret
0x42ddf  ldarg.0
0x42de0  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x42de5  ldarg.3
0x42de6  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42deb  ldloc.0
0x42dec  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DocumentTemplateUrl()
0x42df1  ret
0x42df2  ldarg.0
0x42df3  ldstr    aEditformtempla// "EditFormTemplateName"
0x42df8  ldarg.3
0x42df9  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42dfe  ldloc.0
0x42dff  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_EditFormTemplateName()
0x42e04  ret
0x42e05  ldarg.0
0x42e06  ldstr    aEditformurl// "EditFormUrl"
0x42e0b  ldarg.3
0x42e0c  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e11  ldloc.0
0x42e12  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_EditFormUrl()
0x42e17  ret
0x42e18  ldarg.0
0x42e19  ldstr    aFieldlinks// "FieldLinks"
0x42e1e  ldarg.3
0x42e1f  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e24  ldloc.0
0x42e25  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldLinkCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_FieldLinks()
0x42e2a  ret
0x42e2b  ldarg.0
0x42e2c  ldstr    aFields// "Fields"
0x42e31  ldarg.3
0x42e32  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e37  ldloc.0
0x42e38  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Fields()
0x42e3d  ret
0x42e3e  ldarg.0
0x42e3f  ldstr    aGroup// "Group"
0x42e44  ldarg.3
0x42e45  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e4a  ldloc.0
0x42e4b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Group()
0x42e50  ret
0x42e51  ldarg.0
0x42e52  ldstr    aHidden// "Hidden"
0x42e57  ldarg.3
0x42e58  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e5d  ldloc.0
0x42e5e  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Hidden()
0x42e63  box      [mscorlib]System.Boolean
0x42e68  ret
0x42e69  ldarg.0
0x42e6a  ldstr    aId_0// "Id"
0x42e6f  ldarg.3
0x42e70  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e75  ldloc.0
0x42e76  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Id()
0x42e7b  box      [Microsoft.SharePoint]Microsoft.SharePoint.SPContentTypeId
0x42e80  ret
0x42e81  ldarg.0
0x42e82  ldstr    aJslink// "JSLink"
0x42e87  ldarg.3
0x42e88  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42e8d  ldloc.0
0x42e8e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_JSLink()
0x42e93  ret
0x42e94  ldarg.0
0x42e95  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x42e9a  ldarg.3
0x42e9b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42ea0  ldloc.0
0x42ea1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileDisplayFormUrl()
0x42ea6  ret
0x42ea7  ldarg.0
0x42ea8  ldstr    aMobileeditform// "MobileEditFormUrl"
0x42ead  ldarg.3
0x42eae  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42eb3  ldloc.0
0x42eb4  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileEditFormUrl()
0x42eb9  ret
0x42eba  ldarg.0
0x42ebb  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x42ec0  ldarg.3
0x42ec1  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42ec6  ldloc.0
0x42ec7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_MobileNewFormUrl()
0x42ecc  ret
0x42ecd  ldarg.0
0x42ece  ldstr    aName// "Name"
0x42ed3  ldarg.3
0x42ed4  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42ed9  ldloc.0
0x42eda  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Name()
0x42edf  ret
0x42ee0  ldarg.0
0x42ee1  ldstr    aNameresource// "NameResource"
0x42ee6  ldarg.3
0x42ee7  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42eec  ldloc.0
0x42eed  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_NameResource()
0x42ef2  ret
0x42ef3  ldarg.0
0x42ef4  ldstr    aNewformtemplat// "NewFormTemplateName"
0x42ef9  ldarg.3
0x42efa  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x42eff  ldloc.0
0x42f00  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_NewFormTemplateName()
  ... truncated ...
```
