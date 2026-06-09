# Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::UpdateMachineKey

- ea: `0x40`
- end: `0x124`
- name: `Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::UpdateMachineKey`
- size: `228`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x920`

## callees

- `0x40`
- `0x130`

## string_xrefs

- `0x44`: `/configuration/system.web/machineKey`
- `0xa6`: `/configuration/system.web/machineKey`
- `0x68`: `Removed machine key settings`
- `0x79`: `/configuration/system.web`
- `0x94`: `/configuration`
- `0x114`: `Updated machine key settings`

## pseudocode

```c

```

## disassembly

```asm
0x40  ldarg.2
0x41  brtrue.s loc_78
0x43  ldarg.1
0x44  ldstr    aConfigurationS// "/configuration/system.web/machineKey"
0x49  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x4e  stloc.0
0x4f  ldloc.0
0x50  brfalse  loc_123
0x55  ldloc.0
0x56  callvirt instance void [System.Xml]System.Xml.XmlNode::RemoveAll()
0x5b  ldloc.0
0x5c  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x61  ldloc.0
0x62  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x67  pop
0x68  ldstr    aRemovedMachine// "Removed machine key settings"
0x6d  call     T0x2B000001
0x72  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x77  ret
0x78  ldarg.1
0x79  ldstr    aConfigurationS_0// "/configuration/system.web"
0x7e  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x83  stloc.1
0x84  ldloc.1
0x85  brtrue.s loc_A5
0x87  ldarg.1
0x88  ldstr    aSystemWeb// "system.web"
0x8d  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x92  stloc.1
0x93  ldarg.1
0x94  ldstr    aConfiguration// "/configuration"
0x99  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x9e  ldloc.1
0x9f  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xa4  pop
0xa5  ldarg.1
0xa6  ldstr    aConfigurationS// "/configuration/system.web/machineKey"
0xab  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0xb0  stloc.2
0xb1  ldloc.2
0xb2  brtrue.s loc_C8
0xb4  ldarg.1
0xb5  ldstr    aMachinekey// "machineKey"
0xba  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0xbf  stloc.2
0xc0  ldloc.1
0xc1  ldloc.2
0xc2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0xc7  pop
0xc8  ldarg.0
0xc9  ldarg.1
0xca  ldloc.2
0xcb  ldstr    aValidationkey// "validationKey"
0xd0  ldarg.2
0xd1  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings::get_ValidationKey()
0xd6  call     instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute(class [System.Xml]System.Xml.XmlDocument document, class [System.Xml]System.Xml.XmlNode node, string attributeName, string attributeValue)
0xdb  ldarg.0
0xdc  ldarg.1
0xdd  ldloc.2
0xde  ldstr    aDecryptionkey// "decryptionKey"
0xe3  ldarg.2
0xe4  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings::get_DecryptionKey()
0xe9  call     instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute(class [System.Xml]System.Xml.XmlDocument document, class [System.Xml]System.Xml.XmlNode node, string attributeName, string attributeValue)
0xee  ldarg.0
0xef  ldarg.1
0xf0  ldloc.2
0xf1  ldstr    aValidation// "validation"
0xf6  ldarg.2
0xf7  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings::get_Validation()
0xfc  call     instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute(class [System.Xml]System.Xml.XmlDocument document, class [System.Xml]System.Xml.XmlNode node, string attributeName, string attributeValue)
0x101  ldarg.0
0x102  ldarg.1
0x103  ldloc.2
0x104  ldstr    aDecryption// "decryption"
0x109  ldarg.2
0x10a  callvirt instance string [Microsoft.BIServer.Configuration]Microsoft.BIServer.Configuration.MachineKeySettings::get_Decryption()
0x10f  call     instance void Microsoft.BIServer.RSHostingService.ConfigurationFileEditor::SetAttribute(class [System.Xml]System.Xml.XmlDocument document, class [System.Xml]System.Xml.XmlNode node, string attributeName, string attributeValue)
0x114  ldstr    aUpdatedMachine// "Updated machine key settings"
0x119  call     T0x2B000001
0x11e  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x123  ret
```
