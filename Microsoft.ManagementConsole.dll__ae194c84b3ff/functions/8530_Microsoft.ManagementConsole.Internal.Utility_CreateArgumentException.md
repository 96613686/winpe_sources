# Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException

- ea: `0x8530`
- end: `0x8554`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateArgumentException`
- size: `36`
- prototype: ``
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2510`
- `0x28e0`
- `0x2a20`
- `0x3150`
- `0x5bb0`
- `0x9260`
- `0x95b0`
- `0xb190`
- `0xb220`
- `0xdf90`

## callees

- `0x8470`
- `0x8530`

## pseudocode

```c

```

## disassembly

```asm
0x8530  ldarg.2
0x8531  brfalse.s loc_8538
0x8533  ldarg.2
0x8534  ldlen
0x8535  conv.i4
0x8536  brtrue.s loc_8546
0x8538  ldc.i4.1
0x8539  newarr   [mscorlib]System.Object
0x853e  stloc.0
0x853f  ldloc.0
0x8540  ldc.i4.0
0x8541  ldarg.0
0x8542  stelem.ref
0x8543  ldloc.0
0x8544  starg.s  2
0x8546  ldarg.1
0x8547  ldarg.2
0x8548  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x854d  ldarg.0
0x854e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x8553  ret
```
