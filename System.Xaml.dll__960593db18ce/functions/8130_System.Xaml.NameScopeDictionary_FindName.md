# System.Xaml.NameScopeDictionary::FindName

- ea: `0x8130`
- end: `0x8187`
- name: `System.Xaml.NameScopeDictionary::FindName`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x8130`
- `0x11f20`
- `0x1b530`

## string_xrefs

- `0x814b`: `NameScopeNameNotEmptyString`

## pseudocode

```c

```

## disassembly

```asm
0x8130  ldarg.1
0x8131  brtrue.s loc_813E
0x8133  ldstr    aName// "name"
0x8138  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x813d  throw
0x813e  ldarg.1
0x813f  ldsfld   string [mscorlib]System.String::Empty
0x8144  call     bool [mscorlib]System.String::op_Equality(string, string)
0x8149  brfalse.s loc_815B
0x814b  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0x8150  call     string System.Xaml.SR::Get(string id)
0x8155  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x815a  throw
0x815b  ldarg.0
0x815c  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x8161  brfalse.s loc_8170
0x8163  ldarg.0
0x8164  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x8169  ldarg.1
0x816a  callvirt instance object System.Windows.Markup.INameScope::FindName(string name)
0x816f  ret
0x8170  ldarg.0
0x8171  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8176  brtrue.s loc_817A
0x8178  ldnull
0x8179  ret
0x817a  ldarg.0
0x817b  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8180  ldarg.1
0x8181  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x8186  ret
```
