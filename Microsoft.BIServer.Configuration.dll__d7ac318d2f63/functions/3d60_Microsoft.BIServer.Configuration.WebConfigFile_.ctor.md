# Microsoft.BIServer.Configuration.WebConfigFile::.ctor

- ea: `0x3d60`
- end: `0x3d7a`
- name: `Microsoft.BIServer.Configuration.WebConfigFile::.ctor`
- size: `26`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1100`
- `0x1180`
- `0x1220`

## pseudocode

```c

```

## disassembly

```asm
0x3d60  ldarg.0
0x3d61  call     instance void [mscorlib]System.Object::.ctor()
0x3d66  ldarg.0
0x3d67  ldarg.1
0x3d68  stfld    string Microsoft.BIServer.Configuration.WebConfigFile::_fullWebConfigFilePath
0x3d6d  ldarg.0
0x3d6e  ldarg.1
0x3d6f  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x3d74  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.WebConfigFile::_rootElement
0x3d79  ret
```
