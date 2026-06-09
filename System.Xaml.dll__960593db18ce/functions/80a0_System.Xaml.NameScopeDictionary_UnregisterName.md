# System.Xaml.NameScopeDictionary::UnregisterName

- ea: `0x80a0`
- end: `0x812a`
- name: `System.Xaml.NameScopeDictionary::UnregisterName`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x80a0`
- `0x11f20`
- `0x11f50`
- `0x1b520`

## string_xrefs

- `0x80bb`: `NameScopeNameNotEmptyString`
- `0x8110`: `NameScopeNameNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x80a0  ldarg.1
0x80a1  brtrue.s loc_80AE
0x80a3  ldstr    aName// "name"
0x80a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x80ad  throw
0x80ae  ldarg.1
0x80af  ldsfld   string [mscorlib]System.String::Empty
0x80b4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x80b9  brfalse.s loc_80CB
0x80bb  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0x80c0  call     string System.Xaml.SR::Get(string id)
0x80c5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x80ca  throw
0x80cb  ldarg.0
0x80cc  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x80d1  brfalse.s loc_80ED
0x80d3  ldarg.0
0x80d4  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x80d9  ldarg.1
0x80da  callvirt instance void System.Windows.Markup.INameScope::UnregisterName(string name)
0x80df  ldarg.0
0x80e0  ldfld    class System.Xaml.MS.Impl.FrugalObjectList`1<string> System.Xaml.NameScopeDictionary::_names
0x80e5  ldarg.1
0x80e6  callvirt instance bool class System.Xaml.MS.Impl.FrugalObjectList`1<string>::Remove(var<u1>)
0x80eb  pop
0x80ec  ret
0x80ed  ldarg.0
0x80ee  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x80f3  brfalse.s loc_8110
0x80f5  ldarg.0
0x80f6  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x80fb  ldarg.1
0x80fc  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x8101  brfalse.s loc_8110
0x8103  ldarg.0
0x8104  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8109  ldarg.1
0x810a  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Remove(object)
0x810f  ret
0x8110  ldstr    aNamescopenamen_0// "NameScopeNameNotFound"
0x8115  ldc.i4.1
0x8116  newarr   [mscorlib]System.Object
0x811b  dup
0x811c  ldc.i4.0
0x811d  ldarg.1
0x811e  stelem.ref
0x811f  call     string System.Xaml.SR::Get(string id, object[] args)
0x8124  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x8129  throw
```
