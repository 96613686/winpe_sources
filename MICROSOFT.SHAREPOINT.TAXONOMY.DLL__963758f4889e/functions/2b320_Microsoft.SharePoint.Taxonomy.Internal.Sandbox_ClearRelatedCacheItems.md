# Microsoft.SharePoint.Taxonomy.Internal.Sandbox::ClearRelatedCacheItems

- ea: `0x2b320`
- end: `0x2b3be`
- name: `Microsoft.SharePoint.Taxonomy.Internal.Sandbox::ClearRelatedCacheItems`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x2b3c0`

## callees

- `0x1eca0`
- `0x1ed10`
- `0x2b320`
- `0x2bc40`
- `0x56210`
- `0x56c20`
- `0x56df0`

## string_xrefs

- `0x2b32c`: `Clearing sandbox related items from cache.`
- `0x2b3b3`: `Cleared sandbox related items from cache.`

## pseudocode

```c

```

## disassembly

```asm
0x2b320  ldc.i4   0x3265746F
0x2b325  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b32a  ldc.i4.s 0x64
0x2b32c  ldstr    aClearingSandbo// "Clearing sandbox related items from cac"...
0x2b331  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b336  ldarg.0
0x2b337  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b33c  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache Microsoft.SharePoint.Taxonomy.TermStore::get_Cache()
0x2b341  stloc.0
0x2b342  ldarg.0
0x2b343  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem> Microsoft.SharePoint.Taxonomy.Internal.Sandbox::sandboxItems
0x2b348  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::get_Values()
0x2b34d  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::GetEnumerator()
0x2b352  stloc.2
0x2b353  br.s     loc_2B369
0x2b355  ldloca.s 2
0x2b357  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::get_Current()
0x2b35c  stloc.1
0x2b35d  ldloc.0
0x2b35e  ldloc.1
0x2b35f  callvirt instance class Microsoft.SharePoint.Taxonomy.Internal.SharedItem Microsoft.SharePoint.Taxonomy.Internal.SandboxItem::get_SharedItem()
0x2b364  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::RemoveItem(class Microsoft.SharePoint.Taxonomy.Internal.SharedItem item)
0x2b369  ldloca.s 2
0x2b36b  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>::MoveNext()
0x2b370  brtrue.s loc_2B355
0x2b372  leave.s  loc_2B382
0x2b374  ldloca.s 2
0x2b376  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/ValueCollection/Enumerator<class SandboxItemKey, class Microsoft.SharePoint.Taxonomy.Internal.SandboxItem>
0x2b37c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b381  endfinally
0x2b382  ldarg.0
0x2b383  ldfld    class Microsoft.SharePoint.Taxonomy.Internal.TermStoreSandboxItem Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStoreSandboxItem
0x2b388  brfalse.s loc_2B3A7
0x2b38a  ldloc.0
0x2b38b  ldarg.0
0x2b38c  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b391  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Taxonomy.TermStore::get_PartitionId()
0x2b396  callvirt instance void Microsoft.SharePoint.Taxonomy.Internal.TaxonomyCache::FlushTermStoreData(valuetype [mscorlib]System.Guid partitionId)
0x2b39b  ldarg.0
0x2b39c  ldfld    class Microsoft.SharePoint.Taxonomy.TermStore Microsoft.SharePoint.Taxonomy.Internal.Sandbox::termStore
0x2b3a1  ldnull
0x2b3a2  callvirt instance void Microsoft.SharePoint.Taxonomy.TermStore::ReplaceSharedTermStore(class Microsoft.SharePoint.Taxonomy.Internal.TermStoreSandboxItem sandboxItem)
0x2b3a7  ldc.i4   0x32657470
0x2b3ac  call     class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCat::get_msoulscat_OSRV_Taxonomy()
0x2b3b1  ldc.i4.s 0x64
0x2b3b3  ldstr    aClearedSandbox// "Cleared sandbox related items from cach"...
0x2b3b8  call     void [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSCatBase, valuetype [Microsoft.Office.Server]Microsoft.Office.Server.Diagnostics.ULSTraceLevel, string)
0x2b3bd  ret
```
