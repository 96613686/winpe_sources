# NGenTask.TaskHelper::.cctor

- ea: `0x2ee0`
- end: `0x2efb`
- name: `NGenTask.TaskHelper::.cctor`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## string_xrefs

- `0x2ee0`: `\A(?<assembly_name>[A-Za-z0-9.]+), Version=\d+\.\d+\.\d+\.\d+, Culture=(?<culture>[-a-z]+), PublicKeyToken=(?<token>[a-f0-9]{16})\z`

## pseudocode

```c

```

## disassembly

```asm
0x2ee0  ldstr    aAAssemblyNameA// "\\A(?<assembly_name>[A-Za-z0-9.]+), Ver"...
0x2ee5  ldc.i4   0x200
0x2eea  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x2eef  stsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.TaskHelper::s_assemblyNameRegex
0x2ef4  ldnull
0x2ef5  stsfld   class [mscorlib]System.Reflection.MethodInfo NGenTask.TaskHelper::s_isFrameworkAssembly
0x2efa  ret
```
