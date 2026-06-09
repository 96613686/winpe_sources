# Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::.cctor

- ea: `0x44970`
- end: `0x44abb`
- name: `Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::.cctor`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## string_xrefs

- `0x4499a`: `DocumentTemplateUrl`
- `0x44a14`: `SchemaXml`
- `0x44992`: `DocumentTemplate`
- `0x44982`: `DisplayFormTemplateName`
- `0x449a2`: `EditFormTemplateName`
- `0x44a55`: `FieldLinks`
- `0x449cc`: `JSLink`
- `0x449f9`: `NewFormTemplateName`
- `0x44a0b`: `ReadOnly`
- `0x44a1d`: `SchemaXmlWithResourceTokens`
- `0x44a8a`: `SchemaXmlWithResourceTokens`

## pseudocode

```c

```

## disassembly

```asm
0x44970  ldc.i4.s 0x17
0x44972  newarr   [mscorlib]System.String
0x44977  stloc.0
0x44978  ldloc.0
0x44979  ldc.i4.0
0x4497a  ldstr    aDescription// "Description"
0x4497f  stelem.ref
0x44980  ldloc.0
0x44981  ldc.i4.1
0x44982  ldstr    aDisplayformtem// "DisplayFormTemplateName"
0x44987  stelem.ref
0x44988  ldloc.0
0x44989  ldc.i4.2
0x4498a  ldstr    aDisplayformurl// "DisplayFormUrl"
0x4498f  stelem.ref
0x44990  ldloc.0
0x44991  ldc.i4.3
0x44992  ldstr    aDocumenttempla_2// "DocumentTemplate"
0x44997  stelem.ref
0x44998  ldloc.0
0x44999  ldc.i4.4
0x4499a  ldstr    aDocumenttempla// "DocumentTemplateUrl"
0x4499f  stelem.ref
0x449a0  ldloc.0
0x449a1  ldc.i4.5
0x449a2  ldstr    aEditformtempla// "EditFormTemplateName"
0x449a7  stelem.ref
0x449a8  ldloc.0
0x449a9  ldc.i4.6
0x449aa  ldstr    aEditformurl// "EditFormUrl"
0x449af  stelem.ref
0x449b0  ldloc.0
0x449b1  ldc.i4.7
0x449b2  ldstr    aGroup// "Group"
0x449b7  stelem.ref
0x449b8  ldloc.0
0x449b9  ldc.i4.8
0x449ba  ldstr    aHidden// "Hidden"
0x449bf  stelem.ref
0x449c0  ldloc.0
0x449c1  ldc.i4.s 9
0x449c3  ldstr    aId_0// "Id"
0x449c8  stelem.ref
0x449c9  ldloc.0
0x449ca  ldc.i4.s 0xA
0x449cc  ldstr    aJslink// "JSLink"
0x449d1  stelem.ref
0x449d2  ldloc.0
0x449d3  ldc.i4.s 0xB
0x449d5  ldstr    aMobiledisplayf// "MobileDisplayFormUrl"
0x449da  stelem.ref
0x449db  ldloc.0
0x449dc  ldc.i4.s 0xC
0x449de  ldstr    aMobileeditform// "MobileEditFormUrl"
0x449e3  stelem.ref
0x449e4  ldloc.0
0x449e5  ldc.i4.s 0xD
0x449e7  ldstr    aMobilenewformu// "MobileNewFormUrl"
0x449ec  stelem.ref
0x449ed  ldloc.0
0x449ee  ldc.i4.s 0xE
0x449f0  ldstr    aName// "Name"
0x449f5  stelem.ref
0x449f6  ldloc.0
0x449f7  ldc.i4.s 0xF
0x449f9  ldstr    aNewformtemplat// "NewFormTemplateName"
0x449fe  stelem.ref
0x449ff  ldloc.0
0x44a00  ldc.i4.s 0x10
0x44a02  ldstr    aNewformurl// "NewFormUrl"
0x44a07  stelem.ref
0x44a08  ldloc.0
0x44a09  ldc.i4.s 0x11
0x44a0b  ldstr    aReadonly// "ReadOnly"
0x44a10  stelem.ref
0x44a11  ldloc.0
0x44a12  ldc.i4.s 0x12
0x44a14  ldstr    aSchemaxml// "SchemaXml"
0x44a19  stelem.ref
0x44a1a  ldloc.0
0x44a1b  ldc.i4.s 0x13
0x44a1d  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x44a22  stelem.ref
0x44a23  ldloc.0
0x44a24  ldc.i4.s 0x14
0x44a26  ldstr    aScope// "Scope"
0x44a2b  stelem.ref
0x44a2c  ldloc.0
0x44a2d  ldc.i4.s 0x15
0x44a2f  ldstr    aSealed// "Sealed"
0x44a34  stelem.ref
0x44a35  ldloc.0
0x44a36  ldc.i4.s 0x16
0x44a38  ldstr    aStringid// "StringId"
0x44a3d  stelem.ref
0x44a3e  ldloc.0
0x44a3f  stsfld   string[] Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::s_valueProperties
0x44a44  ldc.i4.6
0x44a45  newarr   [mscorlib]System.String
0x44a4a  stloc.1
0x44a4b  ldloc.1
0x44a4c  ldc.i4.0
0x44a4d  ldstr    aDescriptionres// "DescriptionResource"
0x44a52  stelem.ref
0x44a53  ldloc.1
0x44a54  ldc.i4.1
0x44a55  ldstr    aFieldlinks// "FieldLinks"
0x44a5a  stelem.ref
0x44a5b  ldloc.1
0x44a5c  ldc.i4.2
0x44a5d  ldstr    aFields// "Fields"
0x44a62  stelem.ref
0x44a63  ldloc.1
0x44a64  ldc.i4.3
0x44a65  ldstr    aNameresource// "NameResource"
0x44a6a  stelem.ref
0x44a6b  ldloc.1
0x44a6c  ldc.i4.4
0x44a6d  ldstr    aParent// "Parent"
0x44a72  stelem.ref
0x44a73  ldloc.1
0x44a74  ldc.i4.5
0x44a75  ldstr    aWorkflowassoci// "WorkflowAssociations"
0x44a7a  stelem.ref
0x44a7b  ldloc.1
0x44a7c  stsfld   string[] Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::s_refProperties
0x44a81  ldc.i4.1
0x44a82  newarr   [mscorlib]System.String
0x44a87  stloc.2
0x44a88  ldloc.2
0x44a89  ldc.i4.0
0x44a8a  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x44a8f  stelem.ref
0x44a90  ldloc.2
0x44a91  stsfld   string[] Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::s_excludeFromDefaultRetrieveProperties
0x44a96  ldstr    a91b5bd2dE13348// "{91b5bd2d-e133-486f-b727-197ce5eb2c0d}"
0x44a9b  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x44aa0  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::s_targetTypeId
0x44aa5  ldc.i4.1
0x44aa6  newarr   [mscorlib]System.String
0x44aab  stloc.3
0x44aac  ldloc.3
0x44aad  ldc.i4.0
0x44aae  ldstr    aStringid// "StringId"
0x44ab3  stelem.ref
0x44ab4  ldloc.3
0x44ab5  stsfld   string[] Microsoft.SharePoint.ServerStub.SPContentTypeServerStub::s_keyProperties
0x44aba  ret
```
