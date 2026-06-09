# Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor_3

- ea: `0x14220`
- end: `0x142bd`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor_3`
- size: `157`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x141b0`
- `0x141c0`
- `0x14210`

## callees

- `0xc1a0`
- `0x11b00`
- `0x14220`

## string_xrefs

- `0x14232`: `stringComparer`
- `0x1429c`: `{0} was created without a {1}. {1} will be ignored for dependency comparison.`
- `0x142a9`: `DependencyComparer`

## pseudocode

```c

```

## disassembly

```asm
0x14220  ldarg.0
0x14221  call     instance void [mscorlib]System.Object::.ctor()
0x14226  ldarg.1
0x14227  ldstr    aSeed// "seed"
0x1422c  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x14231  ldarg.2
0x14232  ldstr    aStringcomparer// "stringComparer"
0x14237  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1423c  ldarg.0
0x1423d  ldarg.1
0x1423e  stfld    class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::<Seed>k__BackingField
0x14243  ldarg.0
0x14244  ldarg.2
0x14245  stfld    class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::stringComparer
0x1424a  ldarg.0
0x1424b  ldarg.3
0x1424c  stfld    string Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::productArch
0x14251  ldarg.0
0x14252  ldarg.s  5
0x14254  stfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::services
0x14259  ldarg.0
0x1425a  ldarg.s  6
0x1425c  stfld    bool Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::allowIncrementalMajorMatch
0x14261  ldarg.s  4
0x14263  box      Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels
0x14268  ldc.i4.1
0x14269  box      Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels
0x1426e  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x14273  brfalse.s loc_1427C
0x14275  ldarg.0
0x14276  ldc.i4.1
0x14277  stfld    bool Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::strictVersionRanges
0x1427c  ldarg.3
0x1427d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x14282  brfalse.s loc_142BC
0x14284  ldarg.0
0x14285  ldfld    class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::services
0x1428a  dup
0x1428b  brtrue.s loc_14291
0x1428d  pop
0x1428e  ldnull
0x1428f  br.s     loc_14297
0x14291  ldc.i4.0
0x14292  call     T0x2B00003F
0x14297  dup
0x14298  brtrue.s loc_1429C
0x1429a  pop
0x1429b  ret
0x1429c  ldstr    a0WasCreatedWit// "{0} was created without a {1}. {1} will"...
0x142a1  ldc.i4.2
0x142a2  newarr   [mscorlib]System.Object
0x142a7  dup
0x142a8  ldc.i4.0
0x142a9  ldstr    aDependencycomp// "DependencyComparer"
0x142ae  stelem.ref
0x142af  dup
0x142b0  ldc.i4.1
0x142b1  ldstr    aProductarch_2// "productArch"
0x142b6  stelem.ref
0x142b7  callvirt instance void Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string format, object[] args)
0x142bc  ret
```
