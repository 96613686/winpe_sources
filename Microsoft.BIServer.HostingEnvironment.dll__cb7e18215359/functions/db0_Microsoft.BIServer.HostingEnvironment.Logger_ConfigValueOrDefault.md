# Microsoft.BIServer.HostingEnvironment.Logger::ConfigValueOrDefault

- ea: `0xdb0`
- end: `0xdf5`
- name: `Microsoft.BIServer.HostingEnvironment.Logger::ConfigValueOrDefault`
- size: `69`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0xcc0`

## callees

- `0x340`
- `0xdb0`

## string_xrefs

- `0xdcb`: `CONFIG: {0} = {1} (default)`
- `0xdd9`: `CONFIG: {0} = {1} (env)`
- `0xde7`: `CONFIG: {0} = {1} (switch)`

## pseudocode

```c

```

## disassembly

```asm
0xdb0  ldsfld   class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.Args::CommandLine
0xdb5  ldarg.0
0xdb6  ldloca.s 0
0xdb8  callvirt instance bool Microsoft.BIServer.HostingEnvironment.Args::TryGetSwitch(string key, [out] string& value)
0xdbd  brtrue.s loc_DE7
0xdbf  ldarg.0
0xdc0  call     string [mscorlib]System.Environment::GetEnvironmentVariable(string)
0xdc5  stloc.0
0xdc6  ldloc.0
0xdc7  brtrue.s loc_DD9
0xdc9  ldarg.1
0xdca  stloc.0
0xdcb  ldstr    aConfig01Defaul// "CONFIG: {0} = {1} (default)"
0xdd0  ldarg.0
0xdd1  ldloc.0
0xdd2  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0xdd7  br.s     loc_DF3
0xdd9  ldstr    aConfig01Env// "CONFIG: {0} = {1} (env)"
0xdde  ldarg.0
0xddf  ldloc.0
0xde0  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0xde5  br.s     loc_DF3
0xde7  ldstr    aConfig01Switch// "CONFIG: {0} = {1} (switch)"
0xdec  ldarg.0
0xded  ldloc.0
0xdee  call     void [mscorlib]System.Console::WriteLine(string, object, object)
0xdf3  ldloc.0
0xdf4  ret
```
