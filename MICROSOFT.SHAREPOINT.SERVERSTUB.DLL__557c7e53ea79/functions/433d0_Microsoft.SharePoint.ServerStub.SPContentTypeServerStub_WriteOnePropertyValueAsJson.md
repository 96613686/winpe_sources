# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::WriteOnePropertyValueAsJson

- ea: `0x433d0`
- end: `0x43ea5`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::WriteOnePropertyValueAsJson`
- size: `2773`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x433d0`

## string_xrefs

- `0x43444`: `DocumentTemplateUrl`
- `0x437b3`: `DocumentTemplateUrl`
- `0x4352a`: `SchemaXml`
- `0x43d03`: `SchemaXml`
- `0x43438`: `DocumentTemplate`
- `0x43769`: `DocumentTemplate`
- `0x43420`: `DisplayFormTemplateName`
- `0x436d5`: `DisplayFormTemplateName`
- `0x43450`: `EditFormTemplateName`
- `0x437fd`: `EditFormTemplateName`
- `0x43468`: `FieldLinks`
- `0x43891`: `FieldLinks`
- `0x434a8`: `JSLink`
- `0x43a11`: `JSLink`
- `0x434f6`: `NewFormTemplateName`
- `0x43bd4`: `NewFormTemplateName`
- `0x4351d`: `ReadOnly`
- `0x43cb9`: `ReadOnly`
- `0x43537`: `SchemaXmlWithResourceTokens`
- `0x43d4d`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x433d0  ldc.i4.0
0x433d1  stloc.0
0x433d2  ldarg.2
0x433d3  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType
0x433d8  stloc.1
0x433d9  ldloc.1
0x433da  brtrue.s loc_433E7
0x433dc  ldstr    aTarget// "target"
0x433e1  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x433e6  throw
0x433e7  ldarg.3
0x433e8  callvirt instance string [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_Name()
0x433ed  dup
0x433ee  stloc.2
0x433ef  brfalse  loc_43E97
0x433f4  volatile.
0x433f6  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c94-1
0x433fb  brtrue   loc_4357E
0x43400  ldc.i4.s 0x1D
0x43402  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0x43407  dup
0x43408  ldstr    aDescription// "Description"
0x4340d  ldc.i4.0
0x4340e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43413  dup
0x43414  ldstr    aDescriptionres// "DescriptionResource"
0x43419  ldc.i4.1
0x4341a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4341f  dup
0x43420  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x43425  ldc.i4.2
0x43426  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4342b  dup
0x4342c  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43431  ldc.i4.3
0x43432  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43437  dup
0x43438  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x4343d  ldc.i4.4
0x4343e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43443  dup
0x43444  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x43449  ldc.i4.5
0x4344a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4344f  dup
0x43450  ldstr    aEditformtempla// "EditFormTemplateName"
0x43455  ldc.i4.6
0x43456  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4345b  dup
0x4345c  ldstr    aEditformurl// "EditFormUrl"
0x43461  ldc.i4.7
0x43462  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43467  dup
0x43468  ldstr    aFieldlinks// "FieldLinks"
0x4346d  ldc.i4.8
0x4346e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43473  dup
0x43474  ldstr    aFields// "Fields"
0x43479  ldc.i4.s 9
0x4347b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43480  dup
0x43481  ldstr    aGroup// "Group"
0x43486  ldc.i4.s 0xA
0x43488  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4348d  dup
0x4348e  ldstr    aHidden// "Hidden"
0x43493  ldc.i4.s 0xB
0x43495  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4349a  dup
0x4349b  ldstr    aId_0// "Id"
0x434a0  ldc.i4.s 0xC
0x434a2  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434a7  dup
0x434a8  ldstr    aJslink// "JSLink"
0x434ad  ldc.i4.s 0xD
0x434af  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434b4  dup
0x434b5  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x434ba  ldc.i4.s 0xE
0x434bc  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434c1  dup
0x434c2  ldstr    aMobileeditform// "MobileEditFormUrl"
0x434c7  ldc.i4.s 0xF
0x434c9  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434ce  dup
0x434cf  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x434d4  ldc.i4.s 0x10
0x434d6  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434db  dup
0x434dc  ldstr    aName// "Name"
0x434e1  ldc.i4.s 0x11
0x434e3  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434e8  dup
0x434e9  ldstr    aNameresource// "NameResource"
0x434ee  ldc.i4.s 0x12
0x434f0  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x434f5  dup
0x434f6  ldstr    aNewformtemplat// "NewFormTemplateName"
0x434fb  ldc.i4.s 0x13
0x434fd  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43502  dup
0x43503  ldstr    aNewformurl// "NewFormUrl"
0x43508  ldc.i4.s 0x14
0x4350a  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4350f  dup
0x43510  ldstr    aParent// "Parent"
0x43515  ldc.i4.s 0x15
0x43517  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4351c  dup
0x4351d  ldstr    aReadonly// "ReadOnly"
0x43522  ldc.i4.s 0x16
0x43524  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43529  dup
0x4352a  ldstr    aSchemaxml// "SchemaXml"
0x4352f  ldc.i4.s 0x17
0x43531  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43536  dup
0x43537  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4353c  ldc.i4.s 0x18
0x4353e  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43543  dup
0x43544  ldstr    aScope// "Scope"
0x43549  ldc.i4.s 0x19
0x4354b  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43550  dup
0x43551  ldstr    aSealed// "Sealed"
0x43556  ldc.i4.s 0x1A
0x43558  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4355d  dup
0x4355e  ldstr    aStringid// "StringId"
0x43563  ldc.i4.s 0x1B
0x43565  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x4356a  dup
0x4356b  ldstr    aWorkflowassoci// "WorkflowAssociations"
0x43570  ldc.i4.s 0x1C
0x43572  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0x43577  volatile.
0x43579  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c94-1
0x4357e  volatile.
0x43580  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{0674EEC2-BDB4-4E42-971D-6EEC8C9C8639}::$$method0x6000c94-1
0x43585  ldloc.2
0x43586  ldloca.s 3
0x43588  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0x4358d  brfalse  loc_43E97
0x43592  ldloc.3
0x43593  switch   loc_43611, loc_4365B, loc_436AC, loc_436F6, loc_43740, loc_4378A, loc_437D4, loc_4381E, loc_43868, loc_438B9, loc_4390A, loc_43954, loc_4399E, loc_439E8, loc_43A32, loc_43A7C, loc_43AC6, loc_43B10, loc_43B5A, loc_43BAB, loc_43BF5, loc_43C3F, loc_43C90, loc_43CDA, loc_43D24, loc_43D6E, loc_43DB8, loc_43E02, loc_43E49
0x4360c  br       loc_43E97
0x43611  ldarg.3
0x43612  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43617  stloc.s  4
0x43619  ldloca.s 4
0x4361b  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x43620  brfalse.s loc_43639
0x43622  ldarg.3
0x43623  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43628  stloc.s  5
0x4362a  ldloca.s 5
0x4362c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x43631  brtrue.s loc_43639
0x43633  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x43638  throw
0x43639  ldarg.0
0x4363a  ldstr    aDescription// "Description"
0x4363f  ldarg.s  4
0x43641  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43646  ldc.i4.1
0x43647  stloc.0
0x43648  ldarg.1
0x43649  ldloc.1
0x4364a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_Description()
0x4364f  ldarg.s  4
0x43651  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43656  br       loc_43EA3
0x4365b  ldarg.3
0x4365c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43661  stloc.s  6
0x43663  ldloca.s 6
0x43665  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4366a  brfalse.s loc_43683
0x4366c  ldarg.3
0x4366d  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43672  stloc.s  7
0x43674  ldloca.s 7
0x43676  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x4367b  brfalse.s loc_43683
0x4367d  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x43682  throw
0x43683  ldarg.0
0x43684  ldstr    aDescriptionres// "DescriptionResource"
0x43689  ldarg.s  4
0x4368b  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43690  ldc.i4.1
0x43691  stloc.0
0x43692  ldarg.0
0x43693  ldarg.1
0x43694  ldloc.1
0x43695  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUserResource [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DescriptionResource()
0x4369a  ldarg.3
0x4369b  callvirt instance class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ObjectQuery()
0x436a0  ldarg.s  4
0x436a2  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::WriteQueryResult(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, object, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientObjectQuery, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x436a7  br       loc_43EA3
0x436ac  ldarg.3
0x436ad  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x436b2  stloc.s  8
0x436b4  ldloca.s 8
0x436b6  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x436bb  brfalse.s loc_436D4
0x436bd  ldarg.3
0x436be  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x436c3  stloc.s  9
0x436c5  ldloca.s 9
0x436c7  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x436cc  brtrue.s loc_436D4
0x436ce  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x436d3  throw
0x436d4  ldarg.0
0x436d5  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x436da  ldarg.s  4
0x436dc  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x436e1  ldc.i4.1
0x436e2  stloc.0
0x436e3  ldarg.1
0x436e4  ldloc.1
0x436e5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormTemplateName()
0x436ea  ldarg.s  4
0x436ec  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x436f1  br       loc_43EA3
0x436f6  ldarg.3
0x436f7  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x436fc  stloc.s  0xA
0x436fe  ldloca.s 0xA
0x43700  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x43705  brfalse.s loc_4371E
0x43707  ldarg.3
0x43708  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x4370d  stloc.s  0xB
0x4370f  ldloca.s 0xB
0x43711  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x43716  brtrue.s loc_4371E
0x43718  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x4371d  throw
0x4371e  ldarg.0
0x4371f  ldstr    aDisplayformurl// "DisplayFormUrl"
0x43724  ldarg.s  4
0x43726  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4372b  ldc.i4.1
0x4372c  stloc.0
0x4372d  ldarg.1
0x4372e  ldloc.1
0x4372f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DisplayFormUrl()
0x43734  ldarg.s  4
0x43736  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x4373b  br       loc_43EA3
0x43740  ldarg.3
0x43741  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43746  stloc.s  0xC
0x43748  ldloca.s 0xC
0x4374a  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x4374f  brfalse.s loc_43768
0x43751  ldarg.3
0x43752  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43757  stloc.s  0xD
0x43759  ldloca.s 0xD
0x4375b  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x43760  brtrue.s loc_43768
0x43762  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x43767  throw
0x43768  ldarg.0
0x43769  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x4376e  ldarg.s  4
0x43770  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43775  ldc.i4.1
0x43776  stloc.0
0x43777  ldarg.1
0x43778  ldloc.1
0x43779  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPContentType::get_DocumentTemplate()
0x4377e  ldarg.s  4
0x43780  call     void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.DataConverter::WriteString(class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.JsonWriter, string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x43785  br       loc_43EA3
0x4378a  ldarg.3
0x4378b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x43790  stloc.s  0xE
0x43792  ldloca.s 0xE
0x43794  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x43799  brfalse.s loc_437B2
0x4379b  ldarg.3
0x4379c  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ClientQueryProperty::get_ScalarProperty()
0x437a1  stloc.s  0xF
0x437a3  ldloca.s 0xF
0x437a5  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x437aa  brtrue.s loc_437B2
0x437ac  newobj   instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.InvalidClientQueryException::.ctor()
0x437b1  throw
0x437b2  ldarg.0
0x437b3  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x437b8  ldarg.s  4
0x437ba  call     instance void [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ServerStub::CheckBlockedGetProperty(string, class [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.ProxyContext)
0x437bf  ldc.i4.1
0x437c0  stloc.0
  ... truncated ...
```
