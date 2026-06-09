# Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCache::ValidateUpdate

- ea: `0x2d7330`
- end: `0x2d7cf9`
- name: `Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCache::ValidateUpdate`
- size: `2505`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2d6d90`

## callees

- `0x1c8480`
- `0x1c8540`
- `0x1c8740`
- `0x24dab0`
- `0x251db0`
- `0x2b4f00`
- `0x2d2d90`
- `0x2d2de0`
- `0x2d5540`
- `0x2d5ac0`
- `0x2d5b70`
- `0x2d5d10`
- `0x2d5d50`
- `0x2d7330`
- `0x2d84e0`
- `0x2d8560`
- `0x2d86f0`
- `0x2d8a50`
- `0x93cf20`
- `0x93dab0`
- `0x93dae0`
- `0x957f10`

## string_xrefs

- `0x2d73b4`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: ParentId and Id Dict cache size mismatch: ParentId has [{0}] and Id has [{1}].`
- `0x2d7405`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: ParentId and Id cache size mismatch: ParentId has [{0}] and Id has [{1}].`
- `0x2d746c`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: ParentId cache is not sorted: Element at address {0} [{1}] has comparison of {2} to element at address {3} [{4}].`
- `0x2d7546`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Id cache is not sorted: Element at address {0} [{1}] has comparison of {2} to element at address {3} [{4}].`
- `0x2d7618`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Dependency cache is not sorted: Element at address {0} [{1}] has comparison of {2} to element at address {3} [{4}].`
- `0x2d76f1`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Persisted cache and regenerated cache size mismatch: Persisted cache has [{0}] and regenerated cache has [{1}].`
- `0x2d7773`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: ParentId cache mismatch for fields entry [{0}] and index {1}.`
- `0x2d77e2`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Id dict cache mismatch for fields entry [{0}].`
- `0x2d783a`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Id cache mismatch for fields entry [{0}] and index {1}.`
- `0x2d78e2`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: ParentId cache mismatch for object [{0}] and index {1} and value [{2}].`
- `0x2d794e`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Id dict cache mismatch for object [{0}] and value [{1}].`
- `0x2d79a4`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Id cache mismatch for object [{0}] and index {1} and value [{2}].`
- `0x2d7a30`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Child collection mismatch for object [{0}]: cache has {1} elements and DB has {2}.`
- `0x2d7ac8`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Dependency collection mismatch for object [{0}]: cache has {1} elements and DB from refresh query has {2}.`
- `0x2d7b43`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Dependency collection mismatch for object [{0}]: DB data from refresh has {1} elements and DB from collection query has {2}.`
- `0x2d7bfd`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Name cache mismatch for object [{0}]: object in cache is {1} but isDeleted is {2}.`
- `0x2d7c5d`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Name cache mismatch for object [{0}]: object in cache has GUID {1} but DB has GUID {2}..`
- `0x2d7cc0`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Hit exception while validating cache update: {0}.`
- `0x2d7ced`: `SPPersistedObjectDerivedCollectionCache.ValidateUpdate: Detected one or more inconsistencies in the derived collection cache.`

## pseudocode

```c

