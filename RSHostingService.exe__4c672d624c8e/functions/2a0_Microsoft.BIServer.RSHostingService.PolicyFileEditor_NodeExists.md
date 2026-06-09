# Microsoft.BIServer.RSHostingService.PolicyFileEditor::NodeExists

- ea: `0x2a0`
- end: `0x2b0`
- name: `Microsoft.BIServer.RSHostingService.PolicyFileEditor::NodeExists`
- size: `16`
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
0x2a0  ldarg.0
0x2a1  ldarg.1
0x2a2  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x2a7  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x2ac  ldc.i4.0
0x2ad  cgt
0x2af  ret
```
