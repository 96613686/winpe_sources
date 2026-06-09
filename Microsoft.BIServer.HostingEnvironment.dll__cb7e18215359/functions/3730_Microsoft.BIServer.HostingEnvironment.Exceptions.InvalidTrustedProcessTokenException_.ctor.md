# Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor

- ea: `0x3730`
- end: `0x374d`
- name: `Microsoft.BIServer.HostingEnvironment.Exceptions.InvalidTrustedProcessTokenException::.ctor`
- size: `29`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x3380`

## callees

- `0x3700`

## string_xrefs

- `0x3731`: `Invalid Trusted Process Token!  `

## pseudocode

```c

```

## disassembly

```asm
0x3730  ldarg.0
0x3731  ldstr    aInvalidTrusted_0// "Invalid Trusted Process Token!  "
0x3736  ldarg.1
0x3737  call     string [mscorlib]System.String::Concat(string, string)
0x373c  ldarg.2
0x373d  call     string [mscorlib]System.String::Format(string, object[])
0x3742  call     T0x2B00000A
0x3747  call     instance void Microsoft.BIServer.HostingEnvironment.Exceptions.HostingEnvironmentException::.ctor(string message, object[] parametersObjects)
0x374c  ret
```
