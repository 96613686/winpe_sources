# System.Xaml.NameScopeDictionary::RegisterName

- ea: `0x7fc0`
- end: `0x809c`
- name: `System.Xaml.NameScopeDictionary::RegisterName`
- size: `220`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1250`
- `0x7fc0`
- `0x11f20`
- `0x11f50`
- `0x1b510`

## string_xrefs

- `0x7fe9`: `NameScopeNameNotEmptyString`

## pseudocode

```c

```

## disassembly

```asm
0x7fc0  ldarg.1
0x7fc1  brtrue.s loc_7FCE
0x7fc3  ldstr    aName// "name"
0x7fc8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fcd  throw
0x7fce  ldarg.2
0x7fcf  brtrue.s loc_7FDC
0x7fd1  ldstr    aScopedelement// "scopedElement"
0x7fd6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x7fdb  throw
0x7fdc  ldarg.1
0x7fdd  ldsfld   string [mscorlib]System.String::Empty
0x7fe2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7fe7  brfalse.s loc_7FF9
0x7fe9  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0x7fee  call     string System.Xaml.SR::Get(string id)
0x7ff3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x7ff8  throw
0x7ff9  ldarg.1
0x7ffa  call     bool System.Xaml.NameValidationHelper::IsValidIdentifierName(string name)
0x7fff  brtrue.s loc_801B
0x8001  ldstr    aNamescopeinval// "NameScopeInvalidIdentifierName"
0x8006  ldc.i4.1
0x8007  newarr   [mscorlib]System.Object
0x800c  dup
0x800d  ldc.i4.0
0x800e  ldarg.1
0x800f  stelem.ref
0x8010  call     string System.Xaml.SR::Get(string id, object[] args)
0x8015  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x801a  throw
0x801b  ldarg.0
0x801c  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x8021  brfalse.s loc_803E
0x8023  ldarg.0
0x8024  ldfld    class System.Xaml.MS.Impl.FrugalObjectList`1<string> System.Xaml.NameScopeDictionary::_names
0x8029  ldarg.1
0x802a  callvirt instance int32 class System.Xaml.MS.Impl.FrugalObjectList`1<string>::Add(var<u1>)
0x802f  pop
0x8030  ldarg.0
0x8031  ldfld    class System.Windows.Markup.INameScope System.Xaml.NameScopeDictionary::_underlyingNameScope
0x8036  ldarg.1
0x8037  ldarg.2
0x8038  callvirt instance void System.Windows.Markup.INameScope::RegisterName(string name, object scopedElement)
0x803d  ret
0x803e  ldarg.0
0x803f  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8044  brtrue.s loc_805F
0x8046  ldarg.0
0x8047  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x804c  stfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8051  ldarg.0
0x8052  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8057  ldarg.1
0x8058  ldarg.2
0x8059  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x805e  ret
0x805f  ldarg.0
0x8060  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8065  ldarg.1
0x8066  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x806b  stloc.0
0x806c  ldloc.0
0x806d  brtrue.s loc_807D
0x806f  ldarg.0
0x8070  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScopeDictionary::_nameMap
0x8075  ldarg.1
0x8076  ldarg.2
0x8077  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x807c  ret
0x807d  ldarg.2
0x807e  ldloc.0
0x807f  beq.s    loc_809B
0x8081  ldstr    aNamescopedupli// "NameScopeDuplicateNamesNotAllowed"
0x8086  ldc.i4.1
0x8087  newarr   [mscorlib]System.Object
0x808c  dup
0x808d  ldc.i4.0
0x808e  ldarg.1
0x808f  stelem.ref
0x8090  call     string System.Xaml.SR::Get(string id, object[] args)
0x8095  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x809a  throw
0x809b  ret
```
