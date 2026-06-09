# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::.ctor_1

- ea: `0x7280`
- end: `0x72ed`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::.ctor_1`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x36e0`
- `0x4170`
- `0x4bd0`
- `0x6f40`
- `0x7390`

## pseudocode

```c

```

## disassembly

```asm
0x7280  ldarg.0
0x7281  ldstr    asc_126C2// ""
0x7286  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x728b  ldarg.0
0x728c  ldstr    asc_126C2// ""
0x7291  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x7296  ldarg.0
0x7297  newobj   instance void [mscorlib]System.Object::.ctor()
0x729c  stfld    object Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configChangeLockObject
0x72a1  ldarg.0
0x72a2  call     instance void Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::.ctor()
0x72a7  ldarg.0
0x72a8  ldsfld   string [mscorlib]System.String::Empty
0x72ad  ldsfld   string [mscorlib]System.String::Empty
0x72b2  newobj   instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::.ctor(string configFileName, string configLocation)
0x72b7  stfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x72bc  ldarg.0
0x72bd  ldarg.0
0x72be  ldarg.1
0x72bf  call     instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseDocument(class [System.Xml]System.Xml.XmlDocument xmlConfiguration)
0x72c4  stfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x72c9  ldarg.0
0x72ca  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x72cf  ldarg.0
0x72d0  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x72d5  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Validate(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x72da  ldarg.0
0x72db  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x72e0  ldarg.0
0x72e1  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x72e6  ldc.i4.1
0x72e7  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Load(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties, bool resetProperties)
0x72ec  ret
```
