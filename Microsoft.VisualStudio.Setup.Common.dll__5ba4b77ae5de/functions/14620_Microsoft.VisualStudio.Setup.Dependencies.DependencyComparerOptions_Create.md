# Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::Create

- ea: `0x14620`
- end: `0x14649`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::Create`
- size: `41`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x156c0`

## callees

- `0xc1a0`
- `0x14650`
- `0x14690`

## string_xrefs

- `0x1462c`: `stringComparer`

## pseudocode

```c

```

## disassembly

```asm
0x14620  ldarg.1
0x14621  ldstr    aSeed// "seed"
0x14626  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x1462b  ldarg.2
0x1462c  ldstr    aStringcomparer// "stringComparer"
0x14631  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x14636  ldarg.0
0x14637  call     string Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::GetArch(class Microsoft.VisualStudio.Setup.IPackage root)
0x1463c  stloc.0
0x1463d  ldarg.1
0x1463e  ldarg.2
0x1463f  ldloc.0
0x14640  ldarg.3
0x14641  ldarg.s  4
0x14643  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed seed, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> stringComparer, string productArch, valuetype Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels validationLevels, class [mscorlib]System.IServiceProvider services)
0x14648  ret
```
