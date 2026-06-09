# Microsoft.BIServer.Configuration.XmlConfigFile::CommitChanges

- ea: `0x3eb0`
- end: `0x3f0a`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::CommitChanges`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x3eb0`

## string_xrefs

- `0x3ee4`: `Writing ConfigReader File [{0}]`

## pseudocode

```c

```

## disassembly

```asm
0x3eb0  newobj   instance void [System.Xml]System.Xml.XmlWriterSettings::.ctor()
0x3eb5  dup
0x3eb6  ldc.i4.1
0x3eb7  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_OmitXmlDeclaration(bool)
0x3ebc  dup
0x3ebd  ldc.i4.1
0x3ebe  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_Indent(bool)
0x3ec3  dup
0x3ec4  ldc.i4.1
0x3ec5  callvirt instance void [System.Xml]System.Xml.XmlWriterSettings::set_NewLineHandling(valuetype [System.Xml]System.Xml.NewLineHandling)
0x3eca  stloc.0
0x3ecb  ldarg.0
0x3ecc  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x3ed1  ldloc.0
0x3ed2  call     class [System.Xml]System.Xml.XmlWriter [System.Xml]System.Xml.XmlWriter::Create(string, class [System.Xml]System.Xml.XmlWriterSettings)
0x3ed7  stloc.1
0x3ed8  ldarg.0
0x3ed9  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x3ede  ldloc.1
0x3edf  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::Save(class [System.Xml]System.Xml.XmlWriter)
0x3ee4  ldstr    aWritingConfigr// "Writing ConfigReader File [{0}]"
0x3ee9  ldc.i4.1
0x3eea  newarr   [mscorlib]System.Object
0x3eef  dup
0x3ef0  ldc.i4.0
0x3ef1  ldarg.0
0x3ef2  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x3ef7  stelem.ref
0x3ef8  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x3efd  leave.s  loc_3F09
0x3eff  ldloc.1
0x3f00  brfalse.s loc_3F08
0x3f02  ldloc.1
0x3f03  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3f08  endfinally
0x3f09  ret
```
