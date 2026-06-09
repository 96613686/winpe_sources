# Microsoft.BIServer.HostingEnvironment.Logger::ParseLevel

- ea: `0xe60`
- end: `0xe7d`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::ParseLevel`
- size: `29`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xf10`
- `0xf80`

## callees

- `0xe60`

## pseudocode

```c

```

## disassembly

```asm
0xe60  ldarg.0
0xe61  ldloca.s 0
0xe63  call     T0x2B00000B
0xe68  brtrue.s loc_E7B
0xe6a  ldstr    a0IsNotAValidLo// "{0} is not a valid Logger.Level"
0xe6f  ldarg.0
0xe70  call     string [mscorlib]System.String::Format(string, object)
0xe75  newobj   instance void [System]System.Configuration.ConfigurationException::.ctor(string)
0xe7a  throw
0xe7b  ldloc.0
0xe7c  ret
```
