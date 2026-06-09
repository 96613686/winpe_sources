# Microsoft.BIServer.RSHostingService.PolicyFileEditor::AddNode

- ea: `0x2d0`
- end: `0x2fd`
- name: `Microsoft.BIServer.RSHostingService.PolicyFileEditor::AddNode`
- size: `45`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x240`

## callees

- `0x300`

## pseudocode

```c

```

## disassembly

```asm
0x2d0  ldarg.0
0x2d1  ldarg.1
0x2d2  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::SelectSingleNode(string)
0x2d7  ldarg.0
0x2d8  ldarg.2
0x2d9  call     class [System.Xml]System.Xml.XmlDocumentFragment Microsoft.BIServer.RSHostingService.PolicyFileEditor::CreateElement(class [System.Xml]System.Xml.XmlDocument xmlDocument, string element)
0x2de  callvirt instance class [System.Xml]System.Xml.XmlNode [System.Xml]System.Xml.XmlNode::AppendChild(class [System.Xml]System.Xml.XmlNode)
0x2e3  pop
0x2e4  ldstr    aAddedEntryToPo// "Added entry to policy file. {0} - {1}"
0x2e9  ldc.i4.2
0x2ea  newarr   [mscorlib]System.Object
0x2ef  dup
0x2f0  ldc.i4.0
0x2f1  ldarg.1
0x2f2  stelem.ref
0x2f3  dup
0x2f4  ldc.i4.1
0x2f5  ldarg.2
0x2f6  stelem.ref
0x2f7  call     void [Microsoft.BIServer.HostingEnvironment]Microsoft.BIServer.HostingEnvironment.Logger::Info(string, object[])
0x2fc  ret
```
