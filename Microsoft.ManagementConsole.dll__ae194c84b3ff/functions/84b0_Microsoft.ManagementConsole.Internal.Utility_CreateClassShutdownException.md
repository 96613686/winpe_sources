# Microsoft.ManagementConsole.Internal.Utility::CreateClassShutdownException

- ea: `0x84b0`
- end: `0x84d0`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateClassShutdownException`
- size: `32`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x9d70`
- `0xd7e0`

## callees

- `0xd0`
- `0x8470`

## pseudocode

```c

```

## disassembly

```asm
0x84b0  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionClassShutdown()
0x84b5  ldc.i4.2
0x84b6  newarr   [mscorlib]System.Object
0x84bb  stloc.0
0x84bc  ldloc.0
0x84bd  ldc.i4.0
0x84be  ldarg.0
0x84bf  stelem.ref
0x84c0  ldloc.0
0x84c1  ldc.i4.1
0x84c2  ldarg.1
0x84c3  stelem.ref
0x84c4  ldloc.0
0x84c5  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x84ca  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x84cf  ret
```
