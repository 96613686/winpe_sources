# Microsoft.BIServer.Configuration.InstanceRegistry::GetCurrentVersionKey

- ea: `0x3110`
- end: `0x312a`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::GetCurrentVersionKey`
- size: `26`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x30f0`

## callees

- `0x3130`

## pseudocode

```c

```

## disassembly

```asm
0x3110  ldstr    aHkeyLocalMachi// "HKEY_LOCAL_MACHINE\\Software\\Microsoft"...
0x3115  call     class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath Microsoft.BIServer.Configuration.InstanceRegistry::get_CurrentInstancePath()
0x311a  call     string [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath::op_Implicit(class [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.RSPath)
0x311f  ldstr    aMssqlserverCur// "MSSQLServer\\CurrentVersion"
0x3124  call     string [mscorlib]System.IO.Path::Combine(string, string, string)
0x3129  ret
```
