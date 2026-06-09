# Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::EnsureAjaxEntries

- ea: `0xa6ee20`
- end: `0xa6f019`
- name: `Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::EnsureAjaxEntries`
- size: `505`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0xa6ece0`

## callees

- `0x19bc40`
- `0xa6ee00`
- `0xa6ee20`

## string_xrefs

- `0xa6ef81`: `configuration/system.webServer/modules`
- `0xa6ee35`: `configuration/system.web`
- `0xa6ee9a`: `configuration/SharePoint/SafeControls`
- `0xa6eebb`: `configuration/system.web/httpHandlers`
- `0xa6ef1e`: `configuration/system.web/httpHandlers`
- `0xa6ef3f`: `configuration/system.web/httpHandlers`
- `0xa6ee23`: `configuration/configSections`
- `0xa6ee79`: `configuration/configSections`
- `0xa6ee47`: `configuration/system.webServer`
- `0xa6ef60`: `configuration/system.webServer`
- `0xa6ee59`: `configuration/system.web.extensions`
- `0xa6ee6b`: `configuration/configSections/sectionGroup[@name='system.web.extensions']`
- `0xa6ee7f`: `<sectionGroup name="system.web.extensions" type="System.Web.Configuration.SystemWebExtensionsSectionGroup, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">\n      <sectionGroup name="scripting" type="System.Web.Configuration.ScriptingSectionGroup, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35">\n          <section name="scriptResourceHandler" type="System.Web.Configuration.ScriptingScriptResourceHandlerSection`
- `0xa6ee8c`: `configuration/SharePoint/SafeControls/SafeControl[@Assembly='System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'][@Namespace='System.Web.UI']`
- `0xa6eea0`: `<SafeControl Assembly="System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" Namespace="System.Web.UI" TypeName="*" Safe="True" AllowRemoteDesigner="True" SafeAgainstScript="False" />`
- `0xa6eead`: `configuration/system.web/httpHandlers/add[@path='*_AppService.axd']`
- `0xa6eec1`: `<add verb="*" path="*_AppService.axd" validate="false" type="System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6eece`: `configuration/system.web/compilation/assemblies/add[@assembly='System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35']`
- `0xa6eedc`: `configuration/system.web/compilation/assemblies`
- `0xa6eee2`: `<add assembly="System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6eeef`: `configuration/system.web/pages/controls/add[@assembly='System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35'][@tagPrefix='asp'][@namespace='System.Web.UI']`
- `0xa6eefd`: `configuration/system.web/pages/controls`
- `0xa6ef03`: `<add tagPrefix="asp" namespace="System.Web.UI" assembly="System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6ef10`: `configuration/system.web/httpHandlers/remove[@verb='*'][@path='*.asmx']`
- `0xa6ef24`: `<remove verb="*" path="*.asmx" />`
- `0xa6ef31`: `configuration/system.web/httpHandlers/add[@verb='*'][@path='*.asmx']`
- `0xa6ef45`: `<add verb="*" path="*.asmx" validate="false" type="System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6ef52`: `configuration/system.webServer/validation`
- `0xa6ef66`: `<validation validateIntegratedModeConfiguration="false" />`
- `0xa6ef73`: `configuration/system.webServer/modules/add[@name='ScriptModule']`
- `0xa6ef87`: `<add name="ScriptModule" preCondition="integratedMode" type="System.Web.Handlers.ScriptModule, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6ef94`: `configuration/system.webServer/handlers/remove[@name='WebServiceHandlerFactory-Integrated']`
- `0xa6efa2`: `configuration/system.webServer/handlers`
- `0xa6efc3`: `configuration/system.webServer/handlers`
- `0xa6efe4`: `configuration/system.webServer/handlers`
- `0xa6f005`: `configuration/system.webServer/handlers`
- `0xa6efa8`: `<remove name="WebServiceHandlerFactory-Integrated" />`
- `0xa6efb5`: `configuration/system.webServer/handlers/add[@name='ScriptHandlerFactory']`
- `0xa6efc9`: `<add name="ScriptHandlerFactory" verb="*" path="*.asmx" preCondition="integratedMode" type="System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6efd6`: `configuration/system.webServer/handlers/add[@name='ScriptHandlerFactoryAppServices']`
- `0xa6efea`: `<add name="ScriptHandlerFactoryAppServices" verb="*" path="*_AppService.axd" preCondition="integratedMode" type="System.Web.Script.Services.ScriptHandlerFactory, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`
- `0xa6eff7`: `configuration/system.webServer/handlers/add[@name='ScriptResource']`
- `0xa6f00b`: `<add name="ScriptResource" preCondition="integratedMode" verb="GET,HEAD" path="ScriptResource.axd" type="System.Web.Handlers.ScriptResourceHandler, System.Web.Extensions, Version=4.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35" />`

## pseudocode

```c

```

## disassembly

