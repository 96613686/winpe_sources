# System.Deployment.Application.ManifestGenerator::AddFile

- ea: `0x19080`
- end: `0x190b3`
- name: `System.Deployment.Application.ManifestGenerator::AddFile`
- size: `51`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x19040`

## callees

- `0x24780`

## string_xrefs

- `0x19086`: `urn:schemas-microsoft-com:asm.v1`

## pseudocode

```c

```

## disassembly

```asm
0x19080  ldarg.0
0x19081  ldstr    aFile_0// "file"
0x19086  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:asm.v1"
0x1908b  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::CreateElement(string, string)
0x19090  stloc.0
0x19091  ldarg.1
0x19092  ldloc.0
0x19093  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x19098  pop
0x19099  ldloc.0
0x1909a  ldstr    aName// "name"
0x1909f  ldnull
0x190a0  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlElement::SetAttributeNode(string, string)
0x190a5  stloc.1
0x190a6  ldloc.1
0x190a7  ldarg.2
0x190a8  callvirt instance string System.Deployment.Application.Manifest.File::get_Name()
0x190ad  callvirt instance void [System.Xml]System.Xml.XmlNode::set_Value(string)
0x190b2  ret
```
