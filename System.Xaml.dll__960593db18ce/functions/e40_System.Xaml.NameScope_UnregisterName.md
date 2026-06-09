# System.Xaml.NameScope::UnregisterName

- ea: `0xe40`
- end: `0xea8`
- name: `System.Xaml.NameScope::UnregisterName`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1140`

## callees

- `0xe40`
- `0x11f20`
- `0x11f50`

## string_xrefs

- `0xe5b`: `NameScopeNameNotEmptyString`
- `0xe8e`: `NameScopeNameNotFound`

## pseudocode

```c

```

## disassembly

```asm
0xe40  ldarg.1
0xe41  brtrue.s loc_E4E
0xe43  ldstr    aName// "name"
0xe48  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xe4d  throw
0xe4e  ldarg.1
0xe4f  ldsfld   string [mscorlib]System.String::Empty
0xe54  call     bool [mscorlib]System.String::op_Equality(string, string)
0xe59  brfalse.s loc_E6B
0xe5b  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0xe60  call     string System.Xaml.SR::Get(string id)
0xe65  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe6a  throw
0xe6b  ldarg.0
0xe6c  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xe71  brfalse.s loc_E8E
0xe73  ldarg.0
0xe74  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xe79  ldarg.1
0xe7a  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0xe7f  brfalse.s loc_E8E
0xe81  ldarg.0
0xe82  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xe87  ldarg.1
0xe88  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Remove(object)
0xe8d  ret
0xe8e  ldstr    aNamescopenamen_0// "NameScopeNameNotFound"
0xe93  ldc.i4.1
0xe94  newarr   [mscorlib]System.Object
0xe99  dup
0xe9a  ldc.i4.0
0xe9b  ldarg.1
0xe9c  stelem.ref
0xe9d  call     string System.Xaml.SR::Get(string id, object[] args)
0xea2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xea7  throw
```
