# Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException_0

- ea: `0x310`
- end: `0x332`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException_0`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x49d0`

## callees

- `0x20`
- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldarg.0
0x311  ldarg.1
0x312  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionArgumentOutOfRangeMin()
0x317  ldc.i4.2
0x318  newarr   [mscorlib]System.Object
0x31d  stloc.0
0x31e  ldloc.0
0x31f  ldc.i4.0
0x320  ldarg.0
0x321  stelem.ref
0x322  ldloc.0
0x323  ldc.i4.1
0x324  ldarg.2
0x325  stelem.ref
0x326  ldloc.0
0x327  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x32c  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, object, string)
0x331  ret
```
