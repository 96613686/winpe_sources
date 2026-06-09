# System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadXML

- ea: `0x23630`
- end: `0x236a6`
- name: `System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadXML`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x21b30`

## callees

- `0x1ee90`
- `0x1ef70`
- `0x1ff20`
- `0x23630`
- `0x236b0`
- `0x23870`
- `0x23960`

## string_xrefs

- `0x23633`: `reader`

## pseudocode

```c

```

## disassembly

```asm
0x23630  ldarg.1
0x23631  brtrue.s loc_2363E
0x23633  ldstr    aReader// "reader"
0x23638  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2363d  throw
0x2363e  ldarg.1
0x2363f  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x23644  ldc.i4.1
0x23645  bne.un.s loc_23659
0x23647  ldarg.1
0x23648  callvirt instance string [System.Xml]System.Xml.XmlReader::get_Name()
0x2364d  call     string System.Windows.Xps.Packaging.XpsS0Markup::get_SignatureDefinition()
0x23652  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x23657  brfalse.s loc_23669
0x23659  ldstr    aReachpackaging_12// "ReachPackaging_NotSignatureDefinitionEl"...
0x2365e  call     string System.Windows.Xps.SR::Get(string id)
0x23663  newobj   instance void System.Windows.Xps.XpsPackagingException::.ctor(string message)
0x23668  throw
0x23669  ldc.i4.0
0x2366a  stloc.0
0x2366b  ldarg.0
0x2366c  ldarg.1
0x2366d  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadAttributes(class [System.Xml]System.Xml.XmlReader reader)
0x23672  br.s     loc_2369A
0x23674  ldarg.1
0x23675  callvirt instance valuetype [System.Xml]System.Xml.XmlNodeType [System.Xml]System.Xml.XmlReader::get_NodeType()
0x2367a  stloc.1
0x2367b  ldloc.1
0x2367c  ldc.i4.1
0x2367d  beq.s    loc_23686
0x2367f  ldloc.1
0x23680  ldc.i4.s 0xF
0x23682  beq.s    loc_2368F
0x23684  br.s     loc_2369A
0x23686  ldarg.0
0x23687  ldarg.1
0x23688  call     instance void System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadElement(class [System.Xml]System.Xml.XmlReader reader)
0x2368d  br.s     loc_2369A
0x2368f  ldarg.0
0x23690  ldarg.1
0x23691  call     instance bool System.Windows.Xps.Packaging.XpsSignatureDefinition::ReadEndElement(class [System.Xml]System.Xml.XmlReader reader)
0x23696  brfalse.s loc_2369A
0x23698  ldc.i4.1
0x23699  stloc.0
0x2369a  ldloc.0
0x2369b  brtrue.s loc_236A5
0x2369d  ldarg.1
0x2369e  callvirt instance bool [System.Xml]System.Xml.XmlReader::Read()
0x236a3  brtrue.s loc_23674
0x236a5  ret
```
