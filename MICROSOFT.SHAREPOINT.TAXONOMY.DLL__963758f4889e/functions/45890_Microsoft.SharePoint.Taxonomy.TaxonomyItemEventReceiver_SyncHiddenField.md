# Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::SyncHiddenField

- ea: `0x45890`
- end: `0x45cce`
- name: `Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::SyncHiddenField`
- size: `1086`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: `installer_update, broker_com_uri`

## callers

- `0x746e0`
- `0x74730`

## callees

- `0x41640`
- `0x41c10`
- `0x44b20`
- `0x44b40`
- `0x456c0`
- `0x45860`
- `0x45890`
- `0x45cd0`
- `0x46100`
- `0x461a0`
- `0x463f0`

## string_xrefs

- `0x45c58`: `Some but not all taxonomy values were found, this can lead to the catch all being incorrect.  Use TaxonomyField.SetFieldValue to update taxonomy values.  Stack trace is {0}`
- `0x45c8a`: `Some but not all taxonomy values were found, this can lead to the catch all being incorrect.  Use TaxonomyField.SetFieldValue to update taxonomy values.`
- `0x45cab`: `Taxonomy Catch All Field did not exist during list item events`

## pseudocode

```c

```

## disassembly

```asm
0x45890  call     bool Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::ShouldRun()
0x45895  brfalse  loc_45CCD
0x4589a  ldc.i4   0x61676335
0x4589f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x458a4  ldc.i4.s 0x64
0x458a6  ldstr    aStartingSyncOf// "Starting sync of hidden fields for taxo"...
0x458ab  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x458b0  ldarg.0
0x458b1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterUrl()
0x458b6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x458bb  brtrue.s loc_458F0
0x458bd  ldarg.0
0x458be  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterUrl()
0x458c3  ldc.i4.1
0x458c4  newarr   [mscorlib]System.Char
0x458c9  stloc.s  0x1A
0x458cb  ldloc.s  0x1A
0x458cd  ldc.i4.0
0x458ce  ldc.i4.s 0x2F
0x458d0  stelem.i2
0x458d1  ldloc.s  0x1A
0x458d3  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x458d8  stloc.0
0x458d9  ldloc.0
0x458da  ldlen
0x458db  conv.i4
0x458dc  ldc.i4.1
0x458dd  ble.s    loc_458F0
0x458df  ldloc.0
0x458e0  ldc.i4.1
0x458e1  ldelem.ref
0x458e2  ldstr    aForms// "Forms"
0x458e7  ldc.i4.5
0x458e8  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x458ed  brtrue.s loc_458F0
0x458ef  ret
0x458f0  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x458f5  stloc.1
0x458f6  ldnull
0x458f7  stloc.2
0x458f8  ldsfld   string [mscorlib]System.String::Empty
0x458fd  stloc.3
0x458fe  ldsfld   string [mscorlib]System.String::Empty
0x45903  stloc.s  4
0x45905  ldc.i4.0
0x45906  stloc.s  5
0x45908  ldc.i4.0
0x45909  stloc.s  6
0x4590b  ldc.i4.1
0x4590c  stloc.s  7
0x4590e  ldarg.0
0x4590f  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_List()
0x45914  stloc.s  8
0x45916  ldloc.s  8
0x45918  brtrue.s loc_4591B
0x4591a  ret
0x4591b  ldloc.s  8
0x4591d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_Fields()
0x45922  stloc.s  9
0x45924  ldloc.s  9
0x45926  callvirt instance class [mscorlib]System.Collections.IEnumerator [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseCollection::GetEnumerator()
0x4592b  stloc.s  0x1B
0x4592d  br       loc_45B99
0x45932  ldloc.s  0x1B
0x45934  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x45939  castclass [Microsoft.SharePoint]Microsoft.SharePoint.SPField
0x4593e  stloc.s  0xA
0x45940  ldloc.s  0xA
0x45942  isinst   Microsoft.SharePoint.Taxonomy.TaxonomyField
0x45947  stloc.s  0xB
0x45949  ldloc.s  0xB
0x4594b  brfalse  loc_45B99
0x45950  ldnull
0x45951  stloc.s  0xC
0x45953  ldloc.s  9
0x45955  ldloc.s  0xB
0x45957  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyField::get_TextField()
0x4595c  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPField [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldCollection::get_Item(valuetype [mscorlib]System.Guid)
0x45961  stloc.s  0xC
0x45963  leave.s  loc_4597E
0x45965  pop
0x45966  ldc.i4   0x32636B68
0x4596b  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x45970  ldc.i4.s 0x64
0x45972  ldstr    aHiddenTextFiel// "Hidden Text field did not exist when up"...
0x45977  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x4597c  leave.s  loc_4597E
0x4597e  ldloc.s  0xC
0x45980  brfalse  loc_45B99
0x45985  ldloc.s  0xB
0x45987  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_InternalName()
0x4598c  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::GetUnescapedInternalName(string internalName)
0x45991  stloc.s  0xD
0x45993  ldloc.s  0xC
0x45995  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_InternalName()
0x4599a  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::GetUnescapedInternalName(string internalName)
0x4599f  stloc.s  0xE
0x459a1  ldsfld   string [mscorlib]System.String::Empty
0x459a6  stloc.s  0xF
0x459a8  ldsfld   string [mscorlib]System.String::Empty
0x459ad  stloc.s  0x10
0x459af  ldloc.s  0xB
0x459b1  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldLookup::get_AllowMultipleValues()
0x459b6  brfalse.s loc_45A25
0x459b8  ldc.i4.0
0x459b9  stloc.s  0x11
0x459bb  ldloc.s  0xB
0x459bd  ldloc.s  0xC
0x459bf  ldarg.0
0x459c0  ldloc.1
0x459c1  ldloc.s  0xD
0x459c3  ldloc.s  0xE
0x459c5  ldloca.s 0xF
0x459c7  ldloca.s 0x10
0x459c9  ldloca.s 0x11
0x459cb  call     bool Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::UpdateMultipleValueTaxColumn(class Microsoft.SharePoint.Taxonomy.TaxonomyField taxField, class [Microsoft.SharePoint]Microsoft.SharePoint.SPField hiddenField, class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties props, class [mscorlib]System.Collections.Hashtable catchAllField, string unescapedTaxonomyInternalName, string unescapedHiddenTextInternalName, [out] string& taxonomyFieldAfterPropertyIndex, [out] string& hiddenFieldAfterPropertyIndex, [out] bool& keywordsServerUpdate)
0x459d0  stloc.s  0x12
0x459d2  ldloc.s  0x12
0x459d4  brtrue.s loc_459DA
0x459d6  ldloc.s  6
0x459d8  br.s     loc_459DB
0x459da  ldc.i4.1
0x459db  stloc.s  6
0x459dd  ldloc.s  7
0x459df  brfalse.s loc_459E5
0x459e1  ldloc.s  0x12
0x459e3  br.s     loc_459E6
0x459e5  ldc.i4.0
0x459e6  stloc.s  7
0x459e8  ldloc.s  0xB
0x459ea  callvirt instance bool Microsoft.SharePoint.Taxonomy.TaxonomyField::get_IsKeyword()
0x459ef  brfalse.s loc_45A51
0x459f1  ldloc.s  0x11
0x459f3  stloc.s  5
0x459f5  ldloc.s  0xB
0x459f7  stloc.2
0x459f8  ldloc.s  0xF
0x459fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x459ff  brtrue.s loc_45A05
0x45a01  ldloc.s  0xF
0x45a03  br.s     loc_45A0C
0x45a05  ldloc.s  0xB
0x45a07  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_InternalName()
0x45a0c  stloc.s  4
0x45a0e  ldloc.s  0x10
0x45a10  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45a15  brtrue.s loc_45A1B
0x45a17  ldloc.s  0x10
0x45a19  br.s     loc_45A22
0x45a1b  ldloc.s  0xC
0x45a1d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_InternalName()
0x45a22  stloc.3
0x45a23  br.s     loc_45A51
0x45a25  ldloc.s  0xB
0x45a27  ldloc.s  0xC
0x45a29  ldarg.0
0x45a2a  ldloc.1
0x45a2b  ldloc.s  0xD
0x45a2d  ldloc.s  0xE
0x45a2f  ldloca.s 0xF
0x45a31  ldloca.s 0x10
0x45a33  ldarg.1
0x45a34  call     bool Microsoft.SharePoint.Taxonomy.TaxonomyItemEventReceiver::UpdateSingleValueTaxColumn(class Microsoft.SharePoint.Taxonomy.TaxonomyField taxField, class [Microsoft.SharePoint]Microsoft.SharePoint.SPField hiddenField, class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties props, class [mscorlib]System.Collections.Hashtable catchAllFieldValues, string unescapedTaxonomyInternalName, string unescapedHiddenTextInternalName, [out] string& taxonomyFieldAfterPropertyIndex, [out] string& hiddenFieldAfterPropertyIndex, bool adding)
0x45a39  stloc.s  0x13
0x45a3b  ldloc.s  0x13
0x45a3d  brtrue.s loc_45A43
0x45a3f  ldloc.s  6
0x45a41  br.s     loc_45A44
0x45a43  ldc.i4.1
0x45a44  stloc.s  6
0x45a46  ldloc.s  7
0x45a48  brfalse.s loc_45A4E
0x45a4a  ldloc.s  0x13
0x45a4c  br.s     loc_45A4F
0x45a4e  ldc.i4.0
0x45a4f  stloc.s  7
0x45a51  ldarg.1
0x45a52  brfalse  loc_45B99
0x45a57  ldloc.s  0xB
0x45a59  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultValueTyped()
0x45a5e  brfalse  loc_45B99
0x45a63  ldloc.s  0xF
0x45a65  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45a6a  brfalse.s loc_45A75
0x45a6c  ldloc.s  0x10
0x45a6e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45a73  brtrue.s loc_45A99
0x45a75  ldarg.0
0x45a76  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45a7b  ldloc.s  0xF
0x45a7d  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection::get_Item(string)
0x45a82  brtrue   loc_45B99
0x45a87  ldarg.0
0x45a88  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45a8d  ldloc.s  0x10
0x45a8f  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection::get_Item(string)
0x45a94  brtrue   loc_45B99
0x45a99  ldloc.s  0x10
0x45a9b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45aa0  brfalse.s loc_45AC8
0x45aa2  ldarg.0
0x45aa3  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45aa8  ldarg.0
0x45aa9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_FileSystemObjectTypePropertyName()
0x45aae  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection::get_Item(string)
0x45ab3  isinst   [mscorlib]System.String
0x45ab8  ldstr    aFolder// "Folder"
0x45abd  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x45ac2  brfalse.s loc_45AC8
0x45ac4  ldloc.s  0xE
0x45ac6  stloc.s  0x10
0x45ac8  ldloc.s  0xB
0x45aca  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPFieldLookup::get_AllowMultipleValues()
0x45acf  brfalse.s loc_45B4E
0x45ad1  ldloc.s  0xB
0x45ad3  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultValueTyped()
0x45ad8  isinst   Microsoft.SharePoint.Taxonomy.TaxonomyFieldValueCollection
0x45add  stloc.s  0x14
0x45adf  ldloc.s  0x14
0x45ae1  brfalse  loc_45B99
0x45ae6  ldloc.s  0x14
0x45ae8  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue>::GetEnumerator()
0x45aed  stloc.s  0x1C
0x45aef  br.s     loc_45B13
0x45af1  ldloca.s 0x1C
0x45af3  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue>::get_Current()
0x45af8  stloc.s  0x15
0x45afa  ldloc.1
0x45afb  ldloc.s  0x15
0x45afd  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue::get_WssId()
0x45b02  box      [mscorlib]System.Int32
0x45b07  ldloc.s  0x15
0x45b09  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue::get_Label()
0x45b0e  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x45b13  ldloca.s 0x1C
0x45b15  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue>::MoveNext()
0x45b1a  brtrue.s loc_45AF1
0x45b1c  leave.s  loc_45B2C
0x45b1e  ldloca.s 0x1C
0x45b20  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue>
0x45b26  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45b2b  endfinally
0x45b2c  ldloc.s  0x10
0x45b2e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45b33  brtrue.s loc_45B49
0x45b35  ldarg.0
0x45b36  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45b3b  ldloc.s  0x10
0x45b3d  ldloc.s  0x14
0x45b3f  callvirt instance string [mscorlib]System.Object::ToString()
0x45b44  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection::set_Item(string, object)
0x45b49  ldc.i4.1
0x45b4a  stloc.s  6
0x45b4c  br.s     loc_45B99
0x45b4e  ldloc.s  0xB
0x45b50  callvirt instance object [Microsoft.SharePoint]Microsoft.SharePoint.SPField::get_DefaultValueTyped()
0x45b55  isinst   Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue
0x45b5a  stloc.s  0x16
0x45b5c  ldloc.s  0x16
0x45b5e  brfalse.s loc_45B99
0x45b60  ldloc.1
0x45b61  ldloc.s  0x16
0x45b63  callvirt instance int32 Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue::get_WssId()
0x45b68  box      [mscorlib]System.Int32
0x45b6d  ldloc.s  0x16
0x45b6f  callvirt instance string Microsoft.SharePoint.Taxonomy.TaxonomyFieldValue::get_Label()
0x45b74  callvirt instance void [mscorlib]System.Collections.Hashtable::set_Item(object, object)
0x45b79  ldloc.s  0x10
0x45b7b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x45b80  brtrue.s loc_45B96
0x45b82  ldarg.0
0x45b83  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45b88  ldloc.s  0x10
0x45b8a  ldloc.s  0x16
0x45b8c  callvirt instance string [mscorlib]System.Object::ToString()
0x45b91  callvirt instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection::set_Item(string, object)
0x45b96  ldc.i4.1
0x45b97  stloc.s  6
0x45b99  ldloc.s  0x1B
0x45b9b  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x45ba0  brtrue   loc_45932
0x45ba5  leave.s  loc_45BBC
0x45ba7  ldloc.s  0x1B
0x45ba9  isinst   [mscorlib]System.IDisposable
0x45bae  stloc.s  0x1D
0x45bb0  ldloc.s  0x1D
0x45bb2  brfalse.s loc_45BBB
0x45bb4  ldloc.s  0x1D
0x45bb6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45bbb  endfinally
0x45bbc  ldloc.2
0x45bbd  brfalse.s loc_45C15
0x45bbf  ldarg.0
0x45bc0  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPList [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_List()
0x45bc5  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.SPBaseType [Microsoft.SharePoint]Microsoft.SharePoint.SPList::get_BaseType()
0x45bca  ldc.i4.1
0x45bcb  bne.un.s loc_45C15
0x45bcd  ldarg.0
0x45bce  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventDataCollection [Microsoft.SharePoint]Microsoft.SharePoint.SPItemEventProperties::get_AfterProperties()
0x45bd3  ldarg.0
  ... truncated ...
```
