# Microsoft.BIServer.Configuration.ConfigReader::GetServiceSettings

- ea: `0x1430`
- end: `0x14b5`
- name: `Microsoft.BIServer.Configuration.ConfigReader::GetServiceSettings`
- size: `133`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1bb0`
- `0x1c00`

## callees

- `0x1430`
- `0x14c0`
- `0x1760`
- `0x1780`
- `0x35b0`
- `0x35d0`
- `0x35f0`
- `0x3610`
- `0x3630`
- `0x3640`

## string_xrefs

- `0x1437`: `/Service`
- `0x1452`: `MaxQueueThreads`
- `0x1482`: `IsEventService`
- `0x1495`: `IsDataModelRefreshService`

## pseudocode

```c

```

## disassembly

```asm
0x1430  ldarg.0
0x1431  ldarg.0
0x1432  ldfld    class [System.Xml.Linq]System.Xml.Linq.XElement Microsoft.BIServer.Configuration.ConfigReader::_rootElement
0x1437  ldstr    aService// "/Service"
0x143c  call     T0x2B00000F
0x1441  call     T0x2B000014
0x1446  stloc.0
0x1447  newobj   instance void Microsoft.BIServer.Configuration.ServiceSettings::.ctor()
0x144c  stloc.1
0x144d  ldloc.0
0x144e  brfalse.s loc_14B3
0x1450  ldloc.1
0x1451  ldarg.0
0x1452  ldstr    aMaxqueuethread// "MaxQueueThreads"
0x1457  ldloc.0
0x1458  ldc.i4.0
0x1459  ldc.i4   0x7FFFFFFF
0x145e  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, int32 minValue, [opt] int32 maxValue)
0x1463  callvirt instance void Microsoft.BIServer.Configuration.ServiceSettings::set_MaxQueueThreads(int32 value)
0x1468  ldloc.1
0x1469  ldarg.0
0x146a  ldstr    aPollinginterva// "PollingInterval"
0x146f  ldloc.0
0x1470  ldc.i4.1
0x1471  ldc.i4   0x7FFFFFFF
0x1476  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::ReadIntSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, int32 minValue, [opt] int32 maxValue)
0x147b  callvirt instance void Microsoft.BIServer.Configuration.ServiceSettings::set_PollingInterval(int32 value)
0x1480  ldloc.1
0x1481  ldarg.0
0x1482  ldstr    aIseventservice// "IsEventService"
0x1487  ldloc.0
0x1488  ldc.i4.0
0x1489  call     instance bool Microsoft.BIServer.Configuration.ConfigReader::ReadBoolSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, [opt] bool defaultValue)
0x148e  callvirt instance void Microsoft.BIServer.Configuration.ServiceSettings::set_IsEventService(bool value)
0x1493  ldloc.1
0x1494  ldarg.0
0x1495  ldstr    aIsdatamodelref// "IsDataModelRefreshService"
0x149a  ldloc.0
0x149b  ldc.i4.1
0x149c  call     instance bool Microsoft.BIServer.Configuration.ConfigReader::ReadBoolSettingWithValidation(string element, class [System.Xml.Linq]System.Xml.Linq.XElement configSection, [opt] bool defaultValue)
0x14a1  callvirt instance void Microsoft.BIServer.Configuration.ServiceSettings::set_IsDataModelRefreshService(bool value)
0x14a6  ldloc.1
0x14a7  ldarg.0
0x14a8  ldloc.0
0x14a9  call     instance int32 Microsoft.BIServer.Configuration.ConfigReader::GetMaxPoolsize(class [System.Xml.Linq]System.Xml.Linq.XElement serviceSettings)
0x14ae  callvirt instance void Microsoft.BIServer.Configuration.ServiceSettings::set_MaxCatalogConnectionPoolSizePerProcess(int32 value)
0x14b3  ldloc.1
0x14b4  ret
```
