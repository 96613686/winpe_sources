# Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::PackageSatisfiesDependency_0

- ea: `0x142e0`
- end: `0x145dd`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::PackageSatisfiesDependency_0`
- size: `765`
- prototype: ``
- caller_count: `2`
- callee_count: `26`
- tags: `installer_update, broker_com_uri`

## callers

- `0x142d0`
- `0x15e80`

## callees

- `0x5950`
- `0x6640`
- `0x8140`
- `0x8150`
- `0x8160`
- `0x8170`
- `0x8180`
- `0x8190`
- `0x81e0`
- `0x81f0`
- `0x8200`
- `0x8210`
- `0x8220`
- `0x8230`
- `0x8240`
- `0xc1a0`
- `0xc6d0`
- `0x10900`
- `0x142c0`
- `0x142e0`
- `0x145e0`
- `0x164f0`
- `0x16500`
- `0x16510`
- `0x16520`
- `0x1d080`

## pseudocode

```c

```

## disassembly

```asm
0x142e0  newobj   instance void <>c__DisplayClass14_0::.ctor()
0x142e5  stloc.0
0x142e6  ldloc.0
0x142e7  ldarg.0
0x142e8  stfld    class Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer <>c__DisplayClass14_0::<>4__this
0x142ed  ldarg.1
0x142ee  ldstr    aTargetpackage// "targetPackage"
0x142f3  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x142f8  ldarg.2
0x142f9  ldstr    aDependency_0// "dependency"
0x142fe  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x14303  ldc.i4.0
0x14304  stloc.1
0x14305  ldarg.0
0x14306  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x1430b  ldarg.1
0x1430c  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x14311  ldarg.2
0x14312  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Id()
0x14317  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x1431c  brtrue.s loc_14320
0x1431e  ldc.i4.0
0x1431f  ret
0x14320  ldarg.0
0x14321  ldfld    bool Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::strictVersionRanges
0x14326  brtrue.s loc_14333
0x14328  ldarg.3
0x14329  brfalse.s loc_14333
0x1432b  ldarg.3
0x1432c  call     bool Microsoft.VisualStudio.Setup.Extensions::IsExternal(class Microsoft.VisualStudio.Setup.IPackage package)
0x14331  brfalse.s loc_14372
0x14333  ldarg.2
0x14334  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.IPackageDependency::get_Version()
0x14339  brfalse.s loc_14372
0x1433b  ldarg.2
0x1433c  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.IPackageDependency::get_Version()
0x14341  ldarg.1
0x14342  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x14347  callvirt instance bool Microsoft.VisualStudio.Setup.VersionRange::Contains(class [mscorlib]System.Version value)
0x1434c  brtrue.s loc_14372
0x1434e  ldarg.0
0x1434f  ldfld    bool Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::allowIncrementalMajorMatch
0x14354  brfalse.s loc_14370
0x14356  ldarg.2
0x14357  callvirt instance class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.IPackageDependency::get_Version()
0x1435c  call     class Microsoft.VisualStudio.Setup.VersionRange Microsoft.VisualStudio.Setup.Extensions::AdjustVersionRangeForPriorTarget(class Microsoft.VisualStudio.Setup.VersionRange versionRange)
0x14361  ldarg.1
0x14362  callvirt instance class [mscorlib]System.Version Microsoft.VisualStudio.Setup.IPackageIdentity::get_Version()
0x14367  callvirt instance bool Microsoft.VisualStudio.Setup.VersionRange::Contains(class [mscorlib]System.Version value)
0x1436c  brtrue.s loc_14372
0x1436e  ldc.i4.0
0x1436f  ret
0x14370  ldc.i4.0
0x14371  ret
0x14372  ldarg.1
0x14373  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Chip()
0x14378  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x1437d  stloc.2
0x1437e  ldarg.2
0x1437f  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Chip()
0x14384  brfalse.s loc_1439C
0x14386  ldarg.0
0x14387  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x1438c  ldloc.2
0x1438d  ldarg.2
0x1438e  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Chip()
0x14393  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x14398  brtrue.s loc_143C7
0x1439a  ldc.i4.0
0x1439b  ret
0x1439c  ldloc.2
0x1439d  brfalse.s loc_143C7
0x1439f  ldarg.0
0x143a0  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x143a5  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Chip()
0x143aa  brfalse.s loc_143C7
0x143ac  ldarg.0
0x143ad  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x143b2  ldloc.2
0x143b3  ldarg.0
0x143b4  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x143b9  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Chip()
0x143be  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x143c3  brtrue.s loc_143C7
0x143c5  ldc.i4.1
0x143c6  stloc.1
0x143c7  ldarg.1
0x143c8  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_ProductArch()
0x143cd  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x143d2  stloc.3
0x143d3  ldloc.3
0x143d4  brfalse.s loc_143F4
0x143d6  ldarg.0
0x143d7  ldfld    string Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::productArch
0x143dc  brfalse.s loc_143F4
0x143de  ldarg.0
0x143df  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x143e4  ldloc.3
0x143e5  ldarg.0
0x143e6  ldfld    string Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::productArch
0x143eb  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x143f0  brtrue.s loc_143F4
0x143f2  ldc.i4.1
0x143f3  stloc.1
0x143f4  ldarg.1
0x143f5  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_MachineArch()
0x143fa  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x143ff  stloc.s  4
0x14401  ldarg.2
0x14402  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_MachineArch()
0x14407  brfalse.s loc_14420
0x14409  ldarg.0
0x1440a  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x1440f  ldloc.s  4
0x14411  ldarg.2
0x14412  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_MachineArch()
0x14417  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x1441c  brtrue.s loc_1444D
0x1441e  ldc.i4.0
0x1441f  ret
0x14420  ldloc.s  4
0x14422  brfalse.s loc_1444D
0x14424  ldarg.0
0x14425  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x1442a  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_MachineArch()
0x1442f  brfalse.s loc_1444D
0x14431  ldarg.0
0x14432  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x14437  ldloc.s  4
0x14439  ldarg.0
0x1443a  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x1443f  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_MachineArch()
0x14444  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x14449  brtrue.s loc_1444D
0x1444b  ldc.i4.1
0x1444c  stloc.1
0x1444d  ldloc.0
0x1444e  ldarg.1
0x1444f  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Language()
0x14454  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x14459  stfld    string <>c__DisplayClass14_0::packageMappedLang
0x1445e  ldloc.0
0x1445f  ldfld    string <>c__DisplayClass14_0::packageMappedLang
0x14464  brfalse.s loc_144D0
0x14466  ldarg.2
0x14467  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Language()
0x1446c  brfalse.s loc_1448C
0x1446e  ldarg.0
0x1446f  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x14474  ldloc.0
0x14475  ldfld    string <>c__DisplayClass14_0::packageMappedLang
0x1447a  ldarg.2
0x1447b  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Language()
0x14480  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x14485  brtrue   loc_14524
0x1448a  ldc.i4.0
0x1448b  ret
0x1448c  ldarg.0
0x1448d  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x14492  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Languages()
0x14497  brfalse  loc_14524
0x1449c  ldarg.0
0x1449d  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x144a2  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Languages()
0x144a7  call     T0x2B00000D
0x144ac  brfalse.s loc_14524
0x144ae  ldarg.0
0x144af  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x144b4  callvirt instance class [System]System.Collections.Generic.ISet`1<string> Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Languages()
0x144b9  ldloc.0
0x144ba  ldftn    instance bool <>c__DisplayClass14_0::<PackageSatisfiesDependency>b__0(string language)
0x144c0  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x144c5  call     T0x2B00007D
0x144ca  brtrue.s loc_14524
0x144cc  ldc.i4.1
0x144cd  stloc.1
0x144ce  br.s     loc_14524
0x144d0  ldarg.2
0x144d1  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Language()
0x144d6  brfalse.s loc_14524
0x144d8  ldarg.0
0x144d9  ldc.i4.7
0x144da  newarr   [mscorlib]System.String
0x144df  dup
0x144e0  ldc.i4.0
0x144e1  ldstr    aDependency_1// "Dependency "
0x144e6  stelem.ref
0x144e7  dup
0x144e8  ldc.i4.1
0x144e9  ldarg.2
0x144ea  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Id()
0x144ef  stelem.ref
0x144f0  dup
0x144f1  ldc.i4.2
0x144f2  ldstr    aDeclaresLangua// " declares Language="
0x144f7  stelem.ref
0x144f8  dup
0x144f9  ldc.i4.3
0x144fa  ldarg.2
0x144fb  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Language()
0x14500  stelem.ref
0x14501  dup
0x14502  ldc.i4.4
0x14503  ldstr    aButPackage// ", but package "
0x14508  stelem.ref
0x14509  dup
0x1450a  ldc.i4.5
0x1450b  ldarg.1
0x1450c  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x14511  stelem.ref
0x14512  dup
0x14513  ldc.i4.6
0x14514  ldstr    aDoesnTDeclareA// " doesn't declare a language"
0x14519  stelem.ref
0x1451a  call     string [mscorlib]System.String::Concat(string[])
0x1451f  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::LogDependencyWarning(string message)
0x14524  ldarg.1
0x14525  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Branch()
0x1452a  call     string Microsoft.VisualStudio.Setup.Serialization.TokenMapper::MapMatchAnythingToken(string value)
0x1452f  stloc.s  5
0x14531  ldloc.s  5
0x14533  brfalse.s loc_14582
0x14535  ldarg.2
0x14536  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Branch()
0x1453b  brfalse.s loc_14557
0x1453d  ldarg.0
0x1453e  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x14543  ldloc.s  5
0x14545  ldarg.2
0x14546  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Branch()
0x1454b  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x14550  brtrue   loc_145D6
0x14555  ldc.i4.0
0x14556  ret
0x14557  ldarg.0
0x14558  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x1455d  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Branch()
0x14562  brfalse.s loc_145D6
0x14564  ldarg.0
0x14565  ldfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x1456a  ldloc.s  5
0x1456c  ldarg.0
0x1456d  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::get_Seed()
0x14572  callvirt instance string Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed::get_Branch()
0x14577  callvirt instance bool class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x1457c  brtrue.s loc_145D6
0x1457e  ldc.i4.1
0x1457f  stloc.1
0x14580  br.s     loc_145D6
0x14582  ldarg.2
0x14583  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Branch()
0x14588  brfalse.s loc_145D6
0x1458a  ldarg.0
0x1458b  ldc.i4.7
0x1458c  newarr   [mscorlib]System.String
0x14591  dup
0x14592  ldc.i4.0
0x14593  ldstr    aDependency_1// "Dependency "
0x14598  stelem.ref
0x14599  dup
0x1459a  ldc.i4.1
0x1459b  ldarg.2
0x1459c  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Id()
0x145a1  stelem.ref
0x145a2  dup
0x145a3  ldc.i4.2
0x145a4  ldstr    aDeclaresBranch// " declares Branch="
0x145a9  stelem.ref
0x145aa  dup
0x145ab  ldc.i4.3
0x145ac  ldarg.2
0x145ad  callvirt instance string Microsoft.VisualStudio.Setup.IPackageDependency::get_Branch()
0x145b2  stelem.ref
0x145b3  dup
0x145b4  ldc.i4.4
0x145b5  ldstr    aButPackage// ", but package "
0x145ba  stelem.ref
0x145bb  dup
0x145bc  ldc.i4.5
0x145bd  ldarg.1
0x145be  callvirt instance string Microsoft.VisualStudio.Setup.IPackageIdentity::get_Id()
0x145c3  stelem.ref
0x145c4  dup
0x145c5  ldc.i4.6
0x145c6  ldstr    aDoesnTDeclareA_0// " doesn't declare a branch"
0x145cb  stelem.ref
0x145cc  call     string [mscorlib]System.String::Concat(string[])
0x145d1  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::LogDependencyWarning(string message)
0x145d6  ldloc.1
0x145d7  brtrue.s loc_145DB
0x145d9  ldc.i4.2
0x145da  ret
0x145db  ldc.i4.1
0x145dc  ret
```
