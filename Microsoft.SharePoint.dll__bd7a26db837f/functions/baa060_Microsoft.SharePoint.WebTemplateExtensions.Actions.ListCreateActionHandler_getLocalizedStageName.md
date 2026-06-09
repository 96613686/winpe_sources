# Microsoft.SharePoint.WebTemplateExtensions.Actions.ListCreateActionHandler::_getLocalizedStageName

- ea: `0xbaa060`
- end: `0xbaa297`
- name: `Microsoft.SharePoint.WebTemplateExtensions.Actions.ListCreateActionHandler::_getLocalizedStageName`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xbaa720`

## callees

- `0xba68e0`
- `0xbaa060`
- `0xbaa670`

## string_xrefs

- `0xbaa08f`: `schemaXml`
- `0xbaa0fb`: `deleteSPField`
- `0xbaa080`: `addSPFieldXml`
- `0xbaa12b`: `removeContentType`
- `0xbaa14f`: `associateListViewCommandSet`
- `0xbaa168`: `removeSPView`
- `0xbaa06e`: `WebTemplateExtensionsFeature_Desc_SetListDescription`
- `0xbaa0af`: `WebTemplateExtensionsFeature_Desc_AddFieldToListXML`
- `0xbaa1ce`: `WebTemplateExtensionsFeature_Desc_AddColumn`
- `0xbaa1df`: `WebTemplateExtensionsFeature_Desc_RemoveColumn`
- `0xbaa1f0`: `WebTemplateExtensionsFeature_Desc_AddSiteColumnToList`
- `0xbaa1fe`: `WebTemplateExtensionsFeature_Desc_SetListTitle`
- `0xbaa20c`: `WebTemplateExtensionsFeature_Desc_AddListContentType`
- `0xbaa21a`: `WebTemplateExtensionsFeature_Desc_RemoveListContentType`
- `0xbaa228`: `WebTemplateExtensionsFeature_Desc_SetFieldCustomFormatter`
- `0xbaa236`: `WebTemplateExtensionsFeature_Desc_AssociateFieldCustomizer`
- `0xbaa244`: `WebTemplateExtensionsFeature_Desc_AssociateListViewCommandSet`
- `0xbaa252`: `WebTemplateExtensionsFeature_Desc_AddView`
- `0xbaa260`: `WebTemplateExtensionsFeature_Desc_RemoveView`

## pseudocode

```c

