# Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadDocument

- ea: `0x7340`
- end: `0x7384`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::LoadDocument`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x72f0`

## callees

- `0x4bd0`
- `0x7390`
- `0x10330`

## pseudocode

```c

```

## disassembly

```asm
0x7340  newobj   instance void <>c__DisplayClass18_0::.ctor()
0x7345  stloc.0
0x7346  ldloc.0
0x7347  ldarg.0
0x7348  stfld    class Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager <>c__DisplayClass18_0::<>4__this
0x734d  ldloc.0
0x734e  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x7353  stfld    class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass18_0::xmlConfiguration
0x7358  ldloc.0
0x7359  ldftn    instance void <>c__DisplayClass18_0::<LoadDocument>b__0()
0x735f  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody::.ctor(object, native int)
0x7364  call     void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RevertImpersonationContext::Run(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ContextBody)
0x7369  ldarg.0
0x736a  ldloc.0
0x736b  ldfld    class [System.Xml]System.Xml.XmlDocument <>c__DisplayClass18_0::xmlConfiguration
0x7370  call     instance class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag Microsoft.ReportingServices.Diagnostics.RSConfigurationFileManager::ParseDocument(class [System.Xml]System.Xml.XmlDocument xmlConfiguration)
0x7375  stloc.1
0x7376  ldarg.0
0x7377  ldfld    class Microsoft.ReportingServices.Diagnostics.RSConfiguration Microsoft.ReportingServices.Diagnostics.RSConfigurationManager::m_config
0x737c  ldloc.1
0x737d  callvirt instance void Microsoft.ReportingServices.Diagnostics.RSConfiguration::Validate(class Microsoft.ReportingServices.Diagnostics.ConfigurationPropertyBag properties)
0x7382  ldloc.1
0x7383  ret
```
