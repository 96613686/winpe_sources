# Microsoft.SharePoint.Taxonomy.Term::DeleteCustomProperty_0

- ea: `0x50930`
- end: `0x509c5`
- name: `Microsoft.SharePoint.Taxonomy.Term::DeleteCustomProperty_0`
- size: `149`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x4e190`
- `0x4e1d0`
- `0x4e1e0`
- `0x4e1f0`

## callees

- `0x30a90`
- `0x32680`
- `0x48a60`
- `0x4d600`
- `0x4d620`
- `0x4dab0`
- `0x4f680`
- `0x4f6a0`
- `0x50570`
- `0x50680`
- `0x50930`

## string_xrefs

- `0x5093c`: `Begin: Term.DeleteCustomProperty(string, bool)`
- `0x509ba`: `End: Term.DeleteCustomProperty(string, bool)`

## pseudocode

```c

```

## disassembly

```asm
0x50930  ldc.i4   0x455CB
0x50935  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x5093a  ldc.i4.s 0x64
0x5093c  ldstr    aBeginTermDelet_0// "Begin: Term.DeleteCustomProperty(string"...
0x50941  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x50946  ldarg.0
0x50947  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::EnsureValidItem()
0x5094c  ldarg.0
0x5094d  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::EnsureNotOrphanedTermsTermSet()
0x50952  ldarg.2
0x50953  brtrue.s loc_5095B
0x50955  ldarg.0
0x50956  call     instance void Microsoft.SharePoint.Taxonomy.Term::EnsureNotPinned()
0x5095b  ldarg.0
0x5095c  ldc.i4.1
0x5095d  conv.i8
0x5095e  ldarg.2
0x5095f  ldc.i4.0
0x50960  ceq
0x50962  call     instance void Microsoft.SharePoint.Taxonomy.Term::BeginUpdate(valuetype Microsoft.SharePoint.Taxonomy.TaxonomyRights permissions, bool checkPermissionsOnSourceTerm)
0x50967  ldarg.2
0x50968  brfalse.s loc_50992
0x5096a  ldarg.1
0x5096b  brtrue.s loc_5097F
0x5096d  ldarg.0
0x5096e  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership Microsoft.SharePoint.Taxonomy.Term::get_Membership()
0x50973  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership::get_LocalCustomProperties()
0x50978  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Clear()
0x5097d  br.s     loc_509AE
0x5097f  ldarg.0
0x50980  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership Microsoft.SharePoint.Taxonomy.Term::get_Membership()
0x50985  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership::get_LocalCustomProperties()
0x5098a  ldarg.1
0x5098b  call     void Microsoft.SharePoint.Taxonomy.TermSetItem::DeleteCustomPropertyWithoutSecurityCheck(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> customProperties, string name)
0x50990  br.s     loc_509AE
0x50992  ldarg.1
0x50993  brtrue.s loc_509A7
0x50995  ldarg.0
0x50996  call     instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x5099b  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.SharePoint.Taxonomy.Internal.SharedTermSetItem::get_CustomProperties()
0x509a0  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Clear()
0x509a5  br.s     loc_509AE
0x509a7  ldarg.0
0x509a8  ldarg.1
0x509a9  call     instance void Microsoft.SharePoint.Taxonomy.TermSetItem::DeleteCustomPropertyWithoutSecurityCheck(string name)
0x509ae  ldc.i4   0x455CC
0x509b3  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x509b8  ldc.i4.s 0x64
0x509ba  ldstr    aEndTermDeletec// "End: Term.DeleteCustomProperty(string, "...
0x509bf  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x509c4  ret
```
