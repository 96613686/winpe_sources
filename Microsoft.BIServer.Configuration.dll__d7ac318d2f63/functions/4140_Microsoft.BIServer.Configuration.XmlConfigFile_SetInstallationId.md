# Microsoft.BIServer.Configuration.XmlConfigFile::SetInstallationId

- ea: `0x4140`
- end: `0x4180`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::SetInstallationId`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config, installer_update, broker_com_uri`

## string_xrefs

- `0x415f`: `InstallationID`
- `0x4140`: `Setting Installation ID to {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4140  ldstr    aSettingInstall// "Setting Installation ID to {0}"
0x4145  ldc.i4.1
0x4146  newarr   [mscorlib]System.Object
0x414b  dup
0x414c  ldc.i4.0
0x414d  ldarg.1
0x414e  box      [mscorlib]System.Guid
0x4153  stelem.ref
0x4154  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x4159  ldarg.0
0x415a  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x415f  ldstr    aInstallationid// "InstallationID"
0x4164  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4169  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x416e  ldarga.s 1
0x4170  ldstr    aB// "B"
0x4175  call     instance string [mscorlib]System.Guid::ToString(string)
0x417a  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::set_Value(string)
0x417f  ret
```
