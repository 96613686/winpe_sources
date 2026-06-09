# NGenTask.TaskExecutive::GetFrameworkPath

- ea: `0x2020`
- end: `0x204b`
- name: `NGenTask.TaskExecutive::GetFrameworkPath`
- size: `43`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x310`
- `0xf20`
- `0x1ad0`
- `0x1db0`
- `0x1e00`
- `0x2050`

## callees

- `0x2020`

## pseudocode

```c

```

## disassembly

```asm
0x2020  ldarg.0
0x2021  ldfld    string NGenTask.TaskExecutive::m_frameworkPath
0x2026  brfalse.s loc_202F
0x2028  ldarg.0
0x2029  ldfld    string NGenTask.TaskExecutive::m_frameworkPath
0x202e  ret
0x202f  ldarg.0
0x2030  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x2035  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x203a  call     string [mscorlib]System.IO.Path::GetDirectoryName(string)
0x203f  stfld    string NGenTask.TaskExecutive::m_frameworkPath
0x2044  ldarg.0
0x2045  ldfld    string NGenTask.TaskExecutive::m_frameworkPath
0x204a  ret
```
