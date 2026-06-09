# Microsoft.SharePoint.Upgrade.UpdateWebConfigForIIS7::Upgrade

- ea: `0xa70300`
- end: `0xa7065f`
- name: `Microsoft.SharePoint.Upgrade.UpdateWebConfigForIIS7::Upgrade`
- size: `863`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x189150`
- `0x19bc40`
- `0x22dc00`
- `0x22f280`
- `0xa45800`
- `0xa4f220`
- `0xa6d090`
- `0xa6d240`
- `0xa70300`

## string_xrefs

- `0xa704c3`: `configuration`
- `0xa70362`: `configuration/system.webServer/modules`
- `0xa70395`: `configuration/system.webServer/modules`
- `0xa703c8`: `configuration/system.webServer/modules`
- `0xa703fb`: `configuration/system.webServer/modules`
- `0xa7047c`: `configuration/system.webServer/modules`
- `0xa705d4`: `configuration/system.webServer/modules`
- `0xa70608`: `configuration/system.webServer/modules`
- `0xa7032f`: `configuration/system.webServer/handlers`
- `0xa70417`: `Added the entry to remove the Session module.`
- `0xa70318`: `Owssvr handler web.config entry was added or modified.`
- `0xa7034b`: `Added the handler entry to remove the OPTIONSVerbHandler.`
- `0xa70367`: `AnonymousIdentification`
- `0xa7037e`: `Added the entry to remove the AnonymousIdentification module.`
- `0xa703b1`: `Added the entry to remove the FileAuthorization module.`
- `0xa703e4`: `Added the entry to remove the Profile.`
- `0xa70433`: `configuration/system.webServer/modules/add[@name='{0}']`
- `0xa70498`: `Added the module entry for owssvr.dll to the web.config.`
- `0xa704af`: `configuration/system.serviceModel`
- `0xa704bd`: `<system.serviceModel>\n                      <serviceHostingEnvironment aspNetCompatibilityEnabled="true" />\n                  </system.serviceModel>`
- `0xa704df`: `Add the system.ServiceModel section`
- `0xa704f6`: `serviceHostingEnvironment`
- `0xa7050b`: `configuration/system.`
- `0xa70516`: `<serviceHostingEnvironment aspNetCompatibilityEnabled="true" />`
- `0xa7052b`: `Added the system.ServiceModel section`
- `0xa70540`: `aspNetCompatibilityEnabled`
- `0xa70558`: `aspNetCompatibilityEnabled`
- `0xa70572`: `Enabled the aspNetCompatibilityEnabled property.`
- `0xa70589`: `configuration/system.webServer/modules/add[@name='SPRequestModule']`
- `0xa705f1`: `Added the module entry for SPRequestModule to the web.config.`
- `0xa7064d`: `Set the runAllManagedModulesForAllRequests property to true for the modules node in the web.config.`

## pseudocode

```c

