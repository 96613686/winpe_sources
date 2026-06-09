# Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetAvailablePackages

- ea: `0x55a60`
- end: `0x55c1b`
- name: `Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetAvailablePackages`
- size: `443`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x51f40`

## callees

- `0x544b0`
- `0x54560`
- `0x55640`
- `0x55a60`
- `0x55c20`
- `0x55e30`

## string_xrefs

- `0x55b51`: `Added {0} extensions to product '{1}'`
- `0x55b9e`: `Added extension '`

## pseudocode

```c

```

## disassembly

```asm
0x55a60  ldarg.0
0x55a61  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetCatalog()
0x55a66  stloc.0
0x55a67  ldloc.0
0x55a68  brfalse  loc_55C12
0x55a6d  ldloc.0
0x55a6e  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Packages()
0x55a73  stloc.1
0x55a74  ldloc.1
0x55a75  brfalse  loc_55C12
0x55a7a  ldloc.1
0x55a7b  call     T0x2B0000E1
0x55a80  brfalse  loc_55C12
0x55a85  ldloc.1
0x55a86  ldarg.0
0x55a87  ldfld    class Microsoft.VisualStudio.Setup.Cache.ExtensionManifestRepository Microsoft.VisualStudio.Setup.Cache.InstanceRepository::extensions
0x55a8c  dup
0x55a8d  brtrue.s loc_55A93
0x55a8f  pop
0x55a90  ldnull
0x55a91  br.s     loc_55A98
0x55a93  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage> Microsoft.VisualStudio.Setup.Cache.ExtensionManifestRepository::GetPackages()
0x55a98  call     T0x2B000274
0x55a9d  stloc.1
0x55a9e  ldarg.0
0x55a9f  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetPackages()
0x55aa4  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> <>c::<>9__46_0
0x55aa9  dup
0x55aaa  brtrue.s loc_55AC3
0x55aac  pop
0x55aad  ldsfld   class <>c <>c::<>9
0x55ab2  ldftn    instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity <>c::<GetAvailablePackages>b__46_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity x)
0x55ab8  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>::.ctor(object, native int)
0x55abd  dup
0x55abe  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity> <>c::<>9__46_0
0x55ac3  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x55ac8  call     T0x2B000275
0x55acd  stloc.2
0x55ace  ldnull
0x55acf  stloc.3
0x55ad0  ldarg.0
0x55ad1  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.Instance Microsoft.VisualStudio.Setup.Cache.InstanceRepository::GetInstance()
0x55ad6  stloc.s  4
0x55ad8  ldloc.1
0x55ad9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::GetEnumerator()
0x55ade  stloc.s  5
0x55ae0  br       loc_55BEE
0x55ae5  ldloc.s  5
0x55ae7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage>::get_Current()
0x55aec  stloc.s  6
0x55aee  ldloc.s  6
0x55af0  ldloc.2
0x55af1  ldloc.s  6
0x55af3  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>::Contains(var<u1>)
0x55af8  brtrue.s loc_55AFD
0x55afa  ldc.i4.1
0x55afb  br.s     loc_55AFE
0x55afd  ldc.i4.3
0x55afe  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::set_CurrentState(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.CurrentState)
0x55b03  ldloc.s  6
0x55b05  callvirt instance valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageType [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage::get_Type()
0x55b0a  ldc.i4.6
0x55b0b  bne.un   loc_55BEE
0x55b10  ldloc.s  4
0x55b12  ldloc.s  6
0x55b14  ldloca.s 3
0x55b16  ldarg.0
0x55b17  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Cache.InstanceRepository::services
0x55b1c  ldloc.0
0x55b1d  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyCollection [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Deprecate()
0x55b22  call     void Microsoft.VisualStudio.Setup.Cache.Extensions::AddPackageExtensions(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IInstance instance, class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackage package, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference>& extensions, [opt] class [mscorlib]System.IServiceProvider services, [opt] class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyCollection deprecatedPackages)
0x55b27  ldloc.3
0x55b28  brfalse  loc_55BEE
0x55b2d  ldloc.3
0x55b2e  call     T0x2B00005D
0x55b33  brfalse  loc_55BEE
0x55b38  ldloc.2
0x55b39  ldloc.s  6
0x55b3b  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity>::Contains(var<u1>)
0x55b40  brfalse  loc_55BEE
0x55b45  ldarg.0
0x55b46  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.InstanceRepository::logger
0x55b4b  dup
0x55b4c  brtrue.s loc_55B51
0x55b4e  pop
0x55b4f  br.s     loc_55B77
0x55b51  ldstr    aAdded0Extensio// "Added {0} extensions to product '{1}'"
0x55b56  ldloc.3
0x55b57  call     T0x2B000276
0x55b5c  box      [mscorlib]System.Int32
0x55b61  ldloc.s  6
0x55b63  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x55b68  call     string [mscorlib]System.String::Format(string, object, object)
0x55b6d  call     T0x2B000003
0x55b72  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x55b77  ldloc.3
0x55b78  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference>::GetEnumerator()
0x55b7d  stloc.s  7
0x55b7f  br.s     loc_55BD7
0x55b81  ldloc.s  7
0x55b83  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Cache.IPackageReference>::get_Current()
0x55b88  stloc.s  8
0x55b8a  ldarg.0
0x55b8b  ldfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Cache.InstanceRepository::logger
0x55b90  dup
0x55b91  brtrue.s loc_55B96
0x55b93  pop
0x55b94  br.s     loc_55BD7
0x55b96  ldc.i4.5
0x55b97  newarr   [mscorlib]System.String
0x55b9c  dup
0x55b9d  ldc.i4.0
0x55b9e  ldstr    aAddedExtension// "Added extension '"
0x55ba3  stelem.ref
0x55ba4  dup
0x55ba5  ldc.i4.1
0x55ba6  ldloc.s  8
0x55ba8  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x55bad  stelem.ref
0x55bae  dup
0x55baf  ldc.i4.2
0x55bb0  ldstr    aToProduct// "' to product '"
0x55bb5  stelem.ref
0x55bb6  dup
0x55bb7  ldc.i4.3
0x55bb8  ldloc.s  6
0x55bba  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity::GetUniqueId()
0x55bbf  stelem.ref
0x55bc0  dup
0x55bc1  ldc.i4.4
0x55bc2  ldstr    asc_7FEB6// "'"
0x55bc7  stelem.ref
0x55bc8  call     string [mscorlib]System.String::Concat(string[])
0x55bcd  call     T0x2B000003
0x55bd2  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x55bd7  ldloc.s  7
0x55bd9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x55bde  brtrue.s loc_55B81
0x55be0  leave.s  loc_55BEE
0x55be2  ldloc.s  7
0x55be4  brfalse.s loc_55BED
0x55be6  ldloc.s  7
0x55be8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55bed  endfinally
0x55bee  ldloc.s  5
0x55bf0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x55bf5  brtrue   loc_55AE5
0x55bfa  leave.s  loc_55C08
0x55bfc  ldloc.s  5
0x55bfe  brfalse.s loc_55C07
0x55c00  ldloc.s  5
0x55c02  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x55c07  endfinally
0x55c08  ldarg.1
0x55c09  ldloc.0
0x55c0a  callvirt instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.DependencyCollection [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Catalog::get_Deprecate()
0x55c0f  stind.ref
0x55c10  ldloc.1
0x55c11  ret
0x55c12  ldarg.1
0x55c13  ldnull
0x55c14  stind.ref
0x55c15  call     T0x2B00008F
0x55c1a  ret
```
