# Microsoft.Windows.Diagnosis.ManagedHost::ConvertScriptErrorToXml

- ea: `0x520`
- end: `0x78c`
- name: `Microsoft.Windows.Diagnosis.ManagedHost::ConvertScriptErrorToXml`
- size: `620`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x200`

## callees

- `0x520`

## pseudocode

```c

```

## disassembly

```asm
0x520  ldnull
0x521  stloc.0
0x522  ldnull
0x523  stloc.1
0x524  ldnull
0x525  stloc.2
0x526  ldnull
0x527  stloc.3
0x528  ldnull
0x529  stloc.s  4
0x52b  newobj   instance void [System.Xml]System.Xml.XmlDocument::.ctor()
0x530  stloc.0
0x531  ldloc.0
0x532  ldloc.0
0x533  ldstr    a10// "1.0"
0x538  ldstr    aUtf8// "UTF-8"
0x53d  ldnull
0x53e  callvirt instance class [System.Xml]System.Xml.XmlDeclaration [System.Xml]System.Xml.XmlDocument::CreateXmlDeclaration(string, string, string)
0x543  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x548  pop
0x549  ldloc.0
0x54a  ldstr    aScripterror// "ScriptError"
0x54f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x554  stloc.1
0x555  ldloc.0
0x556  ldstr    aData// "Data"
0x55b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x560  stloc.2
0x561  ldloc.0
0x562  ldstr    aId// "id"
0x567  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x56c  stloc.3
0x56d  ldloc.3
0x56e  ldstr    aScriptname// "ScriptName"
0x573  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x578  ldloc.2
0x579  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x57e  ldloc.3
0x57f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x584  pop
0x585  ldloc.0
0x586  ldstr    aName// "name"
0x58b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x590  stloc.3
0x591  ldarg.0
0x592  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x597  ldstr    aScriptname// "ScriptName"
0x59c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x5a1  stloc.s  4
0x5a3  ldloc.3
0x5a4  ldloc.s  4
0x5a6  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x5ab  ldloc.2
0x5ac  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x5b1  ldloc.3
0x5b2  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x5b7  pop
0x5b8  ldloc.2
0x5b9  ldloc.0
0x5ba  ldarg.1
0x5bb  callvirt instance class [System.Management.Automation]System.Management.Automation.InvocationInfo [System.Management.Automation]System.Management.Automation.ErrorRecord::get_InvocationInfo()
0x5c0  callvirt instance string [System.Management.Automation]System.Management.Automation.InvocationInfo::get_ScriptName()
0x5c5  call     string [mscorlib]System.IO.Path::GetFileName(string)
0x5ca  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x5cf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5d4  pop
0x5d5  ldloc.1
0x5d6  ldloc.2
0x5d7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x5dc  pop
0x5dd  ldloc.0
0x5de  ldstr    aData// "Data"
0x5e3  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x5e8  stloc.2
0x5e9  ldloc.0
0x5ea  ldstr    aId// "id"
0x5ef  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x5f4  stloc.3
0x5f5  ldloc.3
0x5f6  ldstr    aScriptline// "ScriptLine"
0x5fb  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x600  ldloc.2
0x601  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x606  ldloc.3
0x607  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x60c  pop
0x60d  ldloc.0
0x60e  ldstr    aName// "name"
0x613  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x618  stloc.3
0x619  ldarg.0
0x61a  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x61f  ldstr    aScriptline// "ScriptLine"
0x624  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x629  stloc.s  4
0x62b  ldloc.3
0x62c  ldloc.s  4
0x62e  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x633  ldloc.2
0x634  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x639  ldloc.3
0x63a  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x63f  pop
0x640  ldloc.2
0x641  ldloc.0
0x642  ldarg.1
0x643  callvirt instance class [System.Management.Automation]System.Management.Automation.InvocationInfo [System.Management.Automation]System.Management.Automation.ErrorRecord::get_InvocationInfo()
0x648  callvirt instance int32 [System.Management.Automation]System.Management.Automation.InvocationInfo::get_ScriptLineNumber()
0x64d  stloc.s  5
0x64f  ldloca.s 5
0x651  call     instance string [mscorlib]System.Int32::ToString()
0x656  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x65b  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x660  pop
0x661  ldloc.1
0x662  ldloc.2
0x663  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x668  pop
0x669  ldloc.0
0x66a  ldstr    aData// "Data"
0x66f  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x674  stloc.2
0x675  ldloc.0
0x676  ldstr    aId// "id"
0x67b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x680  stloc.3
0x681  ldloc.3
0x682  ldstr    aScriptcolumn// "ScriptColumn"
0x687  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x68c  ldloc.2
0x68d  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x692  ldloc.3
0x693  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x698  pop
0x699  ldloc.0
0x69a  ldstr    aName// "name"
0x69f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x6a4  stloc.3
0x6a5  ldarg.0
0x6a6  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x6ab  ldstr    aScriptcolumn// "ScriptColumn"
0x6b0  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x6b5  stloc.s  4
0x6b7  ldloc.3
0x6b8  ldloc.s  4
0x6ba  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x6bf  ldloc.2
0x6c0  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x6c5  ldloc.3
0x6c6  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x6cb  pop
0x6cc  ldloc.2
0x6cd  ldloc.0
0x6ce  ldarg.1
0x6cf  callvirt instance class [System.Management.Automation]System.Management.Automation.InvocationInfo [System.Management.Automation]System.Management.Automation.ErrorRecord::get_InvocationInfo()
0x6d4  callvirt instance int32 [System.Management.Automation]System.Management.Automation.InvocationInfo::get_OffsetInLine()
0x6d9  stloc.s  5
0x6db  ldloca.s 5
0x6dd  call     instance string [mscorlib]System.Int32::ToString()
0x6e2  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x6e7  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6ec  pop
0x6ed  ldloc.1
0x6ee  ldloc.2
0x6ef  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x6f4  pop
0x6f5  ldloc.0
0x6f6  ldstr    aData// "Data"
0x6fb  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string)
0x700  stloc.2
0x701  ldloc.0
0x702  ldstr    aId// "id"
0x707  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x70c  stloc.3
0x70d  ldloc.3
0x70e  ldstr    aScripterrortex// "ScriptErrorText"
0x713  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x718  ldloc.2
0x719  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x71e  ldloc.3
0x71f  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x724  pop
0x725  ldloc.0
0x726  ldstr    aName// "name"
0x72b  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlDocument::CreateAttribute(string)
0x730  stloc.3
0x731  ldarg.0
0x732  ldfld    class [mscorlib]System.Resources.ResourceManager Microsoft.Windows.Diagnosis.ManagedHost::m_ResourceManager
0x737  ldstr    aScripterrortex// "ScriptErrorText"
0x73c  callvirt instance string [mscorlib]System.Resources.ResourceManager::GetString(string)
0x741  stloc.s  4
0x743  ldloc.3
0x744  ldloc.s  4
0x746  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerText(string)
0x74b  ldloc.2
0x74c  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x751  ldloc.3
0x752  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::Append(class [System.Xml]System.Xml.XmlAttribute)
0x757  pop
0x758  ldloc.2
0x759  ldloc.0
0x75a  ldarg.1
0x75b  callvirt instance string [System.Management.Automation]System.Management.Automation.ErrorRecord::get_FullyQualifiedErrorId()
0x760  callvirt instance class [System.Xml]System.Xml.XmlText [System.Xml]System.Xml.XmlDocument::CreateTextNode(string)
0x765  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x76a  pop
0x76b  ldloc.1
0x76c  ldloc.2
0x76d  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x772  pop
0x773  ldloc.0
0x774  ldloc.1
0x775  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x77a  pop
0x77b  leave.s  loc_78A
0x77d  pop
0x77e  ldc.i4   0x803C0103
0x783  call     void [mscorlib]System.Runtime.InteropServices.Marshal::ThrowExceptionForHR(int32)
0x788  leave.s  loc_78A
0x78a  ldloc.0
0x78b  ret
```