```

## disassembly

```asm
0xa70300  ldarg.0
0xa70301  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70306  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureOwssvrHandler(class [System.Xml]System.Xml.XmlDocument xdWebConfig)
0xa7030b  brfalse.s loc_A70329
0xa7030d  ldarg.0
0xa7030e  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70313  ldc.i4   0x25A584
0xa70318  ldstr    aOwssvrHandlerW// "Owssvr handler web.config entry was add"...
0xa7031d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70322  ldarg.0
0xa70323  ldc.i4.1
0xa70324  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa70329  ldarg.0
0xa7032a  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa7032f  ldstr    aConfigurationS_39// "configuration/system.webServer/handlers"
0xa70334  ldstr    aOptionsverbhan// "OPTIONSVerbHandler"
0xa70339  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureRemoveEntry(class [System.Xml]System.Xml.XmlDocument xd, string xpath, string name)
0xa7033e  brfalse.s loc_A7035C
0xa70340  ldarg.0
0xa70341  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70346  ldc.i4   0x25A585
0xa7034b  ldstr    aAddedTheHandle// "Added the handler entry to remove the O"...
0xa70350  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70355  ldarg.0
0xa70356  ldc.i4.1
0xa70357  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa7035c  ldarg.0
0xa7035d  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70362  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa70367  ldstr    aAnonymousident// "AnonymousIdentification"
0xa7036c  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureRemoveEntry(class [System.Xml]System.Xml.XmlDocument xd, string xpath, string name)
0xa70371  brfalse.s loc_A7038F
0xa70373  ldarg.0
0xa70374  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70379  ldc.i4   0x25A586
0xa7037e  ldstr    aAddedTheEntryT_0// "Added the entry to remove the Anonymous"...
0xa70383  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70388  ldarg.0
0xa70389  ldc.i4.1
0xa7038a  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa7038f  ldarg.0
0xa70390  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70395  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa7039a  ldstr    aFileauthorizat// "FileAuthorization"
0xa7039f  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureRemoveEntry(class [System.Xml]System.Xml.XmlDocument xd, string xpath, string name)
0xa703a4  brfalse.s loc_A703C2
0xa703a6  ldarg.0
0xa703a7  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa703ac  ldc.i4   0x25A587
0xa703b1  ldstr    aAddedTheEntryT_1// "Added the entry to remove the FileAutho"...
0xa703b6  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa703bb  ldarg.0
0xa703bc  ldc.i4.1
0xa703bd  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa703c2  ldarg.0
0xa703c3  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa703c8  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa703cd  ldstr    aProfile// "Profile"
0xa703d2  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureRemoveEntry(class [System.Xml]System.Xml.XmlDocument xd, string xpath, string name)
0xa703d7  brfalse.s loc_A703F5
0xa703d9  ldarg.0
0xa703da  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa703df  ldc.i4   0x25A588
0xa703e4  ldstr    aAddedTheEntryT_2// "Added the entry to remove the Profile."
0xa703e9  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa703ee  ldarg.0
0xa703ef  ldc.i4.1
0xa703f0  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa703f5  ldarg.0
0xa703f6  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa703fb  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa70400  ldstr    aSession_0// "Session"
0xa70405  call     bool Microsoft.SharePoint.Administration.SPAspConfigurationFile::EnsureRemoveEntry(class [System.Xml]System.Xml.XmlDocument xd, string xpath, string name)
0xa7040a  brfalse.s loc_A70428
0xa7040c  ldarg.0
0xa7040d  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70412  ldc.i4   0x25A589
0xa70417  ldstr    aAddedTheEntryT// "Added the entry to remove the Session m"...
0xa7041c  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70421  ldarg.0
0xa70422  ldc.i4.1
0xa70423  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa70428  ldarg.0
0xa70429  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa7042e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa70433  ldstr    aConfigurationS_49// "configuration/system.webServer/modules/"...
0xa70438  ldc.i4.1
0xa70439  newarr   [mscorlib]System.Object
0xa7043e  stloc.s  0xA
0xa70440  ldloc.s  0xA
0xa70442  ldc.i4.0
0xa70443  ldstr    aSharepoint14mo// "SharePoint14Module"
0xa70448  stelem.ref
0xa70449  ldloc.s  0xA
0xa7044b  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa70450  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa70455  stloc.0
0xa70456  ldloc.0
0xa70457  brtrue.s loc_A704A9
0xa70459  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa7045e  ldstr    aAddName0Precon// "<add name=\"{0}\" preCondition=\"integr"...
0xa70463  ldc.i4.1
0xa70464  newarr   [mscorlib]System.Object
0xa70469  stloc.s  0xB
0xa7046b  ldloc.s  0xB
0xa7046d  ldc.i4.0
0xa7046e  ldstr    aSharepoint14mo// "SharePoint14Module"
0xa70473  stelem.ref
0xa70474  ldloc.s  0xB
0xa70476  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa7047b  stloc.1
0xa7047c  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa70481  ldarg.0
0xa70482  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70487  ldloc.1
0xa70488  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa7048d  ldarg.0
0xa7048e  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70493  ldc.i4   0x25A58A
0xa70498  ldstr    aAddedTheModule// "Added the module entry for owssvr.dll t"...
0xa7049d  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa704a2  ldarg.0
0xa704a3  ldc.i4.1
0xa704a4  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa704a9  ldarg.0
0xa704aa  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa704af  ldstr    aConfigurationS_50// "configuration/system.serviceModel"
0xa704b4  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa704b9  stloc.2
0xa704ba  ldloc.2
0xa704bb  brtrue.s loc_A704F5
0xa704bd  ldstr    aSystemServicem_2// "<system.serviceModel>\r\n              "...
0xa704c2  stloc.3
0xa704c3  ldstr    aConfiguration// "configuration"
0xa704c8  ldarg.0
0xa704c9  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa704ce  ldloc.3
0xa704cf  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa704d4  ldarg.0
0xa704d5  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa704da  ldc.i4   0x25A58B
0xa704df  ldstr    aAddTheSystemSe// "Add the system.ServiceModel section"
0xa704e4  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa704e9  ldarg.0
0xa704ea  ldc.i4.1
0xa704eb  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa704f0  br       loc_A70583
0xa704f5  ldloc.2
0xa704f6  ldstr    aServicehosting// "serviceHostingEnvironment"
0xa704fb  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa70500  isinst   [System.Xml]System.Xml.XmlElement
0xa70505  stloc.s  4
0xa70507  ldloc.s  4
0xa70509  brtrue.s loc_A7053E
0xa7050b  ldstr    aConfigurationS_51// "configuration/system."
0xa70510  ldarg.0
0xa70511  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70516  ldstr    aServicehosting_0// "<serviceHostingEnvironment aspNetCompat"...
0xa7051b  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa70520  ldarg.0
0xa70521  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70526  ldc.i4   0x25A58C
0xa7052b  ldstr    aAddedTheSystem// "Added the system.ServiceModel section"
0xa70530  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70535  ldarg.0
0xa70536  ldc.i4.1
0xa70537  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa7053c  br.s     loc_A70583
0xa7053e  ldloc.s  4
0xa70540  ldstr    aAspnetcompatib// "aspNetCompatibilityEnabled"
0xa70545  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0xa7054a  ldstr    aTrue// "true"
0xa7054f  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsCompareStrings(string str1, string str2)
0xa70554  brtrue.s loc_A70583
0xa70556  ldloc.s  4
0xa70558  ldstr    aAspnetcompatib// "aspNetCompatibilityEnabled"
0xa7055d  ldstr    aTrue// "true"
0xa70562  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa70567  ldarg.0
0xa70568  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa7056d  ldc.i4   0x25A58D
0xa70572  ldstr    aEnabledTheAspn// "Enabled the aspNetCompatibilityEnabled "...
0xa70577  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa7057c  ldarg.0
0xa7057d  ldc.i4.1
0xa7057e  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa70583  ldarg.0
0xa70584  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70589  ldstr    aConfigurationS_52// "configuration/system.webServer/modules/"...
0xa7058e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa70593  stloc.s  5
0xa70595  ldloc.s  5
0xa70597  brtrue.s loc_A70602
0xa70599  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xa7059e  stloc.s  6
0xa705a0  ldloc.s  6
0xa705a2  ldstr    aMicrosoftShare_302// "Microsoft.SharePoint.ApplicationRuntime"...
0xa705a7  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0xa705ac  stloc.s  7
0xa705ae  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xa705b3  ldstr    aAddNameSpreque_2// "<add name=\"SPRequestModule\" preCondit"...
0xa705b8  ldc.i4.1
0xa705b9  newarr   [mscorlib]System.Object
0xa705be  stloc.s  0xC
0xa705c0  ldloc.s  0xC
0xa705c2  ldc.i4.0
0xa705c3  ldloc.s  7
0xa705c5  callvirt instance string [mscorlib]System.Type::get_AssemblyQualifiedName()
0xa705ca  stelem.ref
0xa705cb  ldloc.s  0xC
0xa705cd  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xa705d2  stloc.s  8
0xa705d4  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa705d9  ldarg.0
0xa705da  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa705df  ldloc.s  8
0xa705e1  call     void Microsoft.SharePoint.Utilities.SPUtility::AppendXmlElementToXmlDocument(string xpath, class [System.Xml]System.Xml.XmlDocument xd, string xml)
0xa705e6  ldarg.0
0xa705e7  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa705ec  ldc.i4   0x25A58E
0xa705f1  ldstr    aAddedTheModule_0// "Added the module entry for SPRequestMod"...
0xa705f6  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa705fb  ldarg.0
0xa705fc  ldc.i4.1
0xa705fd  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa70602  ldarg.0
0xa70603  call     instance class [System.Xml]System.Xml.XmlDocument Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::get_AppWebConfig()
0xa70608  ldstr    aConfigurationS_0// "configuration/system.webServer/modules"
0xa7060d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xa70612  isinst   [System.Xml]System.Xml.XmlElement
0xa70617  stloc.s  9
0xa70619  ldloc.s  9
0xa7061b  ldstr    aRunallmanagedm// "runAllManagedModulesForAllRequests"
0xa70620  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string)
0xa70625  ldstr    aTrue// "true"
0xa7062a  call     bool Microsoft.SharePoint.Utilities.SPUtility::StsCompareStrings(string str1, string str2)
0xa7062f  brtrue.s loc_A7065E
0xa70631  ldloc.s  9
0xa70633  ldstr    aRunallmanagedm// "runAllManagedModulesForAllRequests"
0xa70638  ldstr    aTrue// "true"
0xa7063d  callvirt instance void [System.Xml]System.Xml.XmlElement::SetAttribute(string, string)
0xa70642  ldarg.0
0xa70643  call     instance class Microsoft.SharePoint.Upgrade.SPLog Microsoft.SharePoint.Upgrade.SPAction::get_Log()
0xa70648  ldc.i4   0x25A58F
0xa7064d  ldstr    aSetTheRunallma// "Set the runAllManagedModulesForAllReque"...
0xa70652  callvirt instance void Microsoft.SharePoint.Upgrade.SPLog::InfoTag(unsigned int32 tagID, string output)
0xa70657  ldarg.0
0xa70658  ldc.i4.1
0xa70659  call     instance void Microsoft.SharePoint.Upgrade.SPWebConfigIisSiteAction::set_AppWebConfigModified(bool value)
0xa7065e  ret
```
