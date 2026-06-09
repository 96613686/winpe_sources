# NGenTask.LogsParser::.cctor

- ea: `0x3cb0`
- end: `0x3d01`
- name: `NGenTask.LogsParser::.cctor`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `service_task`

## string_xrefs

- `0x3cc4`: `\A2,"(?<assembly_path>[^"]+)",(?<binder_num>[0-9]+)\z`
- `0x3cd8`: `\A3,"(?<assembly_path>[^"]+)","(?<ni_path>[^,]*)",(?<binder_num>[0-9]+)\z`
- `0x3cec`: `\A4,"(?<assembly_path>[^"]+)",(?<binder_num>[0-9]+),(?<timestamp>[0-9a-fA-F]+)\z`

## pseudocode

```c

```

## disassembly

```asm
0x3cb0  ldstr    aA1BinderBinder// "\\A1,\"(?<binder>[^,]*)\",\"(?<binder_p"...
0x3cb5  ldc.i4   0x200
0x3cba  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3cbf  stsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_BindingContextRegex
0x3cc4  ldstr    aA2AssemblyPath// "\\A2,\"(?<assembly_path>[^\"]+)\",(?<bi"...
0x3cc9  ldc.i4   0x200
0x3cce  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3cd3  stsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_ILAssemblyRegex
0x3cd8  ldstr    aA3AssemblyPath// "\\A3,\"(?<assembly_path>[^\"]+)\",\"(?<"...
0x3cdd  ldc.i4   0x200
0x3ce2  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3ce7  stsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_NIUseRegex
0x3cec  ldstr    aA4AssemblyPath// "\\A4,\"(?<assembly_path>[^\"]+)\",(?<bi"...
0x3cf1  ldc.i4   0x200
0x3cf6  newobj   instance void [System]System.Text.RegularExpressions.Regex::.ctor(string, valuetype [System]System.Text.RegularExpressions.RegexOptions)
0x3cfb  stsfld   class [System]System.Text.RegularExpressions.Regex NGenTask.LogsParser::s_ReinstallRegex
0x3d00  ret
```
