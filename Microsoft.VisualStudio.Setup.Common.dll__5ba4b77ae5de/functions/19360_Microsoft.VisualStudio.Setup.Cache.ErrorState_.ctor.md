# Microsoft.VisualStudio.Setup.Cache.ErrorState::.ctor

- ea: `0x19360`
- end: `0x193ad`
- name: `Microsoft.VisualStudio.Setup.Cache.ErrorState::.ctor`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x19020`
- `0x1afb0`

## callees

- `0x194a0`
- `0x194b0`
- `0x19750`
- `0x1bc50`

## pseudocode

```c

```

## disassembly

```asm
0x19360  ldarg.0
0x19361  call     instance void [mscorlib]System.Object::.ctor()
0x19366  ldarg.0
0x19367  ldnull
0x19368  newobj   instance void Microsoft.VisualStudio.Setup.Cache.FailedPackageReferenceCollection::.ctor([opt] class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.VisualStudio.Setup.Cache.FailedPackageReference> comparer)
0x1936d  stfld    class Microsoft.VisualStudio.Setup.Cache.FailedPackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.ErrorState::<FailedPackages>k__BackingField
0x19372  ldarg.0
0x19373  call     instance class Microsoft.VisualStudio.Setup.Cache.FailedPackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.ErrorState::get_FailedPackages()
0x19378  ldarg.0
0x19379  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::<.ctor>b__3_0(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.FailedPackageReference> args)
0x1937f  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.FailedPackageReference>>::.ctor(object, native int)
0x19384  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class Microsoft.VisualStudio.Setup.Cache.FailedPackageReference>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x19389  ldarg.0
0x1938a  ldnull
0x1938b  newobj   instance void Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection::.ctor([opt] class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference> comparer)
0x19390  stfld    class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.ErrorState::<SkippedPackages>k__BackingField
0x19395  ldarg.0
0x19396  call     instance class Microsoft.VisualStudio.Setup.Cache.PackageReferenceCollection Microsoft.VisualStudio.Setup.Cache.ErrorState::get_SkippedPackages()
0x1939b  ldarg.0
0x1939c  ldftn    instance void Microsoft.VisualStudio.Setup.Cache.ErrorState::<.ctor>b__3_1(object source, class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference> args)
0x193a2  newobj   instance void class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference>>::.ctor(object, native int)
0x193a7  callvirt instance void class Microsoft.VisualStudio.Setup.Cache.IndexedCollection`1<class Microsoft.VisualStudio.Setup.Cache.PackageReference>::add_CollectionChanged(class [mscorlib]System.EventHandler`1<class Microsoft.VisualStudio.Setup.NotifyCollectionChangedEventArgs`1<var<u1>>>)
0x193ac  ret
```
