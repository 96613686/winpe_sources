# System.ComponentModel.Design.UndoEngine::GetRequiredService

- ea: `0x62b60`
- end: `0x62b99`
- name: `System.ComponentModel.Design.UndoEngine::GetRequiredService`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x62700`
- `0x128f90`

## callees

- `0x62b60`
- `0x62ba0`
- `0x8eec0`

## string_xrefs

- `0x62b6b`: `UndoEngineMissingService`
- `0x62b8b`: `UndoEngineMissingService`

## pseudocode

```c

```

## disassembly

```asm
0x62b60  ldarg.0
0x62b61  ldarg.1
0x62b62  call     instance object System.ComponentModel.Design.UndoEngine::GetService(class [mscorlib]System.Type serviceType)
0x62b67  stloc.0
0x62b68  ldloc.0
0x62b69  brtrue.s loc_62B97
0x62b6b  ldstr    aUndoenginemiss// "UndoEngineMissingService"
0x62b70  ldc.i4.1
0x62b71  newarr   [mscorlib]System.Object
0x62b76  dup
0x62b77  ldc.i4.0
0x62b78  ldarg.1
0x62b79  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x62b7e  stelem.ref
0x62b7f  call     string System.Design.SR::GetString(string name, object[] args)
0x62b84  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x62b89  stloc.1
0x62b8a  ldloc.1
0x62b8b  ldstr    aUndoenginemiss// "UndoEngineMissingService"
0x62b90  callvirt instance void [mscorlib]System.Exception::set_HelpLink(string)
0x62b95  ldloc.1
0x62b96  throw
0x62b97  ldloc.0
0x62b98  ret
```
