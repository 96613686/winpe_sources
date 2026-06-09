# NGenTask.ParsedLogsInfo::AddNewNativeImage

- ea: `0x3590`
- end: `0x35cb`
- name: `NGenTask.ParsedLogsInfo::AddNewNativeImage`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x3620`
- `0x3930`

## callees

- `0x3590`

## pseudocode

```c

```

## disassembly

```asm
0x3590  ldc.i4.1
0x3591  stloc.0
0x3592  ldarg.0
0x3593  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::m_nativeImages
0x3598  ldarg.1
0x3599  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::ContainsKey(var<u1>)
0x359e  brfalse.s loc_35BA
0x35a0  ldarg.0
0x35a1  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::m_nativeImages
0x35a6  ldarg.1
0x35a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::get_Item(void)
0x35ac  stloc.1
0x35ad  ldloca.s 1
0x35af  ldarg.2
0x35b0  call     instance int32 [mscorlib]System.DateTime::CompareTo(valuetype [mscorlib]System.DateTime)
0x35b5  ldc.i4.0
0x35b6  blt.s    loc_35BA
0x35b8  ldc.i4.0
0x35b9  stloc.0
0x35ba  ldloc.0
0x35bb  brfalse.s loc_35CA
0x35bd  ldarg.0
0x35be  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime> NGenTask.ParsedLogsInfo::m_nativeImages
0x35c3  ldarg.1
0x35c4  ldarg.2
0x35c5  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.DateTime>::set_Item(var<u1>, !!T0)
0x35ca  ret
```
