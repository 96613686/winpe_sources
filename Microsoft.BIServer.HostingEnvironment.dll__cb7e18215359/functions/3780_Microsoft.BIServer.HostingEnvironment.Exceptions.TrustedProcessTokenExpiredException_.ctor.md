# Microsoft.BIServer.HostingEnvironment.Exceptions.TrustedProcessTokenExpiredException::.ctor

- ea: `0x3780`
- end: `0x3793`
- name: `Microsoft.BIServer.HostingEnvironment.Exceptions.TrustedProcessTokenExpiredException::.ctor`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3380`

## callees

- `0x3700`

## pseudocode

```c

```

## disassembly

```asm
0x3780  ldarg.0
0x3781  ldarg.1
0x3782  ldarg.2
0x3783  call     string [mscorlib]System.String::Format(string, object[])
0x3788  call     T0x2B00000A
0x378d  call     instance void Microsoft.BIServer.HostingEnvironment.Exceptions.HostingEnvironmentException::.ctor(string message, object[] parametersObjects)
0x3792  ret
```
