# Microsoft.BIServer.Configuration.Exceptions.ConfigException::Assert

- ea: `0x6790`
- end: `0x67ac`
- name: `Microsoft.BIServer.Configuration.Exceptions.ConfigException::Assert`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x6790`
- `0x67b0`

## pseudocode

```c

```

## disassembly

```asm
0x6790  ldarg.0
0x6791  brtrue.s loc_67AB
0x6793  ldarg.1
0x6794  ldarg.2
0x6795  call     string [mscorlib]System.String::Format(string, object[])
0x679a  dup
0x679b  call     T0x2B000015
0x67a0  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Error(string, object[])
0x67a5  newobj   instance void Microsoft.BIServer.Configuration.Exceptions.ConfigException::.ctor(string message)
0x67aa  throw
0x67ab  ret
```
