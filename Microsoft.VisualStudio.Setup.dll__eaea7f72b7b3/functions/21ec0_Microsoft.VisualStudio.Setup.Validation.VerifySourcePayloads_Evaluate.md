# Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::Evaluate

- ea: `0x21ec0`
- end: `0x220bc`
- name: `Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::Evaluate`
- size: `508`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callees

- `0x199a0`
- `0x21b80`
- `0x21c50`
- `0x21ce0`
- `0x21d00`
- `0x21ec0`
- `0x220c0`

## string_xrefs

- `0x21ff5`: `Precheck_MissingOrInvalidInstallingPackagesInLayoutCaches_Args1`
- `0x21f5a`: `Precheck_MissingOrInvalidUninstallingAndInstallingPackagesInAllCaches_Args2`
- `0x2205e`: `Precheck_MissingOrInvalidUninstallingPackagesInPackageCaches_Args1`

## pseudocode

```c

```

## disassembly

```asm
0x21ec0  ldarg.0
0x21ec1  ldfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::downloadingPackages
0x21ec6  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Count()
0x21ecb  ldc.i4.0
0x21ecc  ble      loc_220BA
0x21ed1  ldarg.0
0x21ed2  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::services
0x21ed7  ldc.i4.0
0x21ed8  call     T0x2B000001
0x21edd  dup
0x21ede  brtrue.s loc_21EE3
0x21ee0  pop
0x21ee1  br.s     loc_21F07
0x21ee3  ldstr    aPrecheck0Downl// "Precheck {0} downloading packages."
0x21ee8  ldarg.0
0x21ee9  ldfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::downloadingPackages
0x21eee  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage>::get_Count()
0x21ef3  box      [mscorlib]System.Int32
0x21ef8  call     string [mscorlib]System.String::Format(string, object)
0x21efd  call     T0x2B000003
0x21f02  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteMessage(string, object[])
0x21f07  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage>::.ctor()
0x21f0c  stloc.0
0x21f0d  ldarg.0
0x21f0e  ldarg.0
0x21f0f  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::services
0x21f14  ldarg.0
0x21f15  ldfld    class [System]System.Collections.Generic.ISet`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::downloadingPackages
0x21f1a  ldloc.0
0x21f1b  call     instance void Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::IdentifyMissingOrInvalidPackagesInLayout(class [mscorlib]System.IServiceProvider services, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> packagesToVerify, class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> missingOrInvalidPackages)
0x21f20  ldarg.0
0x21f21  ldfld    class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IInstallablePackage> Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::uninstallingPackages
0x21f26  ldloc.0
0x21f27  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x21f2c  call     T0x2B00012E
0x21f31  stloc.1
0x21f32  ldloc.0
0x21f33  ldloc.1
0x21f34  ldsfld   class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.PackageIdentityComparer::Default
0x21f39  call     T0x2B000047
0x21f3e  stloc.2
0x21f3f  ldloc.2
0x21f40  call     T0x2B0000A3
0x21f45  brfalse  loc_21FE8
0x21f4a  ldloc.1
0x21f4b  call     T0x2B0000A3
0x21f50  brfalse  loc_21FE8
0x21f55  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x21f5a  ldstr    aPrecheckMissin_1// "Precheck_MissingOrInvalidUninstallingAn"...
0x21f5f  ldc.i4.2
0x21f60  newarr   [mscorlib]System.Object
0x21f65  dup
0x21f66  ldc.i4.0
0x21f67  ldstr    asc_853DA// " "
0x21f6c  ldloc.1
0x21f6d  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_0
0x21f72  dup
0x21f73  brtrue.s loc_21F8C
0x21f75  pop
0x21f76  ldsfld   class <>c <>c::<>9
0x21f7b  ldftn    instance string <>c::<Evaluate>b__10_0(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity n)
0x21f81  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string>::.ctor(object, native int)
0x21f86  dup
0x21f87  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_0
0x21f8c  call     T0x2B0000A4
0x21f91  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x21f96  stelem.ref
0x21f97  dup
0x21f98  ldc.i4.1
0x21f99  ldstr    asc_853DA// " "
0x21f9e  ldloc.2
0x21f9f  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_1
0x21fa4  dup
0x21fa5  brtrue.s loc_21FBE
0x21fa7  pop
0x21fa8  ldsfld   class <>c <>c::<>9
0x21fad  ldftn    instance string <>c::<Evaluate>b__10_1(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity n)
0x21fb3  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string>::.ctor(object, native int)
0x21fb8  dup
0x21fb9  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_1
0x21fbe  call     T0x2B0000A4
0x21fc3  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x21fc8  stelem.ref
0x21fc9  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x21fce  dup
0x21fcf  ldc.i4.1
0x21fd0  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_SupportsRetry(bool value)
0x21fd5  dup
0x21fd6  ldc.i4.0
0x21fd7  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x21fdc  dup
0x21fdd  ldsfld   int32 Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::ErrorCode
0x21fe2  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x21fe7  ret
0x21fe8  ldloc.2
0x21fe9  call     T0x2B0000A3
0x21fee  brfalse.s loc_22051
0x21ff0  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x21ff5  ldstr    aPrecheckMissin_0// "Precheck_MissingOrInvalidInstallingPack"...
0x21ffa  ldc.i4.1
0x21ffb  newarr   [mscorlib]System.Object
0x22000  dup
0x22001  ldc.i4.0
0x22002  ldstr    asc_853DA// " "
0x22007  ldloc.2
0x22008  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_2
0x2200d  dup
0x2200e  brtrue.s loc_22027
0x22010  pop
0x22011  ldsfld   class <>c <>c::<>9
0x22016  ldftn    instance string <>c::<Evaluate>b__10_2(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity n)
0x2201c  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string>::.ctor(object, native int)
0x22021  dup
0x22022  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_2
0x22027  call     T0x2B0000A4
0x2202c  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x22031  stelem.ref
0x22032  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x22037  dup
0x22038  ldc.i4.1
0x22039  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_SupportsRetry(bool value)
0x2203e  dup
0x2203f  ldc.i4.0
0x22040  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x22045  dup
0x22046  ldsfld   int32 Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::ErrorCode
0x2204b  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x22050  ret
0x22051  ldloc.1
0x22052  call     T0x2B0000A3
0x22057  brfalse.s loc_220BA
0x22059  call     class [mscorlib]System.Resources.ResourceManager Microsoft.VisualStudio.Setup.Resources::get_ResourceManager()
0x2205e  ldstr    aPrecheckMissin_2// "Precheck_MissingOrInvalidUninstallingPa"...
0x22063  ldc.i4.1
0x22064  newarr   [mscorlib]System.Object
0x22069  dup
0x2206a  ldc.i4.0
0x2206b  ldstr    asc_853DA// " "
0x22070  ldloc.1
0x22071  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_3
0x22076  dup
0x22077  brtrue.s loc_22090
0x22079  pop
0x2207a  ldsfld   class <>c <>c::<>9
0x2207f  ldftn    instance string <>c::<Evaluate>b__10_3(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity n)
0x22085  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string>::.ctor(object, native int)
0x2208a  dup
0x2208b  stsfld   class [mscorlib]System.Func`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.IPackageIdentity, string> <>c::<>9__10_3
0x22090  call     T0x2B0000A4
0x22095  call     string [mscorlib]System.String::Join(string, class [mscorlib]System.Collections.Generic.IEnumerable`1<string>)
0x2209a  stelem.ref
0x2209b  newobj   instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::.ctor(class [mscorlib]System.Resources.ResourceManager resourceManager, string resourceId, object[] args)
0x220a0  dup
0x220a1  ldc.i4.1
0x220a2  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_SupportsRetry(bool value)
0x220a7  dup
0x220a8  ldc.i4.0
0x220a9  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_IsWarning(bool value)
0x220ae  dup
0x220af  ldsfld   int32 Microsoft.VisualStudio.Setup.Validation.VerifySourcePayloads::ErrorCode
0x220b4  callvirt instance void Microsoft.VisualStudio.Setup.Validation.ValidationResult::set_ErrorCode(int32 value)
0x220b9  ret
0x220ba  ldnull
0x220bb  ret
```
