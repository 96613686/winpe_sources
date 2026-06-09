# System.Xaml.NameScope::RegisterName

- ea: `0xd80`
- end: `0xe39`
- name: `System.Xaml.NameScope::RegisterName`
- size: `185`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x10d0`
- `0x1100`

## callees

- `0xd80`
- `0x1250`
- `0x11f20`
- `0x11f50`

## string_xrefs

- `0xda9`: `NameScopeNameNotEmptyString`

## pseudocode

```c

```

## disassembly

```asm
0xd80  ldarg.1
0xd81  brtrue.s loc_D8E
0xd83  ldstr    aName// "name"
0xd88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd8d  throw
0xd8e  ldarg.2
0xd8f  brtrue.s loc_D9C
0xd91  ldstr    aScopedelement// "scopedElement"
0xd96  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xd9b  throw
0xd9c  ldarg.1
0xd9d  ldsfld   string [mscorlib]System.String::Empty
0xda2  call     bool [mscorlib]System.String::op_Equality(string, string)
0xda7  brfalse.s loc_DB9
0xda9  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0xdae  call     string System.Xaml.SR::Get(string id)
0xdb3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xdb8  throw
0xdb9  ldarg.1
0xdba  call     bool System.Xaml.NameValidationHelper::IsValidIdentifierName(string name)
0xdbf  brtrue.s loc_DDB
0xdc1  ldstr    aNamescopeinval// "NameScopeInvalidIdentifierName"
0xdc6  ldc.i4.1
0xdc7  newarr   [mscorlib]System.Object
0xdcc  dup
0xdcd  ldc.i4.0
0xdce  ldarg.1
0xdcf  stelem.ref
0xdd0  call     string System.Xaml.SR::Get(string id, object[] args)
0xdd5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xdda  throw
0xddb  ldarg.0
0xddc  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xde1  brtrue.s loc_DFC
0xde3  ldarg.0
0xde4  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0xde9  stfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xdee  ldarg.0
0xdef  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xdf4  ldarg.1
0xdf5  ldarg.2
0xdf6  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0xdfb  ret
0xdfc  ldarg.0
0xdfd  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xe02  ldarg.1
0xe03  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0xe08  stloc.0
0xe09  ldloc.0
0xe0a  brtrue.s loc_E1A
0xe0c  ldarg.0
0xe0d  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Xaml.NameScope::_nameMap
0xe12  ldarg.1
0xe13  ldarg.2
0xe14  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0xe19  ret
0xe1a  ldarg.2
0xe1b  ldloc.0
0xe1c  beq.s    loc_E38
0xe1e  ldstr    aNamescopedupli// "NameScopeDuplicateNamesNotAllowed"
0xe23  ldc.i4.1
0xe24  newarr   [mscorlib]System.Object
0xe29  dup
0xe2a  ldc.i4.0
0xe2b  ldarg.1
0xe2c  stelem.ref
0xe2d  call     string System.Xaml.SR::Get(string id, object[] args)
0xe32  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xe37  throw
0xe38  ret
```
