# Microsoft.BIServer.Configuration.XmlConfigFile::AddMaxCatalogConnectionPoolSizePerProcess

- ea: `0x4230`
- end: `0x428e`
- name: `Microsoft.BIServer.Configuration.XmlConfigFile::AddMaxCatalogConnectionPoolSizePerProcess`
- size: `94`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x4230`
- `0x4290`

## string_xrefs

- `0x423a`: `Service tag does not exist in the config file`
- `0x4261`: `MaxCatalogConnectionPoolSizePerProcess doesn't exists in the config file`

## pseudocode

```c

```

## disassembly

```asm
0x4230  ldarg.0
0x4231  call     instance class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.XmlConfigFile::GetServiceElement()
0x4236  stloc.0
0x4237  ldloc.0
0x4238  brtrue.s loc_4254
0x423a  ldstr    aServiceTagDoes// "Service tag does not exist in the confi"...
0x423f  ldc.i4.1
0x4240  newarr   [mscorlib]System.Object
0x4245  dup
0x4246  ldc.i4.0
0x4247  ldarg.0
0x4248  ldfld    string Microsoft.BIServer.Configuration.XmlConfigFile::_configFilePath
0x424d  stelem.ref
0x424e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x4253  ret
0x4254  ldloc.0
0x4255  ldstr    aMaxcatalogconn_0// "//MaxCatalogConnectionPoolSizePerProces"...
0x425a  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.XPath.Extensions::XPathSelectElement(class [System.Xml.Linq]System.Xml.Linq.XNode, string)
0x425f  brtrue.s loc_428D
0x4261  ldstr    aMaxcatalogconn_1// "MaxCatalogConnectionPoolSizePerProcess "...
0x4266  call     T0x2B000015
0x426b  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x4270  ldstr    aMaxcatalogconn// "MaxCatalogConnectionPoolSizePerProcess"
0x4275  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x427a  ldc.i4.0
0x427b  box      [mscorlib]System.Int32
0x4280  newobj   instance void [System.Xml.Linq]System.Xml.Linq.XElement::.ctor(class [System.Xml.Linq]System.Xml.Linq.XName, object)
0x4285  stloc.1
0x4286  ldloc.0
0x4287  ldloc.1
0x4288  callvirt instance void [System.Xml.Linq]System.Xml.Linq.XContainer::Add(object)
0x428d  ret
```
