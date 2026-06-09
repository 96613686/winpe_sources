# System.Web.UI.Design.TemplateDefinition::.ctor_2

- ea: `0x10270`
- end: `0x102be`
- name: `System.Web.UI.Design.TemplateDefinition::.ctor_2`
- size: `78`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x10250`
- `0x10260`
- `0x4bfa0`

## callees

- `0xaf50`
- `0x10270`

## string_xrefs

- `0x10285`: `templatePropertyName`
- `0x10293`: `templatedObject`

## pseudocode

```c

```

## disassembly

```asm
0x10270  ldarg.0
0x10271  ldarg.1
0x10272  ldarg.2
0x10273  call     instance void System.Web.UI.Design.DesignerObject::.ctor(class System.Web.UI.Design.ControlDesigner designer, string name)
0x10278  ldarg.s  4
0x1027a  brfalse.s loc_10285
0x1027c  ldarg.s  4
0x1027e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10283  brtrue.s loc_10290
0x10285  ldstr    aTemplateproper// "templatePropertyName"
0x1028a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1028f  throw
0x10290  ldarg.3
0x10291  brtrue.s loc_1029E
0x10293  ldstr    aTemplatedobjec// "templatedObject"
0x10298  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1029d  throw
0x1029e  ldarg.0
0x1029f  ldarg.s  6
0x102a1  stfld    bool System.Web.UI.Design.TemplateDefinition::_serverControlsOnly
0x102a6  ldarg.0
0x102a7  ldarg.s  5
0x102a9  stfld    class [System.Web]System.Web.UI.WebControls.Style System.Web.UI.Design.TemplateDefinition::_style
0x102ae  ldarg.0
0x102af  ldarg.3
0x102b0  stfld    object System.Web.UI.Design.TemplateDefinition::_templatedObject
0x102b5  ldarg.0
0x102b6  ldarg.s  4
0x102b8  stfld    string System.Web.UI.Design.TemplateDefinition::_templatePropertyName
0x102bd  ret
```
