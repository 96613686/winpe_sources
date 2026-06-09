# Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::SaveNewProperties

- ea: `0x2760`
- end: `0x29fc`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::SaveNewProperties`
- size: `668`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x2210`

## callees

- `0x2760`
- `0x2be0`
- `0x14930`
- `0x41420`
- `0x41530`
- `0x41a80`
- `0x41bd0`
- `0x41be0`
- `0x48780`
- `0x497b0`
- `0x4ba10`
- `0x4cba0`
- `0x4d530`
- `0x52e10`
- `0x53f80`
- `0x55050`
- `0x6de50`

## string_xrefs

- `0x299f`: `UserCreated`
- `0x29dd`: `IsPathRendered`

## pseudocode

```c

```

## disassembly

```asm
0x2760  ldarg.1
0x2761  ldstr    aSspid_0// "SspId"
0x2766  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x276b  stloc.s  4
0x276d  ldloca.s 4
0x276f  constrained. [mscorlib]System.Guid
0x2775  callvirt instance string [mscorlib]System.Object::ToString()
0x277a  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x277f  ldarg.0
0x2780  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSet
0x2785  callvirt instance bool [System.Web]System.Web.UI.WebControls.CheckBox::get_Checked()
0x278a  brfalse  loc_2821
0x278f  ldarg.1
0x2790  ldstr    aSspid_0// "SspId"
0x2795  ldarg.0
0x2796  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createSspId
0x279b  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x27a0  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x27a5  ldarg.1
0x27a6  ldarg.0
0x27a7  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createSspId
0x27ac  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x27b1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27b6  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_SspId(valuetype [mscorlib]System.Guid value)
0x27bb  ldarg.1
0x27bc  ldstr    aTermsetid// "TermSetId"
0x27c1  ldarg.0
0x27c2  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x27c7  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x27cc  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x27d1  ldarg.1
0x27d2  ldarg.0
0x27d3  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x27d8  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x27dd  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x27e2  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_TermSetId(valuetype [mscorlib]System.Guid value)
0x27e7  ldarg.1
0x27e8  ldstr    aAnchorid// "AnchorId"
0x27ed  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x27f2  stloc.s  5
0x27f4  ldloca.s 5
0x27f6  constrained. [mscorlib]System.Guid
0x27fc  callvirt instance string [mscorlib]System.Object::ToString()
0x2801  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x2806  ldarg.1
0x2807  ldstr    aSspid_0// "SspId"
0x280c  ldarg.0
0x280d  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createSspId
0x2812  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2817  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x281c  br       loc_297C
0x2821  ldarg.1
0x2822  ldstr    aSspid_0// "SspId"
0x2827  ldarg.0
0x2828  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseSspId
0x282d  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2832  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x2837  ldarg.1
0x2838  ldarg.0
0x2839  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseSspId
0x283e  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x2843  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2848  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_SspId(valuetype [mscorlib]System.Guid value)
0x284d  ldarg.1
0x284e  ldstr    aTermsetid// "TermSetId"
0x2853  ldarg.0
0x2854  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSetId
0x2859  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x285e  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x2863  ldarg.1
0x2864  ldarg.0
0x2865  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSetId
0x286a  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x286f  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2874  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::set_TermSetId(valuetype [mscorlib]System.Guid value)
0x2879  ldarg.1
0x287a  ldstr    aAnchorid// "AnchorId"
0x287f  ldarg.0
0x2880  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseAnchorId
0x2885  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x288a  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x288f  ldarg.0
0x2890  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x2895  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x289a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x289f  stloc.s  6
0x28a1  ldloca.s 6
0x28a3  constrained. [mscorlib]System.Guid
0x28a9  callvirt instance string [mscorlib]System.Object::ToString()
0x28ae  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x28b3  brfalse  loc_297C
0x28b8  ldarg.0
0x28b9  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x28be  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x28c3  ldarg.0
0x28c4  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::reuseTermSetId
0x28c9  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x28ce  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x28d3  brfalse  loc_297C
0x28d8  ldarg.1
0x28d9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Web()
0x28de  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_Site()
0x28e3  ldarg.1
0x28e4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Web()
0x28e9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_ID()
0x28ee  ldarg.1
0x28ef  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.TaxonomyField::get_List()
0x28f4  brfalse.s loc_2903
0x28f6  ldarg.1
0x28f7  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList Microsoft.SharePoint.Taxonomy.TaxonomyField::get_List()
0x28fc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_ID()
0x2901  br.s     loc_2908
0x2903  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x2908  ldc.i4.1
0x2909  call     class Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper Microsoft.SharePoint.Taxonomy.WebServices.TaxonomyInternalService::GetTaxonomySession(class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite site, valuetype [mscorlib]System.Guid webId, valuetype [mscorlib]System.Guid listId, bool resetCache)
0x290e  stloc.0
0x290f  ldloc.0
0x2910  callvirt instance class Microsoft.SharePoint.Taxonomy.TaxonomySession Microsoft.SharePoint.Taxonomy.DisposableTaxonomySessionWrapper::get_Session()
0x2915  stloc.1
0x2916  ldloc.1
0x2917  callvirt instance class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.TaxonomySession::get_DefaultSiteCollectionTermStore()
0x291c  stloc.2
0x291d  ldloc.2
0x291e  brfalse.s loc_2970
0x2920  ldloc.2
0x2921  ldarg.0
0x2922  ldfld    class [System.Web]System.Web.UI.WebControls.TextBox Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSetId
0x2927  callvirt instance string [System.Web]System.Web.UI.WebControls.TextBox::get_Text()
0x292c  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x2931  callvirt instance class Microsoft.SharePoint.Taxonomy.TermSet Microsoft.SharePoint.Taxonomy.TermStore::GetTermSet(valuetype [mscorlib]System.Guid termSetId)
0x2936  stloc.3
0x2937  ldloc.3
0x2938  brfalse.s loc_2970
0x293a  ldloc.3
0x293b  callvirt instance string Microsoft.SharePoint.Taxonomy.TermSetItem::get_Owner()
0x2940  ldarg.1
0x2941  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb Microsoft.SharePoint.Taxonomy.TaxonomyField::get_Web()
0x2946  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPUser [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb::get_CurrentUser()
0x294b  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPPrincipal::get_Name()
0x2950  call     bool [mscorlib]System.String::op_Equality(string, string)
0x2955  brfalse.s loc_2970
0x2957  ldloc.3
0x2958  callvirt instance class Microsoft.SharePoint.Taxonomy.Group Microsoft.SharePoint.Taxonomy.TermSet::get_Group()
0x295d  callvirt instance bool Microsoft.SharePoint.Taxonomy.Group::get_IsSystemGroup()
0x2962  brtrue.s loc_2970
0x2964  ldloc.3
0x2965  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x296a  ldloc.2
0x296b  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::CommitAll()
0x2970  leave.s  loc_297C
0x2972  ldloc.0
0x2973  brfalse.s loc_297B
0x2975  ldloc.0
0x2976  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x297b  endfinally
0x297c  ldarg.0
0x297d  ldfld    class Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::defaultValueControl
0x2982  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyWebTaggingControl::get_Text()
0x2987  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x298c  brfalse.s loc_2997
0x298e  ldarg.1
0x298f  ldnull
0x2990  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPField::set_DefaultValue(string)
0x2995  br.s     loc_299E
0x2997  ldarg.0
0x2998  ldarg.1
0x2999  call     instance void Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::SetDefaultValue(class Microsoft.SharePoint.Taxonomy.TaxonomyField field)
0x299e  ldarg.1
0x299f  ldstr    aUsercreated// "UserCreated"
0x29a4  ldarg.0
0x29a5  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::createTermSet
0x29aa  callvirt instance bool [System.Web]System.Web.UI.WebControls.CheckBox::get_Checked()
0x29af  stloc.s  7
0x29b1  ldloca.s 7
0x29b3  call     instance string [mscorlib]System.Boolean::ToString()
0x29b8  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x29bd  ldarg.1
0x29be  ldstr    aOpen// "Open"
0x29c3  ldarg.0
0x29c4  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::fillInTrue
0x29c9  callvirt instance bool [System.Web]System.Web.UI.WebControls.CheckBox::get_Checked()
0x29ce  stloc.s  8
0x29d0  ldloca.s 8
0x29d2  call     instance string [mscorlib]System.Boolean::ToString()
0x29d7  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x29dc  ldarg.1
0x29dd  ldstr    aIspathrendered// "IsPathRendered"
0x29e2  ldarg.0
0x29e3  ldfld    class [System.Web]System.Web.UI.WebControls.RadioButton Microsoft.SharePoint.Taxonomy.TaxonomyFieldEditor::displayPath
0x29e8  callvirt instance bool [System.Web]System.Web.UI.WebControls.CheckBox::get_Checked()
0x29ed  stloc.s  9
0x29ef  ldloca.s 9
0x29f1  call     instance string [mscorlib]System.Boolean::ToString()
0x29f6  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyField::SaveNewFieldProperty(string name, string value)
0x29fb  ret
```
