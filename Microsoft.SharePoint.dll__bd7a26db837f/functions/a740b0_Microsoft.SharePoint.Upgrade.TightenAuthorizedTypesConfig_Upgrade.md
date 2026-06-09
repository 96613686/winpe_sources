# Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::Upgrade

- ea: `0xa740b0`
- end: `0xa74248`
- name: `Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::Upgrade`
- size: `408`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0xa45800`
- `0xa4f220`
- `0xa6d090`
- `0xa6d240`
- `0xa74250`
- `0xa742a0`

## string_xrefs

- `0xa740d3`: `System.Workflow.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa7415b`: `System.Workflow.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74195`: `System.Workflow.Activities, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa740f3`: `System.Workflow.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74178`: `System.Workflow.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa741b2`: `System.Workflow.Activities, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74113`: `System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa741cf`: `System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74209`: `System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74133`: `System.Workflow.ComponentModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa741ec`: `System.Workflow.ComponentModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa74226`: `System.Workflow.ComponentModel, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35`
- `0xa7414d`: `configuration/System.Workflow.ComponentModel.WorkflowCompiler/authorizedTypes/targetFx`
- `0xa740bb`: `=====TightenAuthorizedTypesConfig`
- `0xa740ce`: `configuration/System.Workflow.ComponentModel.WorkflowCompiler/authorizedTypes/targetFx/authorizedType[@Assembly='{0}'][@Namespace='{1}'][@TypeName='{2}']`
- `0xa740ee`: `configuration/System.Workflow.ComponentModel.WorkflowCompiler/authorizedTypes/targetFx/authorizedType[@Assembly='{0}'][@Namespace='{1}'][@TypeName='{2}']`
- `0xa7410e`: `configuration/System.Workflow.ComponentModel.WorkflowCompiler/authorizedTypes/targetFx/authorizedType[@Assembly='{0}'][@Namespace='{1}'][@TypeName='{2}']`
- `0xa7412e`: `configuration/System.Workflow.ComponentModel.WorkflowCompiler/authorizedTypes/targetFx/authorizedType[@Assembly='{0}'][@Namespace='{1}'][@TypeName='{2}']`

## pseudocode

```c

