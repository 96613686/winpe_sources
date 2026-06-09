# System.Web.UI.Design.TemplateEditingService::CreateFrame_0

- ea: `0x10d60`
- end: `0x10dc4`
- name: `System.Web.UI.Design.TemplateEditingService::CreateFrame_0`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x10d50`

## callees

- `0x10440`
- `0x10d60`
- `0x10dd0`

## string_xrefs

- `0x10d8b`: `templateNames`
- `0x10da3`: `templateStyles`

## pseudocode

```c

```

## disassembly

```asm
0x10d60  ldarg.1
0x10d61  brtrue.s loc_10D6E
0x10d63  ldstr    aDesigner// "designer"
0x10d68  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10d6d  throw
0x10d6e  ldarg.2
0x10d6f  brfalse.s loc_10D79
0x10d71  ldarg.2
0x10d72  callvirt instance int32 [mscorlib]System.String::get_Length()
0x10d77  brtrue.s loc_10D84
0x10d79  ldstr    aFramename// "frameName"
0x10d7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10d83  throw
0x10d84  ldarg.3
0x10d85  brfalse.s loc_10D8B
0x10d87  ldarg.3
0x10d88  ldlen
0x10d89  brtrue.s loc_10D96
0x10d8b  ldstr    aTemplatenames// "templateNames"
0x10d90  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10d95  throw
0x10d96  ldarg.s  5
0x10d98  brfalse.s loc_10DAE
0x10d9a  ldarg.s  5
0x10d9c  ldlen
0x10d9d  conv.i4
0x10d9e  ldarg.3
0x10d9f  ldlen
0x10da0  conv.i4
0x10da1  beq.s    loc_10DAE
0x10da3  ldstr    aTemplatestyles// "templateStyles"
0x10da8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x10dad  throw
0x10dae  ldarg.0
0x10daf  ldarg.2
0x10db0  call     instance string System.Web.UI.Design.TemplateEditingService::CreateFrameName(string frameName)
0x10db5  starg.s  2
0x10db7  ldarg.1
0x10db8  ldarg.2
0x10db9  ldarg.3
0x10dba  ldarg.s  4
0x10dbc  ldarg.s  5
0x10dbe  newobj   instance void System.Web.UI.Design.TemplateEditingFrame::.ctor(class System.Web.UI.Design.TemplatedControlDesigner owner, string frameName, string[] templateNames, class [System.Web]System.Web.UI.WebControls.Style controlStyle, class [System.Web]System.Web.UI.WebControls.Style[] templateStyles)
0x10dc3  ret
```
