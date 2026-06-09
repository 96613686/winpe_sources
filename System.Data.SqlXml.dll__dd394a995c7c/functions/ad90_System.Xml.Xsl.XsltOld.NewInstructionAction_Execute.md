# System.Xml.Xsl.XsltOld.NewInstructionAction::Execute

- ea: `0xad90`
- end: `0xaded`
- name: `System.Xml.Xsl.XsltOld.NewInstructionAction::Execute`
- size: `93`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x54960`

## callees

- `0x4160`
- `0x4170`
- `0x43e0`
- `0xad90`
- `0xcb20`

## string_xrefs

- `0xada7`: `Xslt_UnknownExtensionElement`

## pseudocode

```c

```

## disassembly

```asm
0xad90  ldarg.2
0xad91  callvirt instance int32 System.Xml.Xsl.XsltOld.ActionFrame::get_State()
0xad96  stloc.0
0xad97  ldloc.0
0xad98  brfalse.s loc_AD9F
0xad9a  ldloc.0
0xad9b  ldc.i4.1
0xad9c  beq.s    loc_ADE6
0xad9e  ret
0xad9f  ldarg.0
0xada0  ldfld    bool System.Xml.Xsl.XsltOld.NewInstructionAction::fallback
0xada5  brtrue.s loc_ADC1
0xada7  ldstr    aXsltUnknownext// "Xslt_UnknownExtensionElement"
0xadac  ldc.i4.1
0xadad  newarr   [mscorlib]System.String
0xadb2  dup
0xadb3  ldc.i4.0
0xadb4  ldarg.0
0xadb5  ldfld    string System.Xml.Xsl.XsltOld.NewInstructionAction::name
0xadba  stelem.ref
0xadbb  call     class [System.Xml]System.Xml.Xsl.XsltException [System.Xml]System.Xml.Xsl.XsltException::Create(string, string[])
0xadc0  throw
0xadc1  ldarg.0
0xadc2  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.ContainerAction::containedActions
0xadc7  brfalse.s loc_ADE6
0xadc9  ldarg.0
0xadca  ldfld    class [mscorlib]System.Collections.ArrayList System.Xml.Xsl.XsltOld.ContainerAction::containedActions
0xadcf  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0xadd4  ldc.i4.0
0xadd5  ble.s    loc_ADE6
0xadd7  ldarg.1
0xadd8  ldarg.2
0xadd9  callvirt instance void System.Xml.Xsl.XsltOld.Processor::PushActionFrame(class System.Xml.Xsl.XsltOld.ActionFrame container)
0xadde  ldarg.2
0xaddf  ldc.i4.1
0xade0  callvirt instance void System.Xml.Xsl.XsltOld.ActionFrame::set_State(int32 value)
0xade5  ret
0xade6  ldarg.2
0xade7  callvirt instance void System.Xml.Xsl.XsltOld.ActionFrame::Finished()
0xadec  ret
```
