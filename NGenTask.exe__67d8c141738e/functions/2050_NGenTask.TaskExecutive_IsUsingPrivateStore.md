# NGenTask.TaskExecutive::IsUsingPrivateStore

- ea: `0x2050`
- end: `0x2095`
- name: `NGenTask.TaskExecutive::IsUsingPrivateStore`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x310`
- `0x20a0`

## callees

- `0x2020`
- `0x2050`

## pseudocode

```c

```

## disassembly

```asm
0x2050  ldarg.0
0x2051  ldflda   valuetype [mscorlib]System.Nullable`1<bool> NGenTask.TaskExecutive::m_fIsLocalGac
0x2056  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x205b  brfalse.s loc_2069
0x205d  ldarg.0
0x205e  ldflda   valuetype [mscorlib]System.Nullable`1<bool> NGenTask.TaskExecutive::m_fIsLocalGac
0x2063  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2068  ret
0x2069  ldarg.0
0x206a  ldarg.0
0x206b  call     instance string NGenTask.TaskExecutive::GetFrameworkPath()
0x2070  ldstr    aFusionLocalgac// "fusion.localgac"
0x2075  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x207a  call     bool [mscorlib]System.IO.File::Exists(string)
0x207f  newobj   instance void valuetype [mscorlib]System.Nullable`1<bool>::.ctor(var<u1>)
0x2084  stfld    valuetype [mscorlib]System.Nullable`1<bool> NGenTask.TaskExecutive::m_fIsLocalGac
0x2089  ldarg.0
0x208a  ldflda   valuetype [mscorlib]System.Nullable`1<bool> NGenTask.TaskExecutive::m_fIsLocalGac
0x208f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x2094  ret
```
