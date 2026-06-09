# Microsoft.SharePoint.Taxonomy.ImportManager::AddTermToImportTermSet

- ea: `0x4a7c0`
- end: `0x4aadf`
- name: `Microsoft.SharePoint.Taxonomy.ImportManager::AddTermToImportTermSet`
- size: `799`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x4a280`

## callees

- `0x25740`
- `0x25790`
- `0x32070`
- `0x48780`
- `0x48790`
- `0x48810`
- `0x4a7c0`
- `0x4d190`
- `0x4d520`
- `0x4d550`
- `0x4ebb0`
- `0x50680`

## string_xrefs

- `0x4a847`: `Error encountered during import.  A name on line {0} is null.`
- `0x4a879`: `Error encountered during import.  The name {0} is not valid on line {1}.`
- `0x4a9b1`: `Error encountered during import.  The available for tagging entry on line {0} is not valid.`
- `0x4a9e0`: `Error encountered during import.  The available for tagging entry on line {0} is not valid.`
- `0x4aa5a`: `Error encountered during import.  The description {0} on line {1} is not valid.`
- `0x4aaa6`: `Error encountered during import when attempting to delete invalid term with id '{0}' on line {1}.  The error was {2}.  `

## pseudocode

```c

```

## disassembly

```asm
0x4a7c0  ldnull
0x4a7c1  stloc.0
0x4a7c2  ldnull
0x4a7c3  stloc.1
0x4a7c4  ldc.i4.0
0x4a7c5  stloc.2
0x4a7c6  ldc.i4.1
0x4a7c7  stloc.3
0x4a7c8  ldc.i4.0
0x4a7c9  stloc.s  4
0x4a7cb  ldc.i4.0
0x4a7cc  stloc.s  5
0x4a7ce  ldarg.0
0x4a7cf  brfalse.s loc_4A7DA
0x4a7d1  ldarg.0
0x4a7d2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x4a7d7  ldc.i4.5
0x4a7d8  bgt.s    loc_4A7DC
0x4a7da  ldc.i4.0
0x4a7db  ret
0x4a7dc  ldc.i4.0
0x4a7dd  stloc.2
0x4a7de  br       loc_4A939
0x4a7e3  ldarg.0
0x4a7e4  ldc.i4.5
0x4a7e5  ldloc.2
0x4a7e6  add.ovf
0x4a7e7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4a7ec  stloc.s  6
0x4a7ee  ldloc.s  6
0x4a7f0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a7f5  brfalse.s loc_4A806
0x4a7f7  ldloc.s  5
0x4a7f9  brfalse  loc_4A94A
0x4a7fe  ldc.i4.1
0x4a7ff  stloc.s  4
0x4a801  br       loc_4A94A
0x4a806  ldloc.s  6
0x4a808  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4a80d  ldc.i4   0xFF
0x4a812  ble.s    loc_4A823
0x4a814  ldloc.s  6
0x4a816  ldc.i4.0
0x4a817  ldc.i4   0xFF
0x4a81c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4a821  stloc.s  6
0x4a823  ldloc.s  6
0x4a825  call     string Microsoft.SharePoint.Taxonomy.TaxonomyItem::NormalizeName(string name)
0x4a82a  stloc.s  6
0x4a82c  ldloc.s  6
0x4a82e  ldstr    aName_1// "name"
0x4a833  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::ValidateName(string name, string parameterName)
0x4a838  leave.s  loc_4A8A4
0x4a83a  pop
0x4a83b  ldc.i4   0x66633373
0x4a840  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a845  ldc.i4.s 0xA
0x4a847  ldstr    aErrorEncounter_3// "Error encountered during import.  A nam"...
0x4a84c  ldc.i4.1
0x4a84d  newarr   [mscorlib]System.Object
0x4a852  stloc.s  0xB
0x4a854  ldloc.s  0xB
0x4a856  ldc.i4.0
0x4a857  ldarg.3
0x4a858  box      [mscorlib]System.Int32
0x4a85d  stelem.ref
0x4a85e  ldloc.s  0xB
0x4a860  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4a865  ldc.i4.0
0x4a866  stloc.3
0x4a867  leave    loc_4A94A
0x4a86c  pop
0x4a86d  ldc.i4   0x66633374
0x4a872  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a877  ldc.i4.s 0xA
0x4a879  ldstr    aErrorEncounter_4// "Error encountered during import.  The n"...
0x4a87e  ldc.i4.2
0x4a87f  newarr   [mscorlib]System.Object
0x4a884  stloc.s  0xC
0x4a886  ldloc.s  0xC
0x4a888  ldc.i4.0
0x4a889  ldloc.s  6
0x4a88b  stelem.ref
0x4a88c  ldloc.s  0xC
0x4a88e  ldc.i4.1
0x4a88f  ldarg.3
0x4a890  box      [mscorlib]System.Int32
0x4a895  stelem.ref
0x4a896  ldloc.s  0xC
0x4a898  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4a89d  ldc.i4.0
0x4a89e  stloc.3
0x4a89f  leave    loc_4A94A
0x4a8a4  ldloc.1
0x4a8a5  brtrue.s loc_4A8AB
0x4a8a7  ldarg.1
0x4a8a8  stloc.0
0x4a8a9  br.s     loc_4A8AD
0x4a8ab  ldloc.1
0x4a8ac  stloc.0
0x4a8ad  ldnull
0x4a8ae  stloc.1
0x4a8af  ldloc.0
0x4a8b0  callvirt instance class Microsoft.SharePoint.Taxonomy.TermCollection Microsoft.SharePoint.Taxonomy.TermSetItem::get_Terms()
0x4a8b5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Taxonomy.Generic.GenericCollection`1<class Microsoft.SharePoint.Taxonomy.Term>::GetEnumerator()
0x4a8ba  stloc.s  0xD
0x4a8bc  br.s     loc_4A8FB
0x4a8be  ldloc.s  0xD
0x4a8c0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.Taxonomy.Term>::get_Current()
0x4a8c5  stloc.s  7
0x4a8c7  ldloc.s  7
0x4a8c9  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4a8ce  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_DefaultLabels()
0x4a8d3  ldarg.2
0x4a8d4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::ContainsKey(var<u1>)
0x4a8d9  brfalse.s loc_4A8FB
0x4a8db  ldloc.s  7
0x4a8dd  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedTerm Microsoft.SharePoint.Taxonomy.Term::get_SharedTerm()
0x4a8e2  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_DefaultLabels()
0x4a8e7  ldarg.2
0x4a8e8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<int32, string>::get_Item(void)
0x4a8ed  ldloc.s  6
0x4a8ef  call     bool [mscorlib]System.String::op_Equality(string, string)
0x4a8f4  brfalse.s loc_4A8FB
0x4a8f6  ldloc.s  7
0x4a8f8  stloc.1
0x4a8f9  br.s     loc_4A904
0x4a8fb  ldloc.s  0xD
0x4a8fd  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4a902  brtrue.s loc_4A8BE
0x4a904  leave.s  loc_4A912
0x4a906  ldloc.s  0xD
0x4a908  brfalse.s loc_4A911
0x4a90a  ldloc.s  0xD
0x4a90c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4a911  endfinally
0x4a912  ldloc.1
0x4a913  brtrue.s loc_4A935
0x4a915  ldloc.0
0x4a916  brfalse.s loc_4A935
0x4a918  ldloc.0
0x4a919  ldloc.s  6
0x4a91b  ldarg.2
0x4a91c  callvirt instance class Microsoft.SharePoint.Taxonomy.Term Microsoft.SharePoint.Taxonomy.TermSetItem::CreateTerm(string name, int32 lcid)
0x4a921  stloc.1
0x4a922  ldc.i4.1
0x4a923  stloc.s  5
0x4a925  ldloc.2
0x4a926  ldarg.0
0x4a927  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x4a92c  ldc.i4.5
0x4a92d  sub.ovf
0x4a92e  ldc.i4.1
0x4a92f  sub.ovf
0x4a930  bne.un.s loc_4A935
0x4a932  ldc.i4.1
0x4a933  stloc.s  4
0x4a935  ldloc.2
0x4a936  ldc.i4.1
0x4a937  add.ovf
0x4a938  stloc.2
0x4a939  ldloc.2
0x4a93a  ldarg.0
0x4a93b  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x4a940  ldc.i4.5
0x4a941  sub.ovf
0x4a942  bge.s    loc_4A94A
0x4a944  ldloc.3
0x4a945  brtrue   loc_4A7E3
0x4a94a  ldloc.3
0x4a94b  brfalse  loc_4AADC
0x4a950  ldloc.1
0x4a951  brfalse  loc_4AADC
0x4a956  ldarg.0
0x4a957  ldc.i4.3
0x4a958  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4a95d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4a962  brtrue.s loc_4A978
0x4a964  ldloc.1
0x4a965  ldarg.0
0x4a966  ldc.i4.3
0x4a967  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4a96c  call     bool [mscorlib]System.Boolean::Parse(string)
0x4a971  callvirt instance void Microsoft.SharePoint.Taxonomy.TermSetItem::set_IsAvailableForTagging(bool value)
0x4a976  br.s     loc_4A9A2
0x4a978  ldc.i4   0x66633375
0x4a97d  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a982  ldc.i4.s 0x64
0x4a984  ldstr    aTheAvailableFo// "The available for tagging entry on line"...
0x4a989  ldc.i4.1
0x4a98a  newarr   [mscorlib]System.Object
0x4a98f  stloc.s  0xE
0x4a991  ldloc.s  0xE
0x4a993  ldc.i4.0
0x4a994  ldarg.3
0x4a995  box      [mscorlib]System.Int32
0x4a99a  stelem.ref
0x4a99b  ldloc.s  0xE
0x4a99d  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4a9a2  leave.s  loc_4AA02
0x4a9a4  pop
0x4a9a5  ldc.i4   0x66633376
0x4a9aa  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a9af  ldc.i4.s 0xA
0x4a9b1  ldstr    aErrorEncounter_5// "Error encountered during import.  The a"...
0x4a9b6  ldc.i4.1
0x4a9b7  newarr   [mscorlib]System.Object
0x4a9bc  stloc.s  0xF
0x4a9be  ldloc.s  0xF
0x4a9c0  ldc.i4.0
0x4a9c1  ldarg.3
0x4a9c2  box      [mscorlib]System.Int32
0x4a9c7  stelem.ref
0x4a9c8  ldloc.s  0xF
0x4a9ca  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4a9cf  ldc.i4.0
0x4a9d0  stloc.3
0x4a9d1  leave.s  loc_4AA02
0x4a9d3  pop
0x4a9d4  ldc.i4   0x66633377
0x4a9d9  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4a9de  ldc.i4.s 0xA
0x4a9e0  ldstr    aErrorEncounter_5// "Error encountered during import.  The a"...
0x4a9e5  ldc.i4.1
0x4a9e6  newarr   [mscorlib]System.Object
0x4a9eb  stloc.s  0x10
0x4a9ed  ldloc.s  0x10
0x4a9ef  ldc.i4.0
0x4a9f0  ldarg.3
0x4a9f1  box      [mscorlib]System.Int32
0x4a9f6  stelem.ref
0x4a9f7  ldloc.s  0x10
0x4a9f9  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4a9fe  ldc.i4.0
0x4a9ff  stloc.3
0x4aa00  leave.s  loc_4AA02
0x4aa02  ldarg.0
0x4aa03  ldc.i4.4
0x4aa04  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4aa09  stloc.s  8
0x4aa0b  ldloc.s  8
0x4aa0d  callvirt instance int32 [mscorlib]System.String::get_Length()
0x4aa12  ldc.i4   0x3E8
0x4aa17  ble.s    loc_4AA28
0x4aa19  ldloc.s  8
0x4aa1b  ldc.i4.0
0x4aa1c  ldc.i4   0x3E8
0x4aa21  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x4aa26  stloc.s  8
0x4aa28  ldloc.s  8
0x4aa2a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4aa2f  brtrue.s loc_4AA82
0x4aa31  ldloc.s  8
0x4aa33  ldstr    aDescription_0// "description"
0x4aa38  call     void Microsoft.SharePoint.Taxonomy.Internal.CommonValidator::ValidateDescription(string description, string parameterName)
0x4aa3d  ldloc.1
0x4aa3e  ldarg.0
0x4aa3f  ldc.i4.4
0x4aa40  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<string>::get_Item(!!T0)
0x4aa45  ldarg.2
0x4aa46  callvirt instance void Microsoft.SharePoint.Taxonomy.Term::SetDescription(string description, int32 lcid)
0x4aa4b  leave.s  loc_4AA82
0x4aa4d  pop
0x4aa4e  ldc.i4   0x66633378
0x4aa53  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4aa58  ldc.i4.s 0xA
0x4aa5a  ldstr    aErrorEncounter_6// "Error encountered during import.  The d"...
0x4aa5f  ldc.i4.2
0x4aa60  newarr   [mscorlib]System.Object
0x4aa65  stloc.s  0x11
0x4aa67  ldloc.s  0x11
0x4aa69  ldc.i4.0
0x4aa6a  ldloc.s  8
0x4aa6c  stelem.ref
0x4aa6d  ldloc.s  0x11
0x4aa6f  ldc.i4.1
0x4aa70  ldarg.3
0x4aa71  box      [mscorlib]System.Int32
0x4aa76  stelem.ref
0x4aa77  ldloc.s  0x11
0x4aa79  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x4aa7e  ldc.i4.0
0x4aa7f  stloc.3
0x4aa80  leave.s  loc_4AA82
0x4aa82  ldloc.3
0x4aa83  brtrue.s loc_4AADC
0x4aa85  ldc.i4.0
0x4aa86  stloc.s  4
0x4aa88  ldloc.1
0x4aa89  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TaxonomyItem::get_Id()
0x4aa8e  stloc.s  9
0x4aa90  ldloc.1
0x4aa91  callvirt instance void Microsoft.SharePoint.Taxonomy.TaxonomyItem::Delete()
0x4aa96  leave.s  loc_4AADC
0x4aa98  stloc.s  0xA
0x4aa9a  ldc.i4   0x66367073
0x4aa9f  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x4aaa4  ldc.i4.s 0xA
0x4aaa6  ldstr    aErrorEncounter_7// "Error encountered during import when at"...
0x4aaab  ldc.i4.3
  ... truncated ...
```
