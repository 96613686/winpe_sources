# Microsoft.BIServer.Configuration.XmlConfigFile::GetInstallationId

- ea: `0x3db0`
- end: `0x3e03`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::GetInstallationId`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x3db0`
- `0x78a0`

## string_xrefs

- `0x3db8`: `Missing file at path {0}`
- `0x3dd4`: `InstallationID`

## pseudocode

```c

```

## disassembly

```asm
0x3db0  ldarg.0
0x3db1  call     bool [mscorlib]System.IO.File::Exists(string)
0x3db6  brtrue.s loc_3DCE
0x3db8  ldstr    aMissingFileAtP// "Missing file at path {0}"
0x3dbd  ldarg.0
0x3dbe  call     string [mscorlib]System.IO.Path::GetFullPath(string)
0x3dc3  call     string [mscorlib]System.String::Format(string, object)
0x3dc8  newobj   instance void MissingConfigFile::.ctor(string message)
0x3dcd  throw
0x3dce  ldarg.0
0x3dcf  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x3dd4  ldstr    aInstallationid// "InstallationID"
0x3dd9  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x3dde  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XContainer::Element(class [System.Xml.Linq]System.Xml.Linq.XName)
0x3de3  stloc.0
0x3de4  ldloc.0
0x3de5  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x3dea  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3def  brtrue.s loc_3DFD
0x3df1  ldloc.0
0x3df2  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XElement::get_Value()
0x3df7  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x3dfc  ret
0x3dfd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e02  ret
```
