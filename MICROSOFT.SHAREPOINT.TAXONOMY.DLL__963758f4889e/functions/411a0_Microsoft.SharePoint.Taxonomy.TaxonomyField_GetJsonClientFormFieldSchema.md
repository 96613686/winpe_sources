# Microsoft.SharePoint.Taxonomy.TaxonomyField::GetJsonClientFormFieldSchema

- ea: `0x411a0`
- end: `0x41390`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyField::GetJsonClientFormFieldSchema`
- size: `496`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x411a0`
- `0x41390`
- `0x41490`
- `0x41570`
- `0x41600`
- `0x41670`
- `0x41680`
- `0x417c0`
- `0x41be0`
- `0x41c10`
- `0x6f910`

## string_xrefs

- `0x412c5`: `IsUseCommaAsDelimiter`
- `0x41304`: `WebServiceUrl`

## pseudocode

```c

```

## disassembly

```asm
0x411a0  ldarg.0
0x411a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x411a6  brtrue   loc_41389
0x411ab  ldarg.0
0x411ac  ldarg.0
0x411ad  ldarg.1
0x411ae  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldLookup::GetJsonClientFormFieldSchema(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPControlMode)
0x411b3  stfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x411b8  ldarg.0
0x411b9  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x411be  ldstr    aSspid_0// "SspId"
0x411c3  ldarg.0
0x411c4  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::get_SspId()
0x411c9  box      [mscorlib]System.Guid
0x411ce  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x411d3  ldarg.0
0x411d4  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x411d9  ldstr    aTermsetid// "TermSetId"
0x411de  ldarg.0
0x411df  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::get_TermSetId()
0x411e4  box      [mscorlib]System.Guid
0x411e9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x411ee  ldarg.0
0x411ef  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x411f4  ldstr    aAnchorid// "AnchorId"
0x411f9  ldarg.0
0x411fa  call     instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::get_AnchorId()
0x411ff  box      [mscorlib]System.Guid
0x41204  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41209  ldarg.0
0x4120a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x4120f  ldstr    aAllowfillin// "AllowFillIn"
0x41214  ldarg.0
0x41215  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Open()
0x4121a  box      [mscorlib]System.Boolean
0x4121f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41224  ldarg.0
0x41225  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x4122a  ldstr    aWidthcss// "WidthCSS"
0x4122f  ldstr    aMsLong// "ms-long"
0x41234  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41239  ldarg.0
0x4123a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x4123f  ldstr    aLcid_1// "Lcid"
0x41244  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x41249  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x4124e  box      [mscorlib]System.Int32
0x41253  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41258  ldarg.0
0x41259  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x4125e  ldstr    aIsspantermsets// "IsSpanTermSets"
0x41263  ldarg.0
0x41264  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsKeyword()
0x41269  box      [mscorlib]System.Boolean
0x4126e  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41273  ldarg.0
0x41274  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x41279  ldstr    aIsspantermstor// "IsSpanTermStores"
0x4127e  ldarg.0
0x4127f  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsKeyword()
0x41284  box      [mscorlib]System.Boolean
0x41289  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4128e  ldarg.0
0x4128f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x41294  ldstr    aIsaddterms// "IsAddTerms"
0x41299  ldarg.0
0x4129a  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Open()
0x4129f  brfalse.s loc_412B4
0x412a1  ldarg.0
0x412a2  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsKeyword()
0x412a7  brtrue.s loc_412B1
0x412a9  ldarg.0
0x412aa  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_CreateValuesInEditForm()
0x412af  br.s     loc_412B5
0x412b1  ldc.i4.1
0x412b2  br.s     loc_412B5
0x412b4  ldc.i4.0
0x412b5  box      [mscorlib]System.Boolean
0x412ba  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x412bf  ldarg.0
0x412c0  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x412c5  ldstr    aIsusecommaasde// "IsUseCommaAsDelimiter"
0x412ca  ldc.i4.1
0x412cb  box      [mscorlib]System.Boolean
0x412d0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x412d5  ldarg.0
0x412d6  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x412db  ldstr    aDisable// "Disable"
0x412e0  ldarg.0
0x412e1  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsTermSetValid()
0x412e6  brfalse.s loc_412F3
0x412e8  ldarg.0
0x412e9  call     instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsAnchorValid()
0x412ee  ldc.i4.0
0x412ef  ceq
0x412f1  br.s     loc_412F4
0x412f3  ldc.i4.1
0x412f4  box      [mscorlib]System.Boolean
0x412f9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x412fe  ldarg.0
0x412ff  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x41304  ldstr    aWebserviceurl// "WebServiceUrl"
0x41309  ldarg.0
0x4130a  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Web()
0x4130f  call     class [System]System.Uri Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetWebServiceUrl(class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb web)
0x41314  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x41319  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x4131e  ldarg.0
0x4131f  ldstr    aTextfield// "TextField"
0x41324  call     instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::GetCustomProperty(string)
0x41329  isinst   [mscorlib]System.String
0x4132e  stloc.0
0x4132f  ldloc.0
0x41330  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x41335  brtrue.s loc_41389
0x41337  ldloca.s 1
0x41339  initobj  [mscorlib]System.Guid
0x4133f  ldloc.0
0x41340  ldloca.s 1
0x41342  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x41347  brfalse.s loc_41389
0x41349  ldarg.0
0x4134a  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_ParentList()
0x4134f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Fields()
0x41354  ldloc.1
0x41355  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPField [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection::get_Item(valuetype [mscorlib]System.Guid)
0x4135a  stloc.2
0x4135b  ldloc.2
0x4135c  brfalse.s loc_41374
0x4135e  ldarg.0
0x4135f  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x41364  ldstr    aHiddenlistinte// "HiddenListInternalName"
0x41369  ldloc.2
0x4136a  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_InternalName()
0x4136f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::set_Item(var<u1>, !!T0)
0x41374  leave.s  loc_41389
0x41376  stloc.3
0x41377  ldc.i4   0x120A789
0x4137c  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x41381  ldloc.3
0x41382  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendExceptionTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, class [mscorlib]System.Exception)
0x41387  leave.s  loc_41389
0x41389  ldarg.0
0x4138a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> Microsoft.SharePoint.Taxonomy.TaxonomyField::fieldSchema
0x4138f  ret
```
