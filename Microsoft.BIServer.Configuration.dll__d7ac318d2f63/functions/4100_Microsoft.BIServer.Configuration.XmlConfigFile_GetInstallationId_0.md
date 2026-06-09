# Microsoft.BIServer.Configuration.XmlConfigFile::GetInstallationId_0

- ea: `0x4100`
- end: `0x4135`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetInstallationId_0`
- size: `53`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x4100`

## string_xrefs

- `0x4106`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x4100  ldarg.0
0x4101  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::_rootElement
0x4106  ldstr    aInstallationid// "InstallationID"
0x410b  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4110  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x4115  stloc.0
0x4116  ldloc.0
0x4117  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x411c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4121  brtrue.s loc_412F
0x4123  ldloc.0
0x4124  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x4129  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x412e  ret
0x412f  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4134  ret
```
