# System.Web.UI.Design.WebControls.FormViewDesigner::.cctor

- ea: `0x24f20`
- end: `0x24f7a`
- name: `System.Web.UI.Design.WebControls.FormViewDesigner::.cctor`
- size: `90`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x24f28`: `ItemTemplate`
- `0x24f38`: `EditItemTemplate`
- `0x24f48`: `HeaderTemplate`
- `0x24f30`: `FooterTemplate`
- `0x24f40`: `InsertItemTemplate`
- `0x24f50`: `EmptyDataTemplate`
- `0x24f58`: `PagerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x24f20  ldc.i4.7
0x24f21  newarr   [mscorlib]System.String
0x24f26  dup
0x24f27  ldc.i4.0
0x24f28  ldstr    aItemtemplate// "ItemTemplate"
0x24f2d  stelem.ref
0x24f2e  dup
0x24f2f  ldc.i4.1
0x24f30  ldstr    aFootertemplate// "FooterTemplate"
0x24f35  stelem.ref
0x24f36  dup
0x24f37  ldc.i4.2
0x24f38  ldstr    aEdititemtempla// "EditItemTemplate"
0x24f3d  stelem.ref
0x24f3e  dup
0x24f3f  ldc.i4.3
0x24f40  ldstr    aInsertitemtemp// "InsertItemTemplate"
0x24f45  stelem.ref
0x24f46  dup
0x24f47  ldc.i4.4
0x24f48  ldstr    aHeadertemplate// "HeaderTemplate"
0x24f4d  stelem.ref
0x24f4e  dup
0x24f4f  ldc.i4.5
0x24f50  ldstr    aEmptydatatempl// "EmptyDataTemplate"
0x24f55  stelem.ref
0x24f56  dup
0x24f57  ldc.i4.6
0x24f58  ldstr    aPagertemplate// "PagerTemplate"
0x24f5d  stelem.ref
0x24f5e  stsfld   string[] System.Web.UI.Design.WebControls.FormViewDesigner::_controlTemplateNames
0x24f63  ldc.i4.7
0x24f64  newarr   [mscorlib]System.Boolean
0x24f69  dup
0x24f6a  ldtoken  valuetype __StaticArrayInitTypeSize=7 <PrivateImplementationDetails>::C36336F242C655C52FA06C4D03F665CA9EA0BB84F20F1B1F90976AA58CA40A4A
0x24f6f  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x24f74  stsfld   bool[] System.Web.UI.Design.WebControls.FormViewDesigner::_controlTemplateSupportsDataBinding
0x24f79  ret
```
