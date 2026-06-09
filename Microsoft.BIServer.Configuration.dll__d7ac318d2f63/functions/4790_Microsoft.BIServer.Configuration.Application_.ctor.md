# Microsoft.BIServer.Configuration.Application::.ctor

- ea: `0x4790`
- end: `0x47da`
- name: `Microsoft.BIServer.Configuration.Application::.ctor`
- size: `74`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1d70`
- `0x3b00`

## callees

- `0x4740`
- `0x4760`
- `0x4780`
- `0x4790`
- `0x7860`

## string_xrefs

- `0x4799`: `VirtualDirectory is null.`

## pseudocode

```c

```

## disassembly

```asm
0x4790  ldarg.0
0x4791  call     instance void [mscorlib]System.Object::.ctor()
0x4796  ldarg.2
0x4797  brtrue.s loc_47A4
0x4799  ldstr    aVirtualdirecto_0// "VirtualDirectory is null."
0x479e  newobj   instance void InvalidUrlReservation::.ctor(string message)
0x47a3  throw
0x47a4  ldarg.2
0x47a5  ldstr    asc_AC04// "/"
0x47aa  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x47af  brfalse.s loc_47BA
0x47b1  ldarg.0
0x47b2  ldarg.2
0x47b3  call     instance void Microsoft.BIServer.Configuration.Application::set_VirtualDirectory(string value)
0x47b8  br.s     loc_47CB
0x47ba  ldarg.0
0x47bb  ldstr    asc_AC04// "/"
0x47c0  ldarg.2
0x47c1  call     string [mscorlib]System.String::Concat(string, string)
0x47c6  call     instance void Microsoft.BIServer.Configuration.Application::set_VirtualDirectory(string value)
0x47cb  ldarg.0
0x47cc  ldarg.1
0x47cd  call     instance void Microsoft.BIServer.Configuration.Application::set_Name(string value)
0x47d2  ldarg.0
0x47d3  ldarg.3
0x47d4  call     instance void Microsoft.BIServer.Configuration.Application::set_URLs(class Microsoft.BIServer.Configuration.URL[] value)
0x47d9  ret
```
