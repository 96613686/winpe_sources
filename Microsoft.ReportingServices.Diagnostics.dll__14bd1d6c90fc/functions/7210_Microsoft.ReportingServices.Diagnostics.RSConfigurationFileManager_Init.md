# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::Init

- ea: `0x7210`
- end: `0x7271`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::Init`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x7180`
- `0x71e0`

## callees

- `0x36e0`
- `0x4170`
- `0x7210`
- `0x72f0`

## pseudocode

```c

```

## disassembly

```asm
0x7210  ldarg.0
0x7211  ldarg.1
0x7212  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x7217  ldarg.0
0x7218  ldarg.2
0x7219  stfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x721e  ldarg.0
0x721f  ldarg.0
0x7220  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x7225  ldarg.0
0x7226  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x722b  newobj   instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::.ctor(string configFileName, string configLocation)
0x7230  stfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x7235  ldarg.0
0x7236  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x723b  brfalse.s loc_7270
0x723d  ldarg.0
0x723e  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configFileName
0x7243  brfalse.s loc_7270
0x7245  ldarg.0
0x7246  ldfld    string Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_configLocation
0x724b  call     bool [mscorlib]System.IO.Directory::Exists(string)
0x7250  brfalse.s loc_7270
0x7252  ldarg.0
0x7253  ldarg.0
0x7254  callvirt instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadConfiguration()
0x7259  stfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x725e  ldarg.0
0x725f  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x7264  ldarg.0
0x7265  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::m_properties
0x726a  ldc.i4.1
0x726b  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Load(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties, bool resetProperties)
0x7270  ret
```
