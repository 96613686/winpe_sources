# Microsoft.VisualStudio.Setup.Dependencies.DependencyManager::MakeDependencyComparer

- ea: `0x156c0`
- end: `0x156e0`
- name: `Microsoft.VisualStudio.Setup.Dependencies.DependencyManager::MakeDependencyComparer`
- size: `32`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x156f0`
- `0x15710`
- `0x157a0`
- `0x157c0`

## callees

- `0x141c0`
- `0x14620`
- `0x156c0`

## pseudocode

```c

```

## disassembly

```asm
0x156c0  ldarg.0
0x156c1  dup
0x156c2  brtrue.s loc_156CA
0x156c4  pop
0x156c5  ldsfld   class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed Microsoft.VisualStudio.Setup.Dependencies.DependencyComparisonSeed::Default
0x156ca  starg.s  0
0x156cc  ldarg.1
0x156cd  ldarg.0
0x156ce  ldsfld   class [mscorlib]System.StringComparer Microsoft.VisualStudio.Setup.Dependencies.DependencyManager::IdentityStringComparer
0x156d3  ldarg.3
0x156d4  ldarg.2
0x156d5  call     class Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions::Create(class Microsoft.VisualStudio.Setup.IPackage root, class Microsoft.VisualStudio.Setup.Dependencies.IDependencyComparisonSeed seed, class [mscorlib]System.Collections.Generic.IEqualityComparer`1<string> stringComparer, [opt] valuetype Microsoft.VisualStudio.Setup.Dependencies.DependencyValidationLevels validationLevels, [opt] class [mscorlib]System.IServiceProvider services)
0x156da  newobj   instance void Microsoft.VisualStudio.Setup.Dependencies.DependencyComparer::.ctor(class Microsoft.VisualStudio.Setup.Dependencies.DependencyComparerOptions options)
0x156df  ret
```