```

## disassembly

```asm
0xa740b0  ldarg.0
0xa740b1  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa740b6  ldc.i4   0x25A54B
0xa740bb  ldstr    aTightenauthori// "=====TightenAuthorizedTypesConfig"
0xa740c0  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa740c5  ldarg.0
0xa740c6  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa740cb  stloc.0
0xa740cc  ldarg.0
0xa740cd  ldloc.0
0xa740ce  ldstr    aConfigurationS_66// "configuration/System.Workflow.Component"...
0xa740d3  ldstr    aSystemWorkflow_4// "System.Workflow.Activities, Version=3.0"...
0xa740d8  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa740dd  ldstr    asc_C84B56// "*"
0xa740e2  call     string [mscorlib]System.String::Format(string, object, object, object)
0xa740e7  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::EnsureNodeRemoved(class [System.Xml]System.Xml.XmlDocument webConfig, string xPath)
0xa740ec  ldarg.0
0xa740ed  ldloc.0
0xa740ee  ldstr    aConfigurationS_66// "configuration/System.Workflow.Component"...
0xa740f3  ldstr    aSystemWorkflow_5// "System.Workflow.Activities, Version=4.0"...
0xa740f8  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa740fd  ldstr    asc_C84B56// "*"
0xa74102  call     string [mscorlib]System.String::Format(string, object, object, object)
0xa74107  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::EnsureNodeRemoved(class [System.Xml]System.Xml.XmlDocument webConfig, string xPath)
0xa7410c  ldarg.0
0xa7410d  ldloc.0
0xa7410e  ldstr    aConfigurationS_66// "configuration/System.Workflow.Component"...
0xa74113  ldstr    aSystemWorkflow_6// "System.Workflow.ComponentModel, Version"...
0xa74118  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa7411d  ldstr    asc_C84B56// "*"
0xa74122  call     string [mscorlib]System.String::Format(string, object, object, object)
0xa74127  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::EnsureNodeRemoved(class [System.Xml]System.Xml.XmlDocument webConfig, string xPath)
0xa7412c  ldarg.0
0xa7412d  ldloc.0
0xa7412e  ldstr    aConfigurationS_66// "configuration/System.Workflow.Component"...
0xa74133  ldstr    aSystemWorkflow_7// "System.Workflow.ComponentModel, Version"...
0xa74138  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa7413d  ldstr    asc_C84B56// "*"
0xa74142  call     string [mscorlib]System.String::Format(string, object, object, object)
0xa74147  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::EnsureNodeRemoved(class [System.Xml]System.Xml.XmlDocument webConfig, string xPath)
0xa7414c  ldloc.0
0xa7414d  ldstr    aConfigurationS_60// "configuration/System.Workflow.Component"...
0xa74152  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa74157  stloc.1
0xa74158  ldarg.0
0xa74159  ldloc.0
0xa7415a  ldloc.1
0xa7415b  ldstr    aSystemWorkflow_4// "System.Workflow.Activities, Version=3.0"...
0xa74160  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa74165  ldarg.0
0xa74166  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::safeAuthorizedTypesInSysWFActivities
0xa7416b  ldstr    aTrue_3// "True"
0xa74170  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa74175  ldarg.0
0xa74176  ldloc.0
0xa74177  ldloc.1
0xa74178  ldstr    aSystemWorkflow_5// "System.Workflow.Activities, Version=4.0"...
0xa7417d  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa74182  ldarg.0
0xa74183  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::safeAuthorizedTypesInSysWFActivities
0xa74188  ldstr    aTrue_3// "True"
0xa7418d  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa74192  ldarg.0
0xa74193  ldloc.0
0xa74194  ldloc.1
0xa74195  ldstr    aSystemWorkflow_4// "System.Workflow.Activities, Version=3.0"...
0xa7419a  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa7419f  ldarg.0
0xa741a0  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::unSafeAuthorizedTypesInSysWFActivities
0xa741a5  ldstr    aFalse_3// "False"
0xa741aa  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa741af  ldarg.0
0xa741b0  ldloc.0
0xa741b1  ldloc.1
0xa741b2  ldstr    aSystemWorkflow_5// "System.Workflow.Activities, Version=4.0"...
0xa741b7  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa741bc  ldarg.0
0xa741bd  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::unSafeAuthorizedTypesInSysWFActivities
0xa741c2  ldstr    aFalse_3// "False"
0xa741c7  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa741cc  ldarg.0
0xa741cd  ldloc.0
0xa741ce  ldloc.1
0xa741cf  ldstr    aSystemWorkflow_6// "System.Workflow.ComponentModel, Version"...
0xa741d4  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa741d9  ldarg.0
0xa741da  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::safeAuthorizedTypesInSysWFComponentModel
0xa741df  ldstr    aTrue_3// "True"
0xa741e4  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa741e9  ldarg.0
0xa741ea  ldloc.0
0xa741eb  ldloc.1
0xa741ec  ldstr    aSystemWorkflow_7// "System.Workflow.ComponentModel, Version"...
0xa741f1  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa741f6  ldarg.0
0xa741f7  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::safeAuthorizedTypesInSysWFComponentModel
0xa741fc  ldstr    aTrue_3// "True"
0xa74201  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa74206  ldarg.0
0xa74207  ldloc.0
0xa74208  ldloc.1
0xa74209  ldstr    aSystemWorkflow_6// "System.Workflow.ComponentModel, Version"...
0xa7420e  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa74213  ldarg.0
0xa74214  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::unSafeAuthorizedTypesInSysWFComponentModel
0xa74219  ldstr    aFalse_3// "False"
0xa7421e  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa74223  ldarg.0
0xa74224  ldloc.0
0xa74225  ldloc.1
0xa74226  ldstr    aSystemWorkflow_7// "System.Workflow.ComponentModel, Version"...
0xa7422b  ldstr    aSystemWorkflow_9// "System.Workflow.*"
0xa74230  ldarg.0
0xa74231  ldfld    string[] Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::unSafeAuthorizedTypesInSysWFComponentModel
0xa74236  ldstr    aFalse_3// "False"
0xa7423b  call     instance void Microsoft.SharePoint.Upgrade.TightenAuthorizedTypesConfig::AppendNewAuthorizedTypeNode(class [System.Xml]System.Xml.XmlDocument xd, class [System.Xml]System.Xml.XmlNode xeAuthorizedTypesNode, string assemblyToAuthorize, string nameSpaceToAuthorize, string[] typeNamesToAuthorize, string authorizedStr)
0xa74240  ldarg.0
0xa74241  ldc.i4.1
0xa74242  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa74247  ret
```
