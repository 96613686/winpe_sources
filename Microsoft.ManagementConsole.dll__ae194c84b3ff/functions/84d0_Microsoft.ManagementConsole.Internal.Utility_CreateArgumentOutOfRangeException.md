# Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException

- ea: `0x84d0`
- end: `0x84f6`
- name: `Microsoft.ManagementConsole.Internal.Utility::CreateArgumentOutOfRangeException`
- size: `38`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3730`
- `0x6ad0`
- `0x8b30`
- `0xd950`

## callees

- `0xa0`
- `0x8470`

## pseudocode

```c

```

## disassembly

```asm
0x84d0  ldarg.0
0x84d1  ldarg.1
0x84d2  call     string Microsoft.ManagementConsole.Internal.Strings::get_ExceptionArgumentOutOfRangeMinMax()
0x84d7  ldc.i4.3
0x84d8  newarr   [mscorlib]System.Object
0x84dd  stloc.0
0x84de  ldloc.0
0x84df  ldc.i4.0
0x84e0  ldarg.0
0x84e1  stelem.ref
0x84e2  ldloc.0
0x84e3  ldc.i4.1
0x84e4  ldarg.2
0x84e5  stelem.ref
0x84e6  ldloc.0
0x84e7  ldc.i4.2
0x84e8  ldarg.3
0x84e9  stelem.ref
0x84ea  ldloc.0
0x84eb  call     string Microsoft.ManagementConsole.Internal.Utility::FormatResourceString(string resourceName, object[] parms)
0x84f0  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string, object, string)
0x84f5  ret
```
