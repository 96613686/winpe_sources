# MS.Internal.Printing.Configuration.PTFeatureNode::GetOptionName

- ea: `0x16ed0`
- end: `0x16f25`
- name: `MS.Internal.Printing.Configuration.PTFeatureNode::GetOptionName`
- size: `85`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0xf660`
- `0xf6c0`
- `0x16c10`

## callees

- `0x16ed0`
- `0x17200`
- `0x17220`
- `0x17ca0`
- `0x17cd0`
- `0x18220`

## string_xrefs

- `0x16f0b`: `http://schemas.microsoft.com/windows/2003/08/printing/printschemakeywords`

## pseudocode

```c

```

## disassembly

```asm
0x16ed0  ldarg.0
0x16ed1  call     instance class MS.Internal.Printing.Configuration.PrintTicketFeature MS.Internal.Printing.Configuration.PTFeatureNode::get_OwnerFeature()
0x16ed6  ldfld    class MS.Internal.Printing.Configuration.InternalPrintTicket MS.Internal.Printing.Configuration.PrintTicketFeature::_ownerPrintTicket
0x16edb  stloc.0
0x16edc  ldnull
0x16edd  stloc.1
0x16ede  ldarg.1
0x16edf  ldc.i4.0
0x16ee0  stind.i1
0x16ee1  ldarg.0
0x16ee2  call     instance class [System.Xml]System.Xml.XmlElement MS.Internal.Printing.Configuration.PTFeatureNode::GetFirstOption()
0x16ee7  stloc.2
0x16ee8  ldloc.2
0x16ee9  brfalse.s loc_16F23
0x16eeb  ldloc.2
0x16eec  ldstr    aName// "name"
0x16ef1  ldstr    asc_41B18// ""
0x16ef6  callvirt instance string [System.Xml]System.Xml.XmlElement::GetAttribute(string, string)
0x16efb  stloc.3
0x16efc  ldloc.3
0x16efd  brfalse.s loc_16F23
0x16eff  ldloc.0
0x16f00  callvirt instance class [System.Xml]System.Xml.XmlDocument MS.Internal.Printing.Configuration.InternalPrintTicket::get_XmlDoc()
0x16f05  ldloc.3
0x16f06  call     string MS.Internal.Printing.Configuration.XmlDocQName::GetURI(class [System.Xml]System.Xml.XmlDocument xmlDoc, string QName)
0x16f0b  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/windows/20"...
0x16f10  call     bool [mscorlib]System.String::op_Equality(string, string)
0x16f15  brfalse.s loc_16F20
0x16f17  ldloc.3
0x16f18  call     string MS.Internal.Printing.Configuration.XmlDocQName::GetLocalName(string QName)
0x16f1d  stloc.1
0x16f1e  br.s     loc_16F23
0x16f20  ldarg.1
0x16f21  ldc.i4.1
0x16f22  stind.i1
0x16f23  ldloc.1
0x16f24  ret
```
