# Microsoft.VisualStudio.Setup.CommandLineParseException::.ctor

- ea: `0x2010`
- end: `0x202d`
- name: `Microsoft.VisualStudio.Setup.CommandLineParseException::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x20e0`

## callees

- `0x2010`
- `0x2040`

## string_xrefs

- `0x201c`: `command`

## pseudocode

```c

```

## disassembly

```asm
0x2010  ldarg.0
0x2011  call     instance void [mscorlib]System.Exception::.ctor()
0x2016  ldarg.0
0x2017  ldarg.1
0x2018  dup
0x2019  brtrue.s loc_2027
0x201b  pop
0x201c  ldstr    aCommand// "command"
0x2021  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2026  throw
0x2027  call     instance void Microsoft.VisualStudio.Setup.CommandLineParseException::set_Command(class Microsoft.VisualStudio.Setup.CommandLine value)
0x202c  ret
```
