# Microsoft.SharePoint.ServerStub.SPFieldServerStub::.cctor

- ea: `0x4dbe0`
- end: `0x4dd91`
- name: `Microsoft.SharePoint.ServerStub.SPFieldServerStub::.cctor`
- size: `433`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## string_xrefs

- `0x4dcb1`: `SchemaXml`
- `0x4dc84`: `JSLink`
- `0x4dcba`: `SchemaXmlWithResourceTokens`
- `0x4dd60`: `SchemaXmlWithResourceTokens`
- `0x4dbfa`: `ClientSideComponentId`
- `0x4dc02`: `ClientSideComponentProperties`
- `0x4dbf2`: `CanBeDeleted`
- `0x4dc9f`: `ReadOnlyField`

## pseudocode

```c

```

## disassembly

```asm
0x4dbe0  ldc.i4.s 0x25
0x4dbe2  newarr   [mscorlib]System.String
0x4dbe7  stloc.0
0x4dbe8  ldloc.0
0x4dbe9  ldc.i4.0
0x4dbea  ldstr    aAutoindexed// "AutoIndexed"
0x4dbef  stelem.ref
0x4dbf0  ldloc.0
0x4dbf1  ldc.i4.1
0x4dbf2  ldstr    aCanbedeleted// "CanBeDeleted"
0x4dbf7  stelem.ref
0x4dbf8  ldloc.0
0x4dbf9  ldc.i4.2
0x4dbfa  ldstr    aClientsidecomp// "ClientSideComponentId"
0x4dbff  stelem.ref
0x4dc00  ldloc.0
0x4dc01  ldc.i4.3
0x4dc02  ldstr    aClientsidecomp_0// "ClientSideComponentProperties"
0x4dc07  stelem.ref
0x4dc08  ldloc.0
0x4dc09  ldc.i4.4
0x4dc0a  ldstr    aCustomformatte// "CustomFormatter"
0x4dc0f  stelem.ref
0x4dc10  ldloc.0
0x4dc11  ldc.i4.5
0x4dc12  ldstr    aDefaultformula// "DefaultFormula"
0x4dc17  stelem.ref
0x4dc18  ldloc.0
0x4dc19  ldc.i4.6
0x4dc1a  ldstr    aDefaultvalue// "DefaultValue"
0x4dc1f  stelem.ref
0x4dc20  ldloc.0
0x4dc21  ldc.i4.7
0x4dc22  ldstr    aDescription// "Description"
0x4dc27  stelem.ref
0x4dc28  ldloc.0
0x4dc29  ldc.i4.8
0x4dc2a  ldstr    aDirection// "Direction"
0x4dc2f  stelem.ref
0x4dc30  ldloc.0
0x4dc31  ldc.i4.s 9
0x4dc33  ldstr    aEnforceuniquev// "EnforceUniqueValues"
0x4dc38  stelem.ref
0x4dc39  ldloc.0
0x4dc3a  ldc.i4.s 0xA
0x4dc3c  ldstr    aEntityproperty// "EntityPropertyName"
0x4dc41  stelem.ref
0x4dc42  ldloc.0
0x4dc43  ldc.i4.s 0xB
0x4dc45  ldstr    aFilterable// "Filterable"
0x4dc4a  stelem.ref
0x4dc4b  ldloc.0
0x4dc4c  ldc.i4.s 0xC
0x4dc4e  ldstr    aFrombasetype// "FromBaseType"
0x4dc53  stelem.ref
0x4dc54  ldloc.0
0x4dc55  ldc.i4.s 0xD
0x4dc57  ldstr    aGroup// "Group"
0x4dc5c  stelem.ref
0x4dc5d  ldloc.0
0x4dc5e  ldc.i4.s 0xE
0x4dc60  ldstr    aHidden// "Hidden"
0x4dc65  stelem.ref
0x4dc66  ldloc.0
0x4dc67  ldc.i4.s 0xF
0x4dc69  ldstr    aId_0// "Id"
0x4dc6e  stelem.ref
0x4dc6f  ldloc.0
0x4dc70  ldc.i4.s 0x10
0x4dc72  ldstr    aIndexed// "Indexed"
0x4dc77  stelem.ref
0x4dc78  ldloc.0
0x4dc79  ldc.i4.s 0x11
0x4dc7b  ldstr    aInternalname// "InternalName"
0x4dc80  stelem.ref
0x4dc81  ldloc.0
0x4dc82  ldc.i4.s 0x12
0x4dc84  ldstr    aJslink// "JSLink"
0x4dc89  stelem.ref
0x4dc8a  ldloc.0
0x4dc8b  ldc.i4.s 0x13
0x4dc8d  ldstr    aNocrawl// "NoCrawl"
0x4dc92  stelem.ref
0x4dc93  ldloc.0
0x4dc94  ldc.i4.s 0x14
0x4dc96  ldstr    aPinnedtofilter// "PinnedToFiltersPane"
0x4dc9b  stelem.ref
0x4dc9c  ldloc.0
0x4dc9d  ldc.i4.s 0x15
0x4dc9f  ldstr    aReadonlyfield// "ReadOnlyField"
0x4dca4  stelem.ref
0x4dca5  ldloc.0
0x4dca6  ldc.i4.s 0x16
0x4dca8  ldstr    aRequired// "Required"
0x4dcad  stelem.ref
0x4dcae  ldloc.0
0x4dcaf  ldc.i4.s 0x17
0x4dcb1  ldstr    aSchemaxml// "SchemaXml"
0x4dcb6  stelem.ref
0x4dcb7  ldloc.0
0x4dcb8  ldc.i4.s 0x18
0x4dcba  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4dcbf  stelem.ref
0x4dcc0  ldloc.0
0x4dcc1  ldc.i4.s 0x19
0x4dcc3  ldstr    aScope// "Scope"
0x4dcc8  stelem.ref
0x4dcc9  ldloc.0
0x4dcca  ldc.i4.s 0x1A
0x4dccc  ldstr    aSealed// "Sealed"
0x4dcd1  stelem.ref
0x4dcd2  ldloc.0
0x4dcd3  ldc.i4.s 0x1B
0x4dcd5  ldstr    aShowinfiltersp// "ShowInFiltersPane"
0x4dcda  stelem.ref
0x4dcdb  ldloc.0
0x4dcdc  ldc.i4.s 0x1C
0x4dcde  ldstr    aSortable// "Sortable"
0x4dce3  stelem.ref
0x4dce4  ldloc.0
0x4dce5  ldc.i4.s 0x1D
0x4dce7  ldstr    aStaticname// "StaticName"
0x4dcec  stelem.ref
0x4dced  ldloc.0
0x4dcee  ldc.i4.s 0x1E
0x4dcf0  ldstr    aTitle// "Title"
0x4dcf5  stelem.ref
0x4dcf6  ldloc.0
0x4dcf7  ldc.i4.s 0x1F
0x4dcf9  ldstr    aFieldtypekind// "FieldTypeKind"
0x4dcfe  stelem.ref
0x4dcff  ldloc.0
0x4dd00  ldc.i4.s 0x20
0x4dd02  ldstr    aTypeasstring// "TypeAsString"
0x4dd07  stelem.ref
0x4dd08  ldloc.0
0x4dd09  ldc.i4.s 0x21
0x4dd0b  ldstr    aTypedisplaynam// "TypeDisplayName"
0x4dd10  stelem.ref
0x4dd11  ldloc.0
0x4dd12  ldc.i4.s 0x22
0x4dd14  ldstr    aTypeshortdescr// "TypeShortDescription"
0x4dd19  stelem.ref
0x4dd1a  ldloc.0
0x4dd1b  ldc.i4.s 0x23
0x4dd1d  ldstr    aValidationform// "ValidationFormula"
0x4dd22  stelem.ref
0x4dd23  ldloc.0
0x4dd24  ldc.i4.s 0x24
0x4dd26  ldstr    aValidationmess// "ValidationMessage"
0x4dd2b  stelem.ref
0x4dd2c  ldloc.0
0x4dd2d  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFieldServerStub::s_valueProperties
0x4dd32  ldc.i4.2
0x4dd33  newarr   [mscorlib]System.String
0x4dd38  stloc.1
0x4dd39  ldloc.1
0x4dd3a  ldc.i4.0
0x4dd3b  ldstr    aDescriptionres// "DescriptionResource"
0x4dd40  stelem.ref
0x4dd41  ldloc.1
0x4dd42  ldc.i4.1
0x4dd43  ldstr    aTitleresource// "TitleResource"
0x4dd48  stelem.ref
0x4dd49  ldloc.1
0x4dd4a  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFieldServerStub::s_refProperties
0x4dd4f  ldc.i4.2
0x4dd50  newarr   [mscorlib]System.String
0x4dd55  stloc.2
0x4dd56  ldloc.2
0x4dd57  ldc.i4.0
0x4dd58  ldstr    aNocrawl// "NoCrawl"
0x4dd5d  stelem.ref
0x4dd5e  ldloc.2
0x4dd5f  ldc.i4.1
0x4dd60  ldstr    aSchemaxmlwithr// "SchemaXmlWithResourceTokens"
0x4dd65  stelem.ref
0x4dd66  ldloc.2
0x4dd67  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFieldServerStub::s_excludeFromDefaultRetrieveProperties
0x4dd6c  ldstr    aC4121b040f574b// "{c4121b04-0f57-4b1d-a145-d25426b16480}"
0x4dd71  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x4dd76  stsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ServerStub.SPFieldServerStub::s_targetTypeId
0x4dd7b  ldc.i4.1
0x4dd7c  newarr   [mscorlib]System.String
0x4dd81  stloc.3
0x4dd82  ldloc.3
0x4dd83  ldc.i4.0
0x4dd84  ldstr    aId_0// "Id"
0x4dd89  stelem.ref
0x4dd8a  ldloc.3
0x4dd8b  stsfld   string[] Microsoft.SharePoint.ServerStub.SPFieldServerStub::s_keyProperties
0x4dd90  ret
```
