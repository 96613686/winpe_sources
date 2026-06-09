# Microsoft.VisualStudio.Setup.ParameterException::.ctor

- ea: `0x20e0`
- end: `0x20fa`
- name: `Microsoft.VisualStudio.Setup.ParameterException::.ctor`
- size: `26`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2060`
- `0x20a0`

## callees

- `0x2010`
- `0x2110`

## pseudocode

```c

```

## disassembly

```asm
0x20e0  ldarg.0
0x20e1  ldarg.1
0x20e2  call     instance void Microsoft.VisualStudio.Setup.CommandLineParseException::.ctor(class Microsoft.VisualStudio.Setup.CommandLine command)
0x20e7  ldarg.2
0x20e8  ldstr    aParameter// "parameter"
0x20ed  call     void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Validate::IsNotNullOrEmpty(string, string)
0x20f2  ldarg.0
0x20f3  ldarg.2
0x20f4  call     instance void Microsoft.VisualStudio.Setup.ParameterException::set_Parameter(string value)
0x20f9  ret
```
