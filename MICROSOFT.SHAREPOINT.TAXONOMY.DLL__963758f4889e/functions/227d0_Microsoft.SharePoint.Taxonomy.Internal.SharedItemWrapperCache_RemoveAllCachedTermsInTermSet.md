# Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::RemoveAllCachedTermsInTermSet

- ea: `0x227d0`
- end: `0x228c1`
- name: `Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::RemoveAllCachedTermsInTermSet`
- size: `241`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x21710`

## callees

- `0x21920`
- `0x21930`
- `0x22260`
- `0x227d0`
- `0x228d0`
- `0x2ebf0`
- `0x2ec50`
- `0x32130`

## string_xrefs

- `0x227dc`: `Finding  all cached Terms of a TermSet`
- `0x228a8`: `Removing all cached Terms of a TermSet`

## pseudocode

```c

```

## disassembly

```asm
0x227d0  ldc.i4   0x7041C4
0x227d5  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x227da  ldc.i4.s 0x64
0x227dc  ldstr    aFindingAllCach// "Finding  all cached Terms of a TermSet"
0x227e1  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x227e6  ldarg.0
0x227e7  ldfld    valuetype Microsoft.SharePoint.Taxonomy.Internal.ItemType Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::itemType
0x227ec  brfalse.s loc_227EF
0x227ee  ret
0x227ef  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<int32>::.ctor()
0x227f4  stloc.0
0x227f5  ldarg.0
0x227f6  call     instance class [mscorlib]System.IDisposable class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::AcquireReaderLock()
0x227fb  stloc.s  4
0x227fd  ldnull
0x227fe  stloc.1
0x227ff  ldnull
0x22800  stloc.2
0x22801  ldarg.0
0x22802  call     instance class [mscorlib]System.Collections.Hashtable class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::get_HashTable()
0x22807  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Keys()
0x2280c  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x22811  stloc.s  5
0x22813  br.s     loc_2286E
0x22815  ldloc.s  5
0x22817  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2281c  castclass Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey
0x22821  stloc.3
0x22822  ldarg.0
0x22823  ldloc.3
0x22824  callvirt instance var<u1> class [Microsoft.Office.Server]Microsoft.Office.Server.Utilities.ThreadSafeCache`2<class Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey, class Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper>::get_Item(void)
0x22829  stloc.2
0x2282a  ldloc.2
0x2282b  brfalse.s loc_2286E
0x2282d  ldloc.2
0x2282e  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItem Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapper::get_Item()
0x22833  castclass Microsoft.SharePoint.Taxonomy.Internal.SharedTerm
0x22838  stloc.1
0x22839  ldloc.1
0x2283a  brfalse.s loc_2286E
0x2283c  ldloc.1
0x2283d  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_PartitionId()
0x22842  ldarg.1
0x22843  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey::get_PartitionId()
0x22848  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x2284d  brfalse.s loc_2286E
0x2284f  ldloc.1
0x22850  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership> Microsoft.SharePoint.Taxonomy.Internal.SharedTerm::get_Memberships()
0x22855  ldarg.1
0x22856  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey::get_InternalId()
0x2285b  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<int32, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermMembership>::ContainsKey(var<u1>)
0x22860  brfalse.s loc_2286E
0x22862  ldloc.0
0x22863  ldloc.1
0x22864  callvirt instance int32 Microsoft.SharePoint.Taxonomy.Internal.SharedItem::get_Id()
0x22869  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<int32>::Add(var<u1>)
0x2286e  ldloc.s  5
0x22870  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x22875  brtrue.s loc_22815
0x22877  leave.s  loc_2288E
0x22879  ldloc.s  5
0x2287b  isinst   [mscorlib]System.IDisposable
0x22880  stloc.s  6
0x22882  ldloc.s  6
0x22884  brfalse.s loc_2288D
0x22886  ldloc.s  6
0x22888  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2288d  endfinally
0x2288e  leave.s  loc_2289C
0x22890  ldloc.s  4
0x22892  brfalse.s loc_2289B
0x22894  ldloc.s  4
0x22896  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2289b  endfinally
0x2289c  ldc.i4   0x7041C6
0x228a1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x228a6  ldc.i4.s 0x64
0x228a8  ldstr    aRemovingAllCac// "Removing all cached Terms of a TermSet"
0x228ad  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x228b2  ldarg.0
0x228b3  ldarg.1
0x228b4  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.Internal.SharedItemInternalKey::get_PartitionId()
0x228b9  ldloc.0
0x228ba  ldarg.2
0x228bb  call     instance void Microsoft.SharePoint.Taxonomy.Internal.SharedItemWrapperCache::RemoveCachedItems(valuetype [mscorlib]System.Guid partitionId, class [mscorlib]System.Collections.Generic.List`1<int32> idList, valuetype [mscorlib]System.DateTime changeTime)
0x228c0  ret
```
