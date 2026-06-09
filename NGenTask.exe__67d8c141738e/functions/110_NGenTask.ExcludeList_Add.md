# NGenTask.ExcludeList::Add

- ea: `0x110`
- end: `0x153`
- name: `NGenTask.ExcludeList::Add`
- size: `67`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x12d0`

## callees

- `0x110`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldc.i4.0
0x111  conv.i8
0x112  stloc.0
0x113  ldarg.1
0x114  call     bool [mscorlib]System.IO.File::Exists(string)
0x119  brfalse.s loc_12A
0x11b  ldarg.1
0x11c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.IO.File::GetLastWriteTimeUtc(string)
0x121  stloc.1
0x122  ldloca.s 1
0x124  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x129  stloc.0
0x12a  leave.s  loc_145
0x12c  stloc.2
0x12d  ldc.i4.3
0x12e  ldloc.2
0x12f  ldstr    aErrorGettingTi// "Error getting timestamp of assembly \"{"...
0x134  ldc.i4.1
0x135  newarr   [mscorlib]System.Object
0x13a  dup
0x13b  ldc.i4.0
0x13c  ldarg.1
0x13d  stelem.ref
0x13e  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x143  leave.s  loc_145
0x145  ldarg.0
0x146  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0x14b  ldarg.1
0x14c  ldloc.0
0x14d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::set_Item(var<u1>, !!T0)
0x152  ret
```
