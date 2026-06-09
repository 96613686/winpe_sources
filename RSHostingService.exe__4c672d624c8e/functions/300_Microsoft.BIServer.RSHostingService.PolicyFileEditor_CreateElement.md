# Microsoft.BIServer.RSHostingService.PolicyFileEditor::CreateElement

- ea: `0x300`
- end: `0x30e`
- name: `Microsoft.BIServer.RSHostingService.PolicyFileEditor::CreateElement`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x2d0`

## pseudocode

```c

```

## disassembly

```asm
0x300  ldarg.0
0x301  callvirt instance class [System.Xml]System.Xml.XmlDocumentFragment [System.Xml]System.Xml.XmlDocument::CreateDocumentFragment()
0x306  dup
0x307  ldarg.1
0x308  callvirt instance void [System.Xml]System.Xml.XmlNode::set_InnerXml(string)
0x30d  ret
```