```

## disassembly

```asm
0x2d7330  ldc.i4.1
0x2d7331  stloc.0
0x2d7332  ldc.i4   0xC8
0x2d7337  stloc.1
0x2d7338  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d733d  ldloc.1
0x2d733e  call     bool Microsoft.SharePoint.Diagnostics.ULS::ShouldTrace(class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level)
0x2d7343  brtrue.s loc_2D734F
0x2d7345  ldarg.0
0x2d7346  call     bool Microsoft.SharePoint.Administration.SPPersistedObjectCollectionCache::ValidateDerivedCollectionCacheUpdateEnabled(class Microsoft.SharePoint.Administration.SPConfigurationDatabase configDb)
0x2d734b  brtrue.s loc_2D734F
0x2d734d  ldloc.0
0x2d734e  ret
0x2d734f  ldnull
0x2d7350  stloc.2
0x2d7351  ldnull
0x2d7352  stloc.3
0x2d7353  ldnull
0x2d7354  stloc.s  4
0x2d7356  ldnull
0x2d7357  stloc.s  5
0x2d7359  ldnull
0x2d735a  stloc.s  6
0x2d735c  ldarg.0
0x2d735d  ldloca.s 2
0x2d735f  ldloca.s 3
0x2d7361  ldloca.s 4
0x2d7363  ldloca.s 5
0x2d7365  ldloca.s 6
0x2d7367  call     bool Microsoft.SharePoint.Administration.SPPersistedObjectDerivedCollectionCache::FetchDerivedMemoryCaches(class Microsoft.SharePoint.Administration.SPConfigurationDatabase configDb, [out] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>& objectContainerFields, [out] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>& objectContainerFieldsById, [out] class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>& objectContainerFieldsByIdDict, [out] class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectDependencyRecord>& dependencyRecords, [out] class Microsoft.SharePoint.Administration.SPPersistedObjectClassDictionary& classDict)
0x2d736c  brfalse  loc_2D7CB0
0x2d7371  newobj   instance void Microsoft.SharePoint.Administration.SPPOCFComparerByParentIdAndId::.ctor()
0x2d7376  stloc.s  7
0x2d7378  newobj   instance void Microsoft.SharePoint.Administration.SPPOCFComparerById::.ctor()
0x2d737d  stloc.s  8
0x2d737f  newobj   instance void Microsoft.SharePoint.Administration.SPPODRComparerByObjectId::.ctor()
0x2d7384  stloc.s  9
0x2d7386  ldarg.s  5
0x2d7388  newobj   instance void class [System.Core]System.Collections.Generic.HashSet`1<valuetype [mscorlib]System.Guid>::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x2d738d  stloc.s  0xA
0x2d738f  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_UseHashTableInsteadOfBinarySearchCode()
0x2d7394  brfalse.s loc_2D73EB
0x2d7396  ldloc.2
0x2d7397  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d739c  ldloc.s  4
0x2d739e  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d73a3  beq      loc_2D7439
0x2d73a8  ldc.i4   0x1817845
0x2d73ad  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d73b2  ldc.i4.s 0xF
0x2d73b4  ldstr    aSppersistedobj_85// "SPPersistedObjectDerivedCollectionCache"...
0x2d73b9  ldc.i4.2
0x2d73ba  newarr   [mscorlib]System.Object
0x2d73bf  stloc.s  0x1D
0x2d73c1  ldloc.s  0x1D
0x2d73c3  ldc.i4.0
0x2d73c4  ldloc.2
0x2d73c5  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d73ca  box      [mscorlib]System.Int32
0x2d73cf  stelem.ref
0x2d73d0  ldloc.s  0x1D
0x2d73d2  ldc.i4.1
0x2d73d3  ldloc.s  4
0x2d73d5  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d73da  box      [mscorlib]System.Int32
0x2d73df  stelem.ref
0x2d73e0  ldloc.s  0x1D
0x2d73e2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d73e7  ldc.i4.0
0x2d73e8  stloc.0
0x2d73e9  br.s     loc_2D7439
0x2d73eb  ldloc.2
0x2d73ec  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d73f1  ldloc.3
0x2d73f2  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d73f7  beq.s    loc_2D7439
0x2d73f9  ldc.i4   0x111D5CF
0x2d73fe  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d7403  ldc.i4.s 0xF
0x2d7405  ldstr    aSppersistedobj_86// "SPPersistedObjectDerivedCollectionCache"...
0x2d740a  ldc.i4.2
0x2d740b  newarr   [mscorlib]System.Object
0x2d7410  stloc.s  0x1E
0x2d7412  ldloc.s  0x1E
0x2d7414  ldc.i4.0
0x2d7415  ldloc.2
0x2d7416  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d741b  box      [mscorlib]System.Int32
0x2d7420  stelem.ref
0x2d7421  ldloc.s  0x1E
0x2d7423  ldc.i4.1
0x2d7424  ldloc.3
0x2d7425  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d742a  box      [mscorlib]System.Int32
0x2d742f  stelem.ref
0x2d7430  ldloc.s  0x1E
0x2d7432  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d7437  ldc.i4.0
0x2d7438  stloc.0
0x2d7439  ldc.i4.0
0x2d743a  stloc.s  0xB
0x2d743c  br       loc_2D74FA
0x2d7441  ldloc.s  7
0x2d7443  ldloc.2
0x2d7444  ldloc.s  0xB
0x2d7446  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d744b  ldloc.2
0x2d744c  ldloc.s  0xB
0x2d744e  ldc.i4.1
0x2d744f  add
0x2d7450  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d7455  callvirt instance int32 class [mscorlib]System.Collections.Generic.Comparer`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::Compare(var<u1>, !!T0)
0x2d745a  ldc.i4.0
0x2d745b  blt      loc_2D74F4
0x2d7460  ldc.i4   0x111D5D0
0x2d7465  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d746a  ldc.i4.s 0xF
0x2d746c  ldstr    aSppersistedobj_87// "SPPersistedObjectDerivedCollectionCache"...
0x2d7471  ldc.i4.5
0x2d7472  newarr   [mscorlib]System.Object
0x2d7477  stloc.s  0x1F
0x2d7479  ldloc.s  0x1F
0x2d747b  ldc.i4.0
0x2d747c  ldloc.s  0xB
0x2d747e  box      [mscorlib]System.Int32
0x2d7483  stelem.ref
0x2d7484  ldloc.s  0x1F
0x2d7486  ldc.i4.1
0x2d7487  ldloc.2
0x2d7488  ldloc.s  0xB
0x2d748a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d748f  stloc.s  0x20
0x2d7491  ldloca.s 0x20
0x2d7493  constrained. Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields
0x2d7499  callvirt instance string [mscorlib]System.Object::ToString()
0x2d749e  stelem.ref
0x2d749f  ldloc.s  0x1F
0x2d74a1  ldc.i4.2
0x2d74a2  ldloc.s  7
0x2d74a4  ldloc.2
0x2d74a5  ldloc.s  0xB
0x2d74a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d74ac  ldloc.2
0x2d74ad  ldloc.s  0xB
0x2d74af  ldc.i4.1
0x2d74b0  add
0x2d74b1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d74b6  callvirt instance int32 class [mscorlib]System.Collections.Generic.Comparer`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::Compare(var<u1>, !!T0)
0x2d74bb  box      [mscorlib]System.Int32
0x2d74c0  stelem.ref
0x2d74c1  ldloc.s  0x1F
0x2d74c3  ldc.i4.3
0x2d74c4  ldloc.s  0xB
0x2d74c6  ldc.i4.1
0x2d74c7  add
0x2d74c8  box      [mscorlib]System.Int32
0x2d74cd  stelem.ref
0x2d74ce  ldloc.s  0x1F
0x2d74d0  ldc.i4.4
0x2d74d1  ldloc.2
0x2d74d2  ldloc.s  0xB
0x2d74d4  ldc.i4.1
0x2d74d5  add
0x2d74d6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d74db  stloc.s  0x21
0x2d74dd  ldloca.s 0x21
0x2d74df  constrained. Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields
0x2d74e5  callvirt instance string [mscorlib]System.Object::ToString()
0x2d74ea  stelem.ref
0x2d74eb  ldloc.s  0x1F
0x2d74ed  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d74f2  ldc.i4.0
0x2d74f3  stloc.0
0x2d74f4  ldloc.s  0xB
0x2d74f6  ldc.i4.1
0x2d74f7  add
0x2d74f8  stloc.s  0xB
0x2d74fa  ldloc.s  0xB
0x2d74fc  ldloc.2
0x2d74fd  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d7502  ldc.i4.1
0x2d7503  sub
0x2d7504  blt      loc_2D7441
0x2d7509  call     bool Microsoft.SharePoint.Administration.SPConfigurationDatabaseDebuggingSettings::get_UseHashTableInsteadOfBinarySearchCode()
0x2d750e  brtrue   loc_2D75E3
0x2d7513  ldc.i4.0
0x2d7514  stloc.s  0xB
0x2d7516  br       loc_2D75D4
0x2d751b  ldloc.s  8
0x2d751d  ldloc.3
0x2d751e  ldloc.s  0xB
0x2d7520  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d7525  ldloc.3
0x2d7526  ldloc.s  0xB
0x2d7528  ldc.i4.1
0x2d7529  add
0x2d752a  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d752f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Comparer`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::Compare(var<u1>, !!T0)
0x2d7534  ldc.i4.0
0x2d7535  blt      loc_2D75CE
0x2d753a  ldc.i4   0x111D5D1
0x2d753f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d7544  ldc.i4.s 0xF
0x2d7546  ldstr    aSppersistedobj_88// "SPPersistedObjectDerivedCollectionCache"...
0x2d754b  ldc.i4.5
0x2d754c  newarr   [mscorlib]System.Object
0x2d7551  stloc.s  0x22
0x2d7553  ldloc.s  0x22
0x2d7555  ldc.i4.0
0x2d7556  ldloc.s  0xB
0x2d7558  box      [mscorlib]System.Int32
0x2d755d  stelem.ref
0x2d755e  ldloc.s  0x22
0x2d7560  ldc.i4.1
0x2d7561  ldloc.3
0x2d7562  ldloc.s  0xB
0x2d7564  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d7569  stloc.s  0x23
0x2d756b  ldloca.s 0x23
0x2d756d  constrained. Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields
0x2d7573  callvirt instance string [mscorlib]System.Object::ToString()
0x2d7578  stelem.ref
0x2d7579  ldloc.s  0x22
0x2d757b  ldc.i4.2
0x2d757c  ldloc.s  7
0x2d757e  ldloc.3
0x2d757f  ldloc.s  0xB
0x2d7581  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d7586  ldloc.3
0x2d7587  ldloc.s  0xB
0x2d7589  ldc.i4.1
0x2d758a  add
0x2d758b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d7590  callvirt instance int32 class [mscorlib]System.Collections.Generic.Comparer`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::Compare(var<u1>, !!T0)
0x2d7595  box      [mscorlib]System.Int32
0x2d759a  stelem.ref
0x2d759b  ldloc.s  0x22
0x2d759d  ldc.i4.3
0x2d759e  ldloc.s  0xB
0x2d75a0  ldc.i4.1
0x2d75a1  add
0x2d75a2  box      [mscorlib]System.Int32
0x2d75a7  stelem.ref
0x2d75a8  ldloc.s  0x22
0x2d75aa  ldc.i4.4
0x2d75ab  ldloc.3
0x2d75ac  ldloc.s  0xB
0x2d75ae  ldc.i4.1
0x2d75af  add
0x2d75b0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Item(!!T0)
0x2d75b5  stloc.s  0x24
0x2d75b7  ldloca.s 0x24
0x2d75b9  constrained. Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields
0x2d75bf  callvirt instance string [mscorlib]System.Object::ToString()
0x2d75c4  stelem.ref
0x2d75c5  ldloc.s  0x22
0x2d75c7  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x2d75cc  ldc.i4.0
0x2d75cd  stloc.0
0x2d75ce  ldloc.s  0xB
0x2d75d0  ldc.i4.1
0x2d75d1  add
0x2d75d2  stloc.s  0xB
0x2d75d4  ldloc.s  0xB
0x2d75d6  ldloc.3
0x2d75d7  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectContainerFields>::get_Count()
0x2d75dc  ldc.i4.1
0x2d75dd  sub
0x2d75de  blt      loc_2D751B
0x2d75e3  ldc.i4.0
0x2d75e4  stloc.s  0xB
0x2d75e6  br       loc_2D76AA
0x2d75eb  ldloc.s  9
0x2d75ed  ldloc.s  5
0x2d75ef  ldloc.s  0xB
0x2d75f1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectDependencyRecord>::get_Item(!!T0)
0x2d75f6  ldloc.s  5
0x2d75f8  ldloc.s  0xB
0x2d75fa  ldc.i4.1
0x2d75fb  add
0x2d75fc  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.List`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectDependencyRecord>::get_Item(!!T0)
0x2d7601  callvirt instance int32 class [mscorlib]System.Collections.Generic.Comparer`1<valuetype Microsoft.SharePoint.Administration.SPPersistedObjectDependencyRecord>::Compare(var<u1>, !!T0)
0x2d7606  ldc.i4.0
0x2d7607  blt      loc_2D76A4
0x2d760c  ldc.i4   0x111D5D2
0x2d7611  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ConfigCache()
0x2d7616  ldc.i4.s 0xF
0x2d7618  ldstr    aSppersistedobj_89// "SPPersistedObjectDerivedCollectionCache"...
0x2d761d  ldc.i4.5
0x2d761e  newarr   [mscorlib]System.Object
0x2d7623  stloc.s  0x25
0x2d7625  ldloc.s  0x25
0x2d7627  ldc.i4.0
0x2d7628  ldloc.s  0xB
0x2d762a  box      [mscorlib]System.Int32
0x2d762f  stelem.ref
0x2d7630  ldloc.s  0x25
0x2d7632  ldc.i4.1
0x2d7633  ldloc.s  5
0x2d7635  ldloc.s  0xB
  ... truncated ...
```
