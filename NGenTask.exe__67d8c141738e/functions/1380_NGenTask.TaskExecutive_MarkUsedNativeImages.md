# NGenTask.TaskExecutive::MarkUsedNativeImages

- ea: `0x1380`
- end: `0x13ff`
- name: `NGenTask.TaskExecutive::MarkUsedNativeImages`
- size: `127`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x1380`
- `0x2c30`
- `0x3700`

## string_xrefs

- `0x1381`: `Marking used native images with new last accessed timestamp information ({0})`

## pseudocode

```c

```

## disassembly

```asm
0x1380  ldc.i4.3
0x1381  ldstr    aMarkingUsedNat// "Marking used native images with new las"...
0x1386  ldc.i4.1
0x1387  newarr   [mscorlib]System.Object
0x138c  dup
0x138d  ldc.i4.0
0x138e  ldarg.2
0x138f  stelem.ref
0x1390  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1395  ldarg.1
0x1396  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::get_NativeImages()
0x139b  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>>::GetEnumerator()
0x13a0  stloc.0
0x13a1  br.s     loc_13EA
0x13a3  ldloc.0
0x13a4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>>::get_Current()
0x13a9  stloc.1
0x13aa  ldarg.0
0x13ab  volatile.
0x13ad  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x13b2  brfalse.s loc_13B6
0x13b4  leave.s  loc_13FE
0x13b6  nop
0x13b7  ldloca.s 1
0x13b9  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>::get_Key()
0x13be  stloc.2
0x13bf  ldarg.3
0x13c0  brfalse.s loc_13CE
0x13c2  ldloc.2
0x13c3  ldstr    aAux// ".aux"
0x13c8  call     string [mscorlib]System.String::Concat(string, string)
0x13cd  stloc.2
0x13ce  ldloc.2
0x13cf  newobj   instance void [mscorlib]System.IO.FileInfo::.ctor(string)
0x13d4  stloc.3
0x13d5  ldloc.3
0x13d6  ldloca.s 1
0x13d8  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, valuetype [mscorlib]System.DateTime>::get_Value()
0x13dd  callvirt instance void [mscorlib]System.IO.FileSystemInfo::set_LastAccessTimeUtc(valuetype [mscorlib]System.DateTime)
0x13e2  leave.s  loc_13EA
0x13e4  pop
0x13e5  leave.s  loc_13EA
0x13e7  pop
0x13e8  leave.s  loc_13EA
0x13ea  ldloc.0
0x13eb  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x13f0  brtrue.s loc_13A3
0x13f2  leave.s  loc_13FE
0x13f4  ldloc.0
0x13f5  brfalse.s loc_13FD
0x13f7  ldloc.0
0x13f8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x13fd  endfinally
0x13fe  ret
```
