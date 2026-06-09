# Microsoft.VisualStudio.Setup.DependencyCollection::Add

- ea: `0x43d0`
- end: `0x4419`
- name: `Microsoft.VisualStudio.Setup.DependencyCollection::Add`
- size: `73`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `installer_update, broker_com_uri`

## callers

- `0x44e0`
- `0xe680`

## callees

- `0x4360`
- `0x43d0`
- `0xc1a0`

## string_xrefs

- `0x43f6`: ` was already added.`

## pseudocode

```c

```

## disassembly

```asm
0x43d0  ldarg.1
0x43d1  ldstr    aItem// "item"
0x43d6  call     void Microsoft.VisualStudio.Setup.Validate::IsNotNull(object o, string paramName)
0x43db  ldarg.1
0x43dc  call     string Microsoft.VisualStudio.Setup.DependencyCollection::GetKeyForItem(class Microsoft.VisualStudio.Setup.Dependency item)
0x43e1  stloc.0
0x43e2  ldarg.0
0x43e3  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Dependency> Microsoft.VisualStudio.Setup.DependencyCollection::store
0x43e8  ldloc.0
0x43e9  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Dependency>::ContainsKey(var<u1>)
0x43ee  brfalse.s loc_440B
0x43f0  ldstr    aTheKey// "The key: "
0x43f5  ldloc.0
0x43f6  ldstr    aWasAlreadyAdde// " was already added."
0x43fb  call     string [mscorlib]System.String::Concat(string, string, string)
0x4400  ldstr    aItem// "item"
0x4405  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x440a  throw
0x440b  ldarg.0
0x440c  ldfld    class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Dependency> Microsoft.VisualStudio.Setup.DependencyCollection::store
0x4411  ldloc.0
0x4412  ldarg.1
0x4413  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.VisualStudio.Setup.Dependency>::Add(var<u1>, !!T0)
0x4418  ret
```
