# System.Windows.NameScope::RegisterName

- ea: `0x33cb0`
- end: `0x33d7f`
- name: `System.Windows.NameScope::RegisterName`
- size: `207`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x34080`
- `0x340b0`

## callees

- `0x11f00`
- `0x12120`
- `0x12150`
- `0x2c100`
- `0x2c130`
- `0x33cb0`
- `0x44be0`

## string_xrefs

- `0x33cd9`: `NameScopeNameNotEmptyString`

## pseudocode

```c

```

## disassembly

```asm
0x33cb0  ldarg.1
0x33cb1  brtrue.s loc_33CBE
0x33cb3  ldstr    aName_0// "name"
0x33cb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33cbd  throw
0x33cbe  ldarg.2
0x33cbf  brtrue.s loc_33CCC
0x33cc1  ldstr    aScopedelement// "scopedElement"
0x33cc6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33ccb  throw
0x33ccc  ldarg.1
0x33ccd  ldsfld   string [mscorlib]System.String::Empty
0x33cd2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33cd7  brfalse.s loc_33CE9
0x33cd9  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0x33cde  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x33ce3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33ce8  throw
0x33ce9  ldarg.1
0x33cea  call     bool System.Windows.Markup.NameValidationHelper::IsValidIdentifierName(string name)
0x33cef  brtrue.s loc_33D0B
0x33cf1  ldstr    aNamescopeinval// "NameScopeInvalidIdentifierName"
0x33cf6  ldc.i4.1
0x33cf7  newarr   [mscorlib]System.Object
0x33cfc  dup
0x33cfd  ldc.i4.0
0x33cfe  ldarg.1
0x33cff  stelem.ref
0x33d00  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x33d05  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33d0a  throw
0x33d0b  ldarg.0
0x33d0c  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33d11  brtrue.s loc_33D2D
0x33d13  ldarg.0
0x33d14  newobj   instance void [System]System.Collections.Specialized.HybridDictionary::.ctor()
0x33d19  stfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33d1e  ldarg.0
0x33d1f  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33d24  ldarg.1
0x33d25  ldarg.2
0x33d26  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x33d2b  br.s     loc_33D6A
0x33d2d  ldarg.0
0x33d2e  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33d33  ldarg.1
0x33d34  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x33d39  stloc.0
0x33d3a  ldloc.0
0x33d3b  brtrue.s loc_33D4C
0x33d3d  ldarg.0
0x33d3e  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33d43  ldarg.1
0x33d44  ldarg.2
0x33d45  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::set_Item(object, object)
0x33d4a  br.s     loc_33D6A
0x33d4c  ldarg.2
0x33d4d  ldloc.0
0x33d4e  beq.s    loc_33D6A
0x33d50  ldstr    aNamescopedupli// "NameScopeDuplicateNamesNotAllowed"
0x33d55  ldc.i4.1
0x33d56  newarr   [mscorlib]System.Object
0x33d5b  dup
0x33d5c  ldc.i4.0
0x33d5d  ldarg.1
0x33d5e  stelem.ref
0x33d5f  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x33d64  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33d69  throw
0x33d6a  call     bool MS.Internal.TraceNameScope::get_IsEnabled()
0x33d6f  brfalse.s loc_33D7E
0x33d71  call     class MS.Internal.AvTraceDetails MS.Internal.TraceNameScope::get_RegisterName()
0x33d76  ldarg.0
0x33d77  ldarg.1
0x33d78  ldarg.2
0x33d79  call     void MS.Internal.TraceNameScope::TraceActivityItem(class MS.Internal.AvTraceDetails traceDetails, object p1, object p2, object p3)
0x33d7e  ret
```
