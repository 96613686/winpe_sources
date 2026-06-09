# Microsoft.BIServer.RSHostingService.PolicyFileEditor::Upgrade

- ea: `0x240`
- end: `0x293`
- name: `Microsoft.BIServer.RSHostingService.PolicyFileEditor::Upgrade`
- size: `83`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1a0`

## callees

- `0x240`
- `0x2a0`
- `0x2b0`
- `0x2d0`

## string_xrefs

- `0x241`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup/CodeGroup[@Name='AppInsights_Strong_Name']`
- `0x24e`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup[@PermissionSetName='Execution'][@class='FirstMatchCodeGroup']`
- `0x283`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup[@PermissionSetName='Execution'][@class='FirstMatchCodeGroup']`
- `0x25e`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup/CodeGroup[@Name='OXML_SDK_Strong_Name']`
- `0x26b`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup/CodeGroup[@Name='OXML_SDK_Strong_Name']`
- `0x276`: `//configuration/mscorlib/security/policy/PolicyLevel/CodeGroup/CodeGroup/CodeGroup[@Name='DocFormatOpemXml_Strong_Name']`
- `0x288`: `\n                            <CodeGroup\n                                    class="UnionCodeGroup" \n                                    version = "1"\n                                    PermissionSetName = "FullTrust"\n                                    Name = "DocFormatOpemXml_Strong_Name"\n                                    Description = "Grants FullTrust to DocumentFormat.OpenXml">\n                            <IMembershipCondition\n                                    class="Str`

## pseudocode

```c

```

## disassembly

```asm
0x240  ldarg.0
0x241  ldstr    aConfigurationM// "//configuration/mscorlib/security/polic"...
0x246  call     bool Microsoft.BIServer.RSHostingService.PolicyFileEditor::NodeExists(class [System.Xml]System.Xml.XmlDocument configToModify, string path)
0x24b  brtrue.s loc_25D
0x24d  ldarg.0
0x24e  ldstr    aConfigurationM_0// "//configuration/mscorlib/security/polic"...
0x253  ldstr    aCodegroup// "\r\n                          <CodeGrou"...
0x258  call     void Microsoft.BIServer.RSHostingService.PolicyFileEditor::AddNode(class [System.Xml]System.Xml.XmlDocument configToModify, string path, string value)
0x25d  ldarg.0
0x25e  ldstr    aConfigurationM_1// "//configuration/mscorlib/security/polic"...
0x263  call     bool Microsoft.BIServer.RSHostingService.PolicyFileEditor::NodeExists(class [System.Xml]System.Xml.XmlDocument configToModify, string path)
0x268  brfalse.s loc_275
0x26a  ldarg.0
0x26b  ldstr    aConfigurationM_1// "//configuration/mscorlib/security/polic"...
0x270  call     void Microsoft.BIServer.RSHostingService.PolicyFileEditor::RemoveNode(class [System.Xml]System.Xml.XmlDocument configToModify, string path)
0x275  ldarg.0
0x276  ldstr    aConfigurationM_2// "//configuration/mscorlib/security/polic"...
0x27b  call     bool Microsoft.BIServer.RSHostingService.PolicyFileEditor::NodeExists(class [System.Xml]System.Xml.XmlDocument configToModify, string path)
0x280  brtrue.s loc_292
0x282  ldarg.0
0x283  ldstr    aConfigurationM_0// "//configuration/mscorlib/security/polic"...
0x288  ldstr    aCodegroup_0// "\r\n                            <CodeGr"...
0x28d  call     void Microsoft.BIServer.RSHostingService.PolicyFileEditor::AddNode(class [System.Xml]System.Xml.XmlDocument configToModify, string path, string value)
0x292  ret
```
