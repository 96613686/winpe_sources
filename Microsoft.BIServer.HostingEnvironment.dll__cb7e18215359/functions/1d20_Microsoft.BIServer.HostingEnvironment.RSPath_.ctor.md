# Microsoft.BIServer.HostingEnvironment.RSPath::.ctor

- ea: `0x1d20`
- end: `0x1d3c`
- name: `Microsoft.BIServer.HostingEnvironment.RSPath::.ctor`
- size: `28`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1d50`
- `0x1d70`
- `0x1d90`
- `0x1db0`
- `0x1dd0`
- `0x1e10`
- `0x1e20`
- `0x1e40`
- `0x1eb0`
- `0x1ef0`
- `0x1f50`

## callees

- `0x1d20`

## string_xrefs

- `0x1d29`: `RSPath cannot be created with a null string`

## pseudocode

```c

```

## disassembly

```asm
0x1d20  ldarg.0
0x1d21  call     instance void [mscorlib]System.Object::.ctor()
0x1d26  ldarg.1
0x1d27  brtrue.s loc_1D34
0x1d29  ldstr    aRspathCannotBe// "RSPath cannot be created with a null st"...
0x1d2e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1d33  throw
0x1d34  ldarg.0
0x1d35  ldarg.1
0x1d36  stfld    string Microsoft.BIServer.HostingEnvironment.RSPath::_path
0x1d3b  ret
```
