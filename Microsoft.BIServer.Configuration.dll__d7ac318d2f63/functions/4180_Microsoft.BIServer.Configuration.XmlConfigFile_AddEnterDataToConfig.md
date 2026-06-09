# Microsoft.BIServer.Configuration.XmlConfigFile::AddEnterDataToConfig

- ea: `0x4180`
- end: `0x4227`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::AddEnterDataToConfig`
- size: `167`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x4180`
- `0x42b0`
- `0x42d0`

## string_xrefs

- `0x41cb`: `Configuration`
- `0x418a`: `Data tag does not exist in the config file`
- `0x41ac`: `Enter Data Extension doesn't exists in the config file`
- `0x41c1`: `Extension`
- `0x41d5`: `ConfigName`
- `0x4214`: `Microsoft.ReportingServices.DataExtensions.XmlDPConnection,Microsoft.ReportingServices.DataExtensions`

## pseudocode

```c

```

## disassembly

```asm
0x4180  ldarg.0
0x4181  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::GetDataElement()
0x4186  stloc.0
0x4187  ldloc.0
0x4188  brtrue.s loc_41A4
0x418a  ldstr    aDataTagDoesNot// "Data tag does not exist in the config f"...
0x418f  ldc.i4.1
0x4190  newarr   [mscorlib]System.Object
0x4195  dup
0x4196  ldc.i4.0
0x4197  ldarg.0
0x4198  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x419d  stelem.ref
0x419e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x41a3  ret
0x41a4  ldarg.0
0x41a5  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::GetEnterDataElement()
0x41aa  brtrue.s loc_4226
0x41ac  ldstr    aEnterDataExten// "Enter Data Extension doesn't exists in "...
0x41b1  call     T0x2B000015
0x41b6  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x41bb  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XDocument::.ctor()
0x41c0  pop
0x41c1  ldstr    aExtension// "Extension"
0x41c6  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x41cb  ldstr    aConfiguration// "Configuration"
0x41d0  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x41d5  ldstr    aConfigname// "ConfigName"
0x41da  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x41df  ldstr    aEnterdata// "ENTERDATA"
0x41e4  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x41e9  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x41ee  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x41f3  stloc.1
0x41f4  ldloc.1
0x41f5  ldstr    aName// "Name"
0x41fa  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x41ff  ldstr    aEnterdata// "ENTERDATA"
0x4204  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::SetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x4209  ldloc.1
0x420a  ldstr    aType// "Type"
0x420f  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x4214  ldstr    aMicrosoftRepor// "Microsoft.ReportingServices.DataExtensi"...
0x4219  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XElement::SetAttributeValue(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x421e  ldloc.0
0x421f  ldloc.1
0x4220  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x4225  ret
0x4226  ret
```
