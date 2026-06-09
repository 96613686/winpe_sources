# MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode

- ea: `0x16bc0`
- end: `0x16c09`
- name: `MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode`
- size: `73`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0xf660`
- `0xf6c0`
- `0x16b10`
- `0x16bc0`
- `0x16c10`
- `0x16d00`

## callees

- `0x16bc0`
- `0x16e80`
- `0x17230`
- `0x18220`

## pseudocode

```c

```

## disassembly

```asm
0x16bc0  ldnull
0x16bc1  stloc.0
0x16bc2  ldarg.0
0x16bc3  ldfld    class MS.Internal.Printing.Configuration.PrintTicketFeature MS.Internal.Printing.Configuration.PrintTicketFeature::_parentFeature
0x16bc8  brfalse.s loc_16BF0
0x16bca  ldarg.0
0x16bcb  ldfld    class MS.Internal.Printing.Configuration.PrintTicketFeature MS.Internal.Printing.Configuration.PrintTicketFeature::_parentFeature
0x16bd0  callvirt instance class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode()
0x16bd5  brfalse.s loc_16C07
0x16bd7  ldarg.0
0x16bd8  ldarg.0
0x16bd9  ldfld    class MS.Internal.Printing.Configuration.PrintTicketFeature MS.Internal.Printing.Configuration.PrintTicketFeature::_parentFeature
0x16bde  callvirt instance class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PrintTicketFeature::get_FeatureNode()
0x16be3  callvirt instance class [System.Xml]System.Xml.XmlElement MS.Internal.Printing.Configuration.PTFeatureNode::get_FeatureElement()
0x16be8  call     class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PTFeatureNode::GetFeatureNode(class MS.Internal.Printing.Configuration.PrintTicketFeature ptFeature, class [System.Xml]System.Xml.XmlElement parentElement)
0x16bed  stloc.0
0x16bee  br.s     loc_16C07
0x16bf0  ldarg.0
0x16bf1  ldarg.0
0x16bf2  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket MS.Internal.Printing.Configuration.PrintTicketFeature::_ownerPrintTicket
0x16bf7  callvirt instance class [System.Xml]System.Xml.XmlDocument MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlDoc()
0x16bfc  callvirt instance class [System.Xml]System.Xml.XmlElement [System.Xml]System.Xml.XmlDocument::get_DocumentElement()
0x16c01  call     class MS.Internal.Printing.Configuration.PTFeatureNode MS.Internal.Printing.Configuration.PTFeatureNode::GetFeatureNode(class MS.Internal.Printing.Configuration.PrintTicketFeature ptFeature, class [System.Xml]System.Xml.XmlElement parentElement)
0x16c06  stloc.0
0x16c07  ldloc.0
0x16c08  ret
```
