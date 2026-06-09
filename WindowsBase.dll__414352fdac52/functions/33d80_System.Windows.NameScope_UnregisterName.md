# System.Windows.NameScope::UnregisterName

- ea: `0x33d80`
- end: `0x33dfd`
- name: `System.Windows.NameScope::UnregisterName`
- size: `125`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x340f0`

## callees

- `0x11f40`
- `0x120f0`
- `0x12150`
- `0x2c100`
- `0x2c130`
- `0x33d80`

## string_xrefs

- `0x33d9b`: `NameScopeNameNotEmptyString`
- `0x33dcf`: `NameScopeNameNotFound`

## pseudocode

```c

```

## disassembly

```asm
0x33d80  ldarg.1
0x33d81  brtrue.s loc_33D8E
0x33d83  ldstr    aName_0// "name"
0x33d88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x33d8d  throw
0x33d8e  ldarg.1
0x33d8f  ldsfld   string [mscorlib]System.String::Empty
0x33d94  call     bool [mscorlib]System.String::op_Equality(string, string)
0x33d99  brfalse.s loc_33DAB
0x33d9b  ldstr    aNamescopenamen// "NameScopeNameNotEmptyString"
0x33da0  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x33da5  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33daa  throw
0x33dab  ldarg.0
0x33dac  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33db1  brfalse.s loc_33DCF
0x33db3  ldarg.0
0x33db4  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33db9  ldarg.1
0x33dba  callvirt instance object [System]System.Collections.Specialized.HybridDictionary::get_Item(object)
0x33dbf  brfalse.s loc_33DCF
0x33dc1  ldarg.0
0x33dc2  ldfld    class [System]System.Collections.Specialized.HybridDictionary System.Windows.NameScope::_nameMap
0x33dc7  ldarg.1
0x33dc8  callvirt instance void [System]System.Collections.Specialized.HybridDictionary::Remove(object)
0x33dcd  br.s     loc_33DE9
0x33dcf  ldstr    aNamescopenamen_0// "NameScopeNameNotFound"
0x33dd4  ldc.i4.1
0x33dd5  newarr   [mscorlib]System.Object
0x33dda  dup
0x33ddb  ldc.i4.0
0x33ddc  ldarg.1
0x33ddd  stelem.ref
0x33dde  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x33de3  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x33de8  throw
0x33de9  call     bool MS.Internal.TraceNameScope::get_IsEnabled()
0x33dee  brfalse.s loc_33DFC
0x33df0  call     class MS.Internal.AvTraceDetails MS.Internal.TraceNameScope::get_UnregisterName()
0x33df5  ldarg.0
0x33df6  ldarg.1
0x33df7  call     void MS.Internal.TraceNameScope::TraceActivityItem(class MS.Internal.AvTraceDetails traceDetails, object p1, object p2)
0x33dfc  ret
```
