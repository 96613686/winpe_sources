# Microsoft.BIServer.Configuration.XmlConfigFile::.ctor

- ea: `0x3e10`
- end: `0x3e4d`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::.ctor`
- size: `61`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3e60`

## string_xrefs

- `0x3e22`: `Reading Config File [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x3e10  ldarg.0
0x3e11  call     instance void [mscorlib]System.Object::.ctor()
0x3e16  ldarg.0
0x3e17  ldarg.1
0x3e18  call     string Microsoft.BIServer.Configuration.XmlConfigFile::GetFileFromDirectory(string installDir)
0x3e1d  stfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x3e22  ldstr    aReadingConfigF// "Reading Config File [{0}]"
0x3e27  ldc.i4.1
0x3e28  newarr   [mscorlib]System.Object
0x3e2d  dup
0x3e2e  ldc.i4.0
0x3e2f  ldarg.0
0x3e30  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x3e35  stelem.ref
0x3e36  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3e3b  ldarg.0
0x3e3c  ldarg.0
0x3e3d  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x3e42  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x3e47  stfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x3e4c  ret
```
