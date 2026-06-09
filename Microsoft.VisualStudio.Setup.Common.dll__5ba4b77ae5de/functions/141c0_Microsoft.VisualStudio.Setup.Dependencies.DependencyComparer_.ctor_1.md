# Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor_1

- ea: `0x141c0`
- end: `0x14204`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor_1`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x156c0`

## callees

- `0x141c0`
- `0x14220`
- `0x146c0`
- `0x146d0`
- `0x146e0`
- `0x146f0`
- `0x14700`

## pseudocode

```c

```

## disassembly

```asm
0x141c0  ldarg.0
0x141c1  ldarg.1
0x141c2  brtrue.s loc_141C7
0x141c4  ldnull
0x141c5  br.s     loc_141CD
0x141c7  ldarg.1
0x141c8  call     instance class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::get_Seed()
0x141cd  ldarg.1
0x141ce  brtrue.s loc_141D3
0x141d0  ldnull
0x141d1  br.s     loc_141D9
0x141d3  ldarg.1
0x141d4  call     instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::get_StringComparer()
0x141d9  ldarg.1
0x141da  brtrue.s loc_141DF
0x141dc  ldnull
0x141dd  br.s     loc_141E5
0x141df  ldarg.1
0x141e0  call     instance string Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::get_ProductArch()
0x141e5  ldarg.1
0x141e6  brtrue.s loc_141EB
0x141e8  ldc.i4.0
0x141e9  br.s     loc_141F1
0x141eb  ldarg.1
0x141ec  call     instance valuetype Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::get_ValidationLevels()
0x141f1  ldarg.1
0x141f2  brtrue.s loc_141F7
0x141f4  ldnull
0x141f5  br.s     loc_141FD
0x141f7  ldarg.1
0x141f8  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::get_Services()
0x141fd  ldc.i4.0
0x141fe  call     instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed seed, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> stringComparer, string productArch, valuetype Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels validationLevels, [opt] class [mscorlib]System.IServiceProvider services, [opt] bool allowIncrementalMajorMatch)
0x14203  ret
```
