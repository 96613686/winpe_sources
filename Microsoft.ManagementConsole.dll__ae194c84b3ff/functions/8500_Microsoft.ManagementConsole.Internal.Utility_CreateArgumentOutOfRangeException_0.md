# Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException_0

- ea: `0x8500`
- end: `0x8522`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException_0`
- size: `34`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3530`
- `0x3570`
- `0x35b0`
- `0x35f0`
- `0x3630`
- `0x3670`
- `0x36b0`
- `0x36f0`
- `0x7c70`

## callees

- `0x90`
- `0x8470`

## pseudocode

```c

```

## disassembly

```asm
0x8500  ldarg.0
0x8501  ldarg.1
0x8502  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionArgumentOutOfRangeMin()
0x8507  ldc.i4.2
0x8508  newarr   [mscorlib]System.Object
0x850d  stloc.0
0x850e  ldloc.0
0x850f  ldc.i4.0
0x8510  ldarg.0
0x8511  stelem.ref
0x8512  ldloc.0
0x8513  ldc.i4.1
0x8514  ldarg.2
0x8515  stelem.ref
0x8516  ldloc.0
0x8517  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x851c  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, object, string)
0x8521  ret
```