```asm
0xa6ee20  ldc.i4.0
0xa6ee21  stloc.0
0xa6ee22  ldarg.0
0xa6ee23  ldstr    aConfigurationC_3// "configuration/configSections"
0xa6ee28  call     bool Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::UpdateAssemblyName(class [System.Xml]System.Xml.XmlDocument webConfig, string path)
0xa6ee2d  brtrue.s loc_A6EE32
0xa6ee2f  ldloc.0
0xa6ee30  br.s     loc_A6EE33
0xa6ee32  ldc.i4.1
0xa6ee33  stloc.0
0xa6ee34  ldarg.0
0xa6ee35  ldstr    aConfigurationS_2// "configuration/system.web"
0xa6ee3a  call     bool Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::UpdateAssemblyName(class [System.Xml]System.Xml.XmlDocument webConfig, string path)
0xa6ee3f  brtrue.s loc_A6EE44
0xa6ee41  ldloc.0
0xa6ee42  br.s     loc_A6EE45
0xa6ee44  ldc.i4.1
0xa6ee45  stloc.0
0xa6ee46  ldarg.0
0xa6ee47  ldstr    aConfigurationS_26// "configuration/system.webServer"
0xa6ee4c  call     bool Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::UpdateAssemblyName(class [System.Xml]System.Xml.XmlDocument webConfig, string path)
0xa6ee51  brtrue.s loc_A6EE56
0xa6ee53  ldloc.0
0xa6ee54  br.s     loc_A6EE57
0xa6ee56  ldc.i4.1
0xa6ee57  stloc.0
0xa6ee58  ldarg.0
0xa6ee59  ldstr    aConfigurationS_27// "configuration/system.web.extensions"
0xa6ee5e  call     bool Microsoft.SharePoint.Upgrade.EnsureAjaxWebConfig::UpdateAssemblyName(class [System.Xml]System.Xml.XmlDocument webConfig, string path)
0xa6ee63  brtrue.s loc_A6EE68
0xa6ee65  ldloc.0
0xa6ee66  br.s     loc_A6EE69
0xa6ee68  ldc.i4.1
0xa6ee69  stloc.0
0xa6ee6a  ldarg.0
0xa6ee6b  ldstr    aConfigurationC_5// "configuration/configSections/sectionGro"...
0xa6ee70  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ee75  stloc.1
0xa6ee76  ldloc.1
0xa6ee77  brtrue.s loc_A6EE8B
0xa6ee79  ldstr    aConfigurationC_3// "configuration/configSections"
0xa6ee7e  ldarg.0
0xa6ee7f  ldstr    aSectiongroupNa_1// "<sectionGroup name=\"system.web.extensi"...
0xa6ee84  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ee89  ldc.i4.1
0xa6ee8a  stloc.0
0xa6ee8b  ldarg.0
0xa6ee8c  ldstr    aConfigurationS_28// "configuration/SharePoint/SafeControls/S"...
0xa6ee91  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ee96  stloc.1
0xa6ee97  ldloc.1
0xa6ee98  brtrue.s loc_A6EEAC
0xa6ee9a  ldstr    aConfigurationS_10// "configuration/SharePoint/SafeControls"
0xa6ee9f  ldarg.0
0xa6eea0  ldstr    aSafecontrolAss// "<SafeControl Assembly=\"System.Web.Exte"...
0xa6eea5  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6eeaa  ldc.i4.1
0xa6eeab  stloc.0
0xa6eeac  ldarg.0
0xa6eead  ldstr    aConfigurationS_29// "configuration/system.web/httpHandlers/a"...
0xa6eeb2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6eeb7  stloc.1
0xa6eeb8  ldloc.1
0xa6eeb9  brtrue.s loc_A6EECD
0xa6eebb  ldstr    aConfigurationS_16// "configuration/system.web/httpHandlers"
0xa6eec0  ldarg.0
0xa6eec1  ldstr    aAddVerbPathApp// "<add verb=\"*\" path=\"*_AppService.axd"...
0xa6eec6  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6eecb  ldc.i4.1
0xa6eecc  stloc.0
0xa6eecd  ldarg.0
0xa6eece  ldstr    aConfigurationS_30// "configuration/system.web/compilation/as"...
0xa6eed3  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6eed8  stloc.1
0xa6eed9  ldloc.1
0xa6eeda  brtrue.s loc_A6EEEE
0xa6eedc  ldstr    aConfigurationS_31// "configuration/system.web/compilation/as"...
0xa6eee1  ldarg.0
0xa6eee2  ldstr    aAddAssemblySys// "<add assembly=\"System.Web.Extensions, "...
0xa6eee7  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6eeec  ldc.i4.1
0xa6eeed  stloc.0
0xa6eeee  ldarg.0
0xa6eeef  ldstr    aConfigurationS_32// "configuration/system.web/pages/controls"...
0xa6eef4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6eef9  stloc.1
0xa6eefa  ldloc.1
0xa6eefb  brtrue.s loc_A6EF0F
0xa6eefd  ldstr    aConfigurationS_33// "configuration/system.web/pages/controls"
0xa6ef02  ldarg.0
0xa6ef03  ldstr    aAddTagprefixAs// "<add tagPrefix=\"asp\" namespace=\"Syst"...
0xa6ef08  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ef0d  ldc.i4.1
0xa6ef0e  stloc.0
0xa6ef0f  ldarg.0
0xa6ef10  ldstr    aConfigurationS_34// "configuration/system.web/httpHandlers/r"...
0xa6ef15  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ef1a  stloc.1
0xa6ef1b  ldloc.1
0xa6ef1c  brtrue.s loc_A6EF30
0xa6ef1e  ldstr    aConfigurationS_16// "configuration/system.web/httpHandlers"
0xa6ef23  ldarg.0
0xa6ef24  ldstr    aRemoveVerbPath// "<remove verb=\"*\" path=\"*.asmx\" />"
0xa6ef29  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ef2e  ldc.i4.1
0xa6ef2f  stloc.0
0xa6ef30  ldarg.0
0xa6ef31  ldstr    aConfigurationS_35// "configuration/system.web/httpHandlers/a"...
0xa6ef36  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ef3b  stloc.1
0xa6ef3c  ldloc.1
0xa6ef3d  brtrue.s loc_A6EF51
0xa6ef3f  ldstr    aConfigurationS_16// "configuration/system.web/httpHandlers"
0xa6ef44  ldarg.0
0xa6ef45  ldstr    aAddVerbPathAsm// "<add verb=\"*\" path=\"*.asmx\" validat"...
0xa6ef4a  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ef4f  ldc.i4.1
0xa6ef50  stloc.0
0xa6ef51  ldarg.0
0xa6ef52  ldstr    aConfigurationS_36// "configuration/system.webServer/validati"...
0xa6ef57  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ef5c  stloc.1
0xa6ef5d  ldloc.1
0xa6ef5e  brtrue.s loc_A6EF72
0xa6ef60  ldstr    aConfigurationS_26// "configuration/system.webServer"
0xa6ef65  ldarg.0
0xa6ef66  ldstr    aValidationVali// "<validation validateIntegratedModeConfi"...
0xa6ef6b  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ef70  ldc.i4.1
0xa6ef71  stloc.0
0xa6ef72  ldarg.0
0xa6ef73  ldstr    aConfigurationS_37// "configuration/system.webServer/modules/"...
0xa6ef78  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ef7d  stloc.1
0xa6ef7e  ldloc.1
0xa6ef7f  brtrue.s loc_A6EF93
0xa6ef81  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa6ef86  ldarg.0
0xa6ef87  ldstr    aAddNameScriptm// "<add name=\"ScriptModule\" preCondition"...
0xa6ef8c  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6ef91  ldc.i4.1
0xa6ef92  stloc.0
0xa6ef93  ldarg.0
0xa6ef94  ldstr    aConfigurationS_38// "configuration/system.webServer/handlers"...
0xa6ef99  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6ef9e  stloc.1
0xa6ef9f  ldloc.1
0xa6efa0  brtrue.s loc_A6EFB4
0xa6efa2  ldstr    aConfigurationS_39// "configuration/system.webServer/handlers"
0xa6efa7  ldarg.0
0xa6efa8  ldstr    aRemoveNameWebs// "<remove name=\"WebServiceHandlerFactory"...
0xa6efad  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6efb2  ldc.i4.1
0xa6efb3  stloc.0
0xa6efb4  ldarg.0
0xa6efb5  ldstr    aConfigurationS_40// "configuration/system.webServer/handlers"...
0xa6efba  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6efbf  stloc.1
0xa6efc0  ldloc.1
0xa6efc1  brtrue.s loc_A6EFD5
0xa6efc3  ldstr    aConfigurationS_39// "configuration/system.webServer/handlers"
0xa6efc8  ldarg.0
0xa6efc9  ldstr    aAddNameScripth// "<add name=\"ScriptHandlerFactory\" verb"...
0xa6efce  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6efd3  ldc.i4.1
0xa6efd4  stloc.0
0xa6efd5  ldarg.0
0xa6efd6  ldstr    aConfigurationS_41// "configuration/system.webServer/handlers"...
0xa6efdb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6efe0  stloc.1
0xa6efe1  ldloc.1
0xa6efe2  brtrue.s loc_A6EFF6
0xa6efe4  ldstr    aConfigurationS_39// "configuration/system.webServer/handlers"
0xa6efe9  ldarg.0
0xa6efea  ldstr    aAddNameScripth_0// "<add name=\"ScriptHandlerFactoryAppServ"...
0xa6efef  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6eff4  ldc.i4.1
0xa6eff5  stloc.0
0xa6eff6  ldarg.0
0xa6eff7  ldstr    aConfigurationS_42// "configuration/system.webServer/handlers"...
0xa6effc  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa6f001  stloc.1
0xa6f002  ldloc.1
0xa6f003  brtrue.s loc_A6F017
0xa6f005  ldstr    aConfigurationS_39// "configuration/system.webServer/handlers"
0xa6f00a  ldarg.0
0xa6f00b  ldstr    aAddNameScriptr// "<add name=\"ScriptResource\" preConditi"...
0xa6f010  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa6f015  ldc.i4.1
0xa6f016  stloc.0
0xa6f017  ldloc.0
0xa6f018  ret
```
