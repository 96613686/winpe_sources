# Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::UpdateStatusForTermStores

- ea: `0x1f860`
- end: `0x1f948`
- name: `Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::UpdateStatusForTermStores`
- size: `232`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x20600`
- `0x20e00`

## callees

- `0x1f860`
- `0x1f980`
- `0x1fb20`
- `0x1fb30`
- `0x337e0`
- `0x33810`

## string_xrefs

- `0x1f8c2`: `Failed to get term store partition during cache check for changes.  Proxy '{0}'. Exception: {1}`
- `0x1f8f8`: `Failed to get term store partition during cache check for changes.  Proxy '{0}'. Exception: {1}`

## pseudocode

```c

```

## disassembly

```asm
0x1f860  ldarg.0
0x1f861  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::AcquireTermStoreDataWriterLock()
0x1f866  ldarg.0
0x1f867  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore> Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::termStoreData
0x1f86c  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore>::get_Values()
0x1f871  call     T0x2B000027
0x1f876  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore>::GetEnumerator()
0x1f87b  stloc.3
0x1f87c  br       loc_1F922
0x1f881  ldloca.s 3
0x1f883  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore>::get_Current()
0x1f888  stloc.0
0x1f889  ldc.i4.1
0x1f88a  stloc.1
0x1f88b  ldloc.0
0x1f88c  brfalse.s loc_1F8B0
0x1f88e  ldloc.0
0x1f88f  ldarg.1
0x1f890  ldarg.2
0x1f891  ldarg.3
0x1f892  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x1f897  ldloc.1
0x1f898  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::SetIsOnlineAndIsAccessDeniedState(bool isOnlineValue, bool isAccessDeniedValue, string proxyName, bool doLogEvent)
0x1f89d  ldc.i4.0
0x1f89e  stloc.1
0x1f89f  ldarg.1
0x1f8a0  brfalse.s loc_1F8B0
0x1f8a2  ldloc.0
0x1f8a3  callvirt instance bool Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore::get_IsInitialized()
0x1f8a8  brtrue.s loc_1F8B0
0x1f8aa  ldarg.0
0x1f8ab  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::FlushTermStoreData()
0x1f8b0  leave.s  loc_1F922
0x1f8b2  stloc.2
0x1f8b3  ldarg.1
0x1f8b4  brtrue.s loc_1F8EC
0x1f8b6  ldc.i4   0x66386272
0x1f8bb  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f8c0  ldc.i4.s 0x64
0x1f8c2  ldstr    aFailedToGetTer_0// "Failed to get term store partition duri"...
0x1f8c7  ldc.i4.2
0x1f8c8  newarr   [mscorlib]System.Object
0x1f8cd  stloc.s  4
0x1f8cf  ldloc.s  4
0x1f8d1  ldc.i4.0
0x1f8d2  ldarg.3
0x1f8d3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x1f8d8  stelem.ref
0x1f8d9  ldloc.s  4
0x1f8db  ldc.i4.1
0x1f8dc  ldloc.2
0x1f8dd  callvirt instance string [mscorlib]System.Object::ToString()
0x1f8e2  stelem.ref
0x1f8e3  ldloc.s  4
0x1f8e5  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1f8ea  br.s     loc_1F920
0x1f8ec  ldc.i4   0x66386273
0x1f8f1  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x1f8f6  ldc.i4.s 0xF
0x1f8f8  ldstr    aFailedToGetTer_0// "Failed to get term store partition duri"...
0x1f8fd  ldc.i4.2
0x1f8fe  newarr   [mscorlib]System.Object
0x1f903  stloc.s  5
0x1f905  ldloc.s  5
0x1f907  ldc.i4.0
0x1f908  ldarg.3
0x1f909  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_DisplayName()
0x1f90e  stelem.ref
0x1f90f  ldloc.s  5
0x1f911  ldc.i4.1
0x1f912  ldloc.2
0x1f913  callvirt instance string [mscorlib]System.Object::ToString()
0x1f918  stelem.ref
0x1f919  ldloc.s  5
0x1f91b  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string, object[])
0x1f920  leave.s  loc_1F922
0x1f922  ldloca.s 3
0x1f924  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore>::MoveNext()
0x1f929  brtrue   loc_1F881
0x1f92e  leave.s  loc_1F93E
0x1f930  ldloca.s 3
0x1f932  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class Microsoft.SharePoint.Taxonomy.Internal.SharedTermStore>
0x1f938  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f93d  endfinally
0x1f93e  leave.s  loc_1F947
0x1f940  ldarg.0
0x1f941  call     instance void Microsoft.SharePoint.Taxonomy.Internal.CombiningTaxonomyCache::ReleaseTermStoreDataWriterLock()
0x1f946  endfinally
0x1f947  ret
```
