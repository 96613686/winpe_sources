# Microsoft.VisualStudio.Setup.DependencyCollection::AddExtensions

- ea: `0x44e0`
- end: `0x45ad`
- name: `Microsoft.VisualStudio.Setup.DependencyCollection::AddExtensions`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x158c0`

## callees

- `0x4140`
- `0x4170`
- `0x4190`
- `0x41b0`
- `0x41d0`
- `0x41f0`
- `0x4210`
- `0x4230`
- `0x4290`
- `0x43d0`
- `0x44e0`
- `0x4600`
- `0x6160`
- `0x81e0`
- `0x81f0`
- `0x8200`
- `0x8210`
- `0x8220`
- `0x8240`
- `0xc1a0`
- `0xc410`
- `0x15680`
- `0x157c0`

## string_xrefs

- `0x44e1`: `extensions`

## pseudocode

```c

```

## disassembly

```asm
0x44e0  ldarg.1
0x44e1  ldstr    aExtensions// "extensions"
0x44e6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x44eb  ldarg.1
0x44ec  call     T0x2B00000F
0x44f1  brtrue.s loc_44F4
0x44f3  ret
0x44f4  ldarg.2
0x44f5  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyManager::.ctor([opt] class [mscorlib]System.IServiceProvider services)
0x44fa  ldarg.1
0x44fb  ldarg.3
0x44fc  ldarg.s  4
0x44fe  ldnull
0x44ff  callvirt instance class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackageIdentity> Microsoft.VisualStudio.Setup.Dependencies.DependencyManager::GetDeprecatedPackages(class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackageIdentity> packages, class Microsoft.VisualStudio.Setup.DependencyCollection deprecated, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed seed, [opt] class [mscorlib]System.Collections.Generic.IEqualityComparer`1<class Microsoft.VisualStudio.Setup.IPackageIdentity> packageComparer)
0x4504  stloc.0
0x4505  ldarg.1
0x4506  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.VisualStudio.Setup.IPackageIdentity>::GetEnumerator()
0x450b  stloc.1
0x450c  br       loc_4595
0x4511  ldloc.1
0x4512  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.VisualStudio.Setup.IPackageIdentity>::get_Current()
0x4517  stloc.2
0x4518  ldarg.0
0x4519  ldloc.2
0x451a  call     instance bool Microsoft.VisualStudio.Setup.DependencyCollection::Contains(class Microsoft.VisualStudio.Setup.IPackageIdentity package)
0x451f  brtrue.s loc_4595
0x4521  ldloc.0
0x4522  ldloc.2
0x4523  call     bool Microsoft.VisualStudio.Setup.Extensions::DoesNotContain(class [System]System.Collections.Generic.ISet`1<class Microsoft.VisualStudio.Setup.IPackageIdentity> set, class Microsoft.VisualStudio.Setup.IPackageIdentity package)
0x4528  brfalse.s loc_4595
0x452a  newobj   instance void Microsoft.VisualStudio.Setup.Dependency::.ctor()
0x452f  dup
0x4530  ldloc.2
0x4531  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x4536  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Id(string value)
0x453b  dup
0x453c  ldloc.2
0x453d  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x4542  ldc.i4.1
0x4543  ldnull
0x4544  ldc.i4.0
0x4545  newobj   instance void Microsoft.VisualStudio.Setup.VersionRange::.ctor(class [mscorlib]System.Version minimum, bool isMinimumInclusive, class [mscorlib]System.Version maximum, bool isMaximumInclusive)
0x454a  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Version(class Microsoft.VisualStudio.Setup.VersionRange value)
0x454f  dup
0x4550  ldloc.2
0x4551  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0x4556  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Chip(string value)
0x455b  dup
0x455c  ldloc.2
0x455d  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0x4562  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Language(string value)
0x4567  dup
0x4568  ldloc.2
0x4569  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0x456e  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Branch(string value)
0x4573  dup
0x4574  ldloc.2
0x4575  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0x457a  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_MachineArch(string value)
0x457f  dup
0x4580  ldc.i4.1
0x4581  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_IsExtension(bool value)
0x4586  dup
0x4587  ldc.i4.2
0x4588  callvirt instance void Microsoft.VisualStudio.Setup.Dependency::set_Type(valuetype Microsoft.VisualStudio.Setup.DependencyType value)
0x458d  stloc.3
0x458e  ldarg.0
0x458f  ldloc.3
0x4590  call     instance void Microsoft.VisualStudio.Setup.DependencyCollection::Add(class Microsoft.VisualStudio.Setup.Dependency item)
0x4595  ldloc.1
0x4596  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x459b  brtrue   loc_4511
0x45a0  leave.s  loc_45AC
0x45a2  ldloc.1
0x45a3  brfalse.s loc_45AB
0x45a5  ldloc.1
0x45a6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45ab  endfinally
0x45ac  ret
```