```

## disassembly

```asm
0xbaa060  ldarg.2
0xbaa061  ldstr    aSetdescription// "setDescription"
0xbaa066  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbaa06b  brfalse.s loc_BAA07F
0xbaa06d  ldarg.0
0xbaa06e  ldstr    aWebtemplateext_30// "WebTemplateExtensionsFeature_Desc_SetLi"...
0xbaa073  ldc.i4.0
0xbaa074  newarr   [mscorlib]System.Object
0xbaa079  callvirt instance string Microsoft.SharePoint.WebTemplateExtensions.Actions.BaseActionHandler::LocalizedString(string stringKey, object[] args)
0xbaa07e  ret
0xbaa07f  ldarg.2
0xbaa080  ldstr    aAddspfieldxml// "addSPFieldXml"
0xbaa085  call     bool [mscorlib]System.String::op_Equality(string, string)
0xbaa08a  brfalse.s loc_BAA0D2
0xbaa08c  ldnull
0xbaa08d  stloc.1
0xbaa08e  ldarg.0
0xbaa08f  ldstr    aSchemaxml_0// "schemaXml"
0xbaa094  ldarg.1
0xbaa095  ldloca.s 0
0xbaa097  ldc.i4.0
0xbaa098  call     T0x2B00096C
0xbaa09d  brfalse.s loc_BAA0AE
0xbaa09f  ldloc.0
0xbaa0a0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xbaa0a5  brtrue.s loc_BAA0AE
0xbaa0a7  ldloc.0
0xbaa0a8  call     string Microsoft.SharePoint.WebTemplateExtensions.Actions.ListCreateActionHandler::GetInternalNameFromFieldXml(string fieldXml)
0xbaa0ad  stloc.1
0xbaa0ae  ldarg.0
0xbaa0af  ldstr    aWebtemplateext_31// "WebTemplateExtensionsFeature_Desc_AddFi"...
0xbaa0b4  ldc.i4.1
0xbaa0b5  newarr   [mscorlib]System.Object
0xbaa0ba  stloc.s  5
0xbaa0bc  ldloc.s  5
0xbaa0be  ldc.i4.0
0xbaa0bf  ldloc.1
0xbaa0c0  dup
0xbaa0c1  brtrue.s loc_BAA0C9
0xbaa0c3  pop
0xbaa0c4  ldsfld   string [mscorlib]System.String::Empty
0xbaa0c9  stelem.ref
0xbaa0ca  ldloc.s  5
0xbaa0cc  callvirt instance string Microsoft.SharePoint.WebTemplateExtensions.Actions.BaseActionHandler::LocalizedString(string stringKey, object[] args)
0xbaa0d1  ret
0xbaa0d2  ldarg.2
0xbaa0d3  dup
0xbaa0d4  stloc.s  6
0xbaa0d6  brfalse  loc_BAA268
0xbaa0db  volatile.
0xbaa0dd  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6021320-1
0xbaa0e2  brtrue   loc_BAA17B
0xbaa0e7  ldc.i4.s 0xB
0xbaa0e9  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::.ctor(int32)
0xbaa0ee  dup
0xbaa0ef  ldstr    aAddspfield// "addSPField"
0xbaa0f4  ldc.i4.0
0xbaa0f5  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa0fa  dup
0xbaa0fb  ldstr    aDeletespfield// "deleteSPField"
0xbaa100  ldc.i4.1
0xbaa101  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa106  dup
0xbaa107  ldstr    aAddsitecolumn// "addSiteColumn"
0xbaa10c  ldc.i4.2
0xbaa10d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa112  dup
0xbaa113  ldstr    aSettitle// "setTitle"
0xbaa118  ldc.i4.3
0xbaa119  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa11e  dup
0xbaa11f  ldstr    aAddcontenttype_0// "addContentType"
0xbaa124  ldc.i4.4
0xbaa125  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa12a  dup
0xbaa12b  ldstr    aRemovecontentt// "removeContentType"
0xbaa130  ldc.i4.5
0xbaa131  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa136  dup
0xbaa137  ldstr    aSetspfieldcust// "setSPFieldCustomFormatter"
0xbaa13c  ldc.i4.6
0xbaa13d  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa142  dup
0xbaa143  ldstr    aAssociatefield// "associateFieldCustomizer"
0xbaa148  ldc.i4.7
0xbaa149  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa14e  dup
0xbaa14f  ldstr    aAssociatelistv// "associateListViewCommandSet"
0xbaa154  ldc.i4.8
0xbaa155  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa15a  dup
0xbaa15b  ldstr    aAddspview// "addSPView"
0xbaa160  ldc.i4.s 9
0xbaa162  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa167  dup
0xbaa168  ldstr    aRemovespview// "removeSPView"
0xbaa16d  ldc.i4.s 0xA
0xbaa16f  call     instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::Add(var<u1>, !!T0)
0xbaa174  volatile.
0xbaa176  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6021320-1
0xbaa17b  volatile.
0xbaa17d  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32> <PrivateImplementationDetails>{7F5A19CB-910C-4E1B-81E8-035FE0963D88}::$$method0x6021320-1
0xbaa182  ldloc.s  6
0xbaa184  ldloca.s 7
0xbaa186  call     instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, int32>::TryGetValue(var<u1>, !!T0)
0xbaa18b  brfalse  loc_BAA268
0xbaa190  ldloc.s  7
0xbaa192  switch   loc_BAA1C8, loc_BAA1D9, loc_BAA1EA, loc_BAA1F8, loc_BAA206, loc_BAA214, loc_BAA222, loc_BAA230, loc_BAA23E, loc_BAA24C, loc_BAA25A
0xbaa1c3  br       loc_BAA268
0xbaa1c8  ldstr    aDisplayname_0// "displayName"
0xbaa1cd  stloc.3
0xbaa1ce  ldstr    aWebtemplateext_32// "WebTemplateExtensionsFeature_Desc_AddCo"...
0xbaa1d3  stloc.2
0xbaa1d4  br       loc_BAA26A
0xbaa1d9  ldstr    aDisplayname_0// "displayName"
0xbaa1de  stloc.3
0xbaa1df  ldstr    aWebtemplateext_33// "WebTemplateExtensionsFeature_Desc_Remov"...
0xbaa1e4  stloc.2
0xbaa1e5  br       loc_BAA26A
0xbaa1ea  ldstr    aInternalname_0// "internalName"
0xbaa1ef  stloc.3
0xbaa1f0  ldstr    aWebtemplateext_34// "WebTemplateExtensionsFeature_Desc_AddSi"...
0xbaa1f5  stloc.2
0xbaa1f6  br.s     loc_BAA26A
0xbaa1f8  ldstr    aTitle_1// "title"
0xbaa1fd  stloc.3
0xbaa1fe  ldstr    aWebtemplateext_35// "WebTemplateExtensionsFeature_Desc_SetLi"...
0xbaa203  stloc.2
0xbaa204  br.s     loc_BAA26A
0xbaa206  ldstr    aName// "name"
0xbaa20b  stloc.3
0xbaa20c  ldstr    aWebtemplateext_36// "WebTemplateExtensionsFeature_Desc_AddLi"...
0xbaa211  stloc.2
0xbaa212  br.s     loc_BAA26A
0xbaa214  ldstr    aName// "name"
0xbaa219  stloc.3
0xbaa21a  ldstr    aWebtemplateext_37// "WebTemplateExtensionsFeature_Desc_Remov"...
0xbaa21f  stloc.2
0xbaa220  br.s     loc_BAA26A
0xbaa222  ldstr    aFielddisplayna_3// "fieldDisplayName"
0xbaa227  stloc.3
0xbaa228  ldstr    aWebtemplateext_38// "WebTemplateExtensionsFeature_Desc_SetFi"...
0xbaa22d  stloc.2
0xbaa22e  br.s     loc_BAA26A
0xbaa230  ldstr    aInternalname_0// "internalName"
0xbaa235  stloc.3
0xbaa236  ldstr    aWebtemplateext_39// "WebTemplateExtensionsFeature_Desc_Assoc"...
0xbaa23b  stloc.2
0xbaa23c  br.s     loc_BAA26A
0xbaa23e  ldstr    aTitle_1// "title"
0xbaa243  stloc.3
0xbaa244  ldstr    aWebtemplateext_40// "WebTemplateExtensionsFeature_Desc_Assoc"...
0xbaa249  stloc.2
0xbaa24a  br.s     loc_BAA26A
0xbaa24c  ldstr    aName// "name"
0xbaa251  stloc.3
0xbaa252  ldstr    aWebtemplateext_41// "WebTemplateExtensionsFeature_Desc_AddVi"...
0xbaa257  stloc.2
0xbaa258  br.s     loc_BAA26A
0xbaa25a  ldstr    aName// "name"
0xbaa25f  stloc.3
0xbaa260  ldstr    aWebtemplateext_42// "WebTemplateExtensionsFeature_Desc_Remov"...
0xbaa265  stloc.2
0xbaa266  br.s     loc_BAA26A
0xbaa268  ldnull
0xbaa269  ret
0xbaa26a  ldarg.0
0xbaa26b  ldloc.3
0xbaa26c  ldarg.1
0xbaa26d  ldloca.s 4
0xbaa26f  ldc.i4.0
0xbaa270  call     T0x2B00096C
0xbaa275  pop
0xbaa276  ldarg.0
0xbaa277  ldloc.2
0xbaa278  ldc.i4.1
0xbaa279  newarr   [mscorlib]System.Object
0xbaa27e  stloc.s  8
0xbaa280  ldloc.s  8
0xbaa282  ldc.i4.0
0xbaa283  ldloc.s  4
0xbaa285  dup
0xbaa286  brtrue.s loc_BAA28E
0xbaa288  pop
0xbaa289  ldsfld   string [mscorlib]System.String::Empty
0xbaa28e  stelem.ref
0xbaa28f  ldloc.s  8
0xbaa291  callvirt instance string Microsoft.SharePoint.WebTemplateExtensions.Actions.BaseActionHandler::LocalizedString(string stringKey, object[] args)
0xbaa296  ret
```
