# Microsoft.ReportingServices.Diagnostics.RSConfigurationManagerProxy::OnChanged

- ea: `0x7060`
- end: `0x7099`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationManagerProxy::OnChanged`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x15c0`
- `0x15e0`
- `0x1640`
- `0x4170`
- `0x7060`

## pseudocode

```c

```

## disassembly

```asm
0x7060  ldarg.1
0x7061  ldarg.0
0x7062  beq.s    loc_707B
0x7064  ldarg.0
0x7065  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x706a  ldarg.2
0x706b  callvirt instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventArgs::get_Properties()
0x7070  ldarg.2
0x7071  callvirt instance bool Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventArgs::get_ResetProperties()
0x7076  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Load(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties, bool resetProperties)
0x707b  ldarg.0
0x707c  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfigurationManagerProxy::m_raiseEvents
0x7081  brfalse.s loc_7098
0x7083  ldarg.0
0x7084  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventHandler Microsoft.ReportingServices.Diagnostics.RSConfigurationManagerProxy::Changed
0x7089  brfalse.s loc_7098
0x708b  ldarg.0
0x708c  ldfld    class Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventHandler Microsoft.ReportingServices.Diagnostics.RSConfigurationManagerProxy::Changed
0x7091  ldarg.0
0x7092  ldarg.2
0x7093  callvirt instance void Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventHandler::Invoke(object sender, class Microsoft.ReportingServices.Diagnostics.ConfigurationChangeEventArgs e)
0x7098  ret
```
