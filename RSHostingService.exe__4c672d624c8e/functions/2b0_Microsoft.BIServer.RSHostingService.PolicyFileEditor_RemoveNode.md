# Microsoft.BIServer.RSHostingService.PolicyFileEditor::RemoveNode

- ea: `0x2b0`
- end: `0x2c6`
- name: `Microsoft.BIServer.RSHostingService.PolicyFileEditor::RemoveNode`
- size: `22`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x240`

## pseudocode

```c

```

## disassembly

```asm
0x2b0  ldarg.0
0x2b1  ldarg.1
0x2b2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2b7  stloc.0
0x2b8  ldloc.0
0x2b9  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::get_ParentNode()
0x2be  ldloc.0
0x2bf  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::RemoveChild(class [System.Xml]System.Xml.XmlNode)
0x2c4  pop
0x2c5  ret
```
