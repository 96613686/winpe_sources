# NGenTask.ExcludeList::Save

- ea: `0x160`
- end: `0x218`
- name: `NGenTask.ExcludeList::Save`
- size: `184`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x160`
- `0x2c60`

## pseudocode

```c

```

## disassembly

```asm
0x160  ldarg.0
0x161  ldfld    string NGenTask.ExcludeList::filename
0x166  brtrue.s loc_169
0x168  ret
0x169  ldarg.0
0x16a  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0x16f  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::get_Count()
0x174  brfalse.s loc_1F2
0x176  ldarg.0
0x177  ldfld    string NGenTask.ExcludeList::filename
0x17c  call     class [mscorlib]System.IO.StreamWriter [mscorlib]System.IO.File::CreateText(string)
0x181  stloc.0
0x182  ldarg.0
0x183  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64> NGenTask.ExcludeList::entries
0x188  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, int64>::GetEnumerator()
0x18d  stloc.1
0x18e  br.s     loc_1B6
0x190  ldloca.s 1
0x192  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>::get_Current()
0x197  stloc.2
0x198  ldloc.0
0x199  ldstr    a01// "{0}\t{1}"
0x19e  ldloca.s 2
0x1a0  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Key()
0x1a5  ldloca.s 2
0x1a7  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, int64>::get_Value()
0x1ac  box      [mscorlib]System.Int64
0x1b1  callvirt instance void [mscorlib]System.IO.TextWriter::WriteLine(string, object, object)
0x1b6  ldloca.s 1
0x1b8  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>::MoveNext()
0x1bd  brtrue.s loc_190
0x1bf  leave.s  loc_1CF
0x1c1  ldloca.s 1
0x1c3  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, int64>
0x1c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ce  endfinally
0x1cf  leave.s  loc_1DB
0x1d1  ldloc.0
0x1d2  brfalse.s loc_1DA
0x1d4  ldloc.0
0x1d5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1da  endfinally
0x1db  leave.s  loc_217
0x1dd  stloc.3
0x1de  ldc.i4.0
0x1df  ldloc.3
0x1e0  ldstr    aErrorUpdatingN// "Error updating NGenDisable.txt"
0x1e5  ldc.i4.0
0x1e6  newarr   [mscorlib]System.Object
0x1eb  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1f0  leave.s  loc_217
0x1f2  nop
0x1f3  ldarg.0
0x1f4  ldfld    string NGenTask.ExcludeList::filename
0x1f9  call     void [mscorlib]System.IO.File::Delete(string)
0x1fe  leave.s  loc_217
0x200  stloc.s  4
0x202  ldc.i4.0
0x203  ldloc.s  4
0x205  ldstr    aErrorDeletingN// "Error deleting NGenDisable.txt"
0x20a  ldc.i4.0
0x20b  newarr   [mscorlib]System.Object
0x210  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x215  leave.s  loc_217
0x217  ret
```
