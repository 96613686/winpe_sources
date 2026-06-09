# Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException

- ea: `0x2e0`
- end: `0x306`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException`
- size: `38`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x49f0`

## callees

- `0x30`
- `0x2c0`

## pseudocode

```c

```

## disassembly

```asm
0x2e0  ldarg.0
0x2e1  ldarg.1
0x2e2  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionArgumentOutOfRangeMinMax()
0x2e7  ldc.i4.3
0x2e8  newarr   [mscorlib]System.Object
0x2ed  stloc.0
0x2ee  ldloc.0
0x2ef  ldc.i4.0
0x2f0  ldarg.0
0x2f1  stelem.ref
0x2f2  ldloc.0
0x2f3  ldc.i4.1
0x2f4  ldarg.2
0x2f5  stelem.ref
0x2f6  ldloc.0
0x2f7  ldc.i4.2
0x2f8  ldarg.3
0x2f9  stelem.ref
0x2fa  ldloc.0
0x2fb  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x300  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, object, string)
0x305  ret
```
