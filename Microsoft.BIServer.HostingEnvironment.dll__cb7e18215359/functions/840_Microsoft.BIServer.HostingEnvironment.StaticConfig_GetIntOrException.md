# Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrException

- ea: `0x840`
- end: `0x866`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::GetIntOrException`
- size: `38`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x7e0`
- `0x840`

## pseudocode

```c

```

## disassembly

```asm
0x840  ldarg.0
0x841  ldarg.1
0x842  call     instance string Microsoft.BIServer.HostingEnvironment.StaticConfig::GetOrException(string key)
0x847  stloc.0
0x848  ldloc.0
0x849  ldloca.s 1
0x84b  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x850  brfalse.s loc_854
0x852  ldloc.1
0x853  ret
0x854  ldstr    aTheValue0ForTh// "The value {0} for the parameter is not "...
0x859  ldloc.0
0x85a  call     string [mscorlib]System.String::Format(string, object)
0x85f  ldarg.1
0x860  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x865  throw
```
