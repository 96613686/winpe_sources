# Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor_0

- ea: `0x3750`
- end: `0x376e`
- name: `Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor_0`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3380`

## callees

- `0x3710`

## string_xrefs

- `0x3752`: `Invalid Trusted Process Token!  `

## pseudocode

```c

```

## disassembly

```asm
0x3750  ldarg.0
0x3751  ldarg.1
0x3752  ldstr    aInvalidTrusted_0// "Invalid Trusted Process Token!  "
0x3757  ldarg.2
0x3758  call     string [mscorlib]System.String::Concat(string, string)
0x375d  ldarg.3
0x375e  call     string [mscorlib]System.String::Format(string, object[])
0x3763  call     T0x2B00000A
0x3768  call     instance void Microsoft.BIServer.HostingEnvironment.Exceptions.HostingEnvironmentException::.ctor(class [mscorlib]System.Exception innerException, string message, object[] parametersObjects)
0x376d  ret
```
