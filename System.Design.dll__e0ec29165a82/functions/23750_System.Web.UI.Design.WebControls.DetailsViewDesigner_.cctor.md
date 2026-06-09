# System.Web.UI.Design.WebControls.DetailsViewDesigner::.cctor

- ea: `0x23750`
- end: `0x237db`
- name: `System.Web.UI.Design.WebControls.DetailsViewDesigner::.cctor`
- size: `139`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x23758`: `ItemTemplate`
- `0x23768`: `EditItemTemplate`
- `0x23778`: `HeaderTemplate`
- `0x237a9`: `HeaderTemplate`
- `0x237a1`: `FooterTemplate`
- `0x23760`: `AlternatingItemTemplate`
- `0x23770`: `InsertItemTemplate`
- `0x237b1`: `EmptyDataTemplate`
- `0x237b9`: `PagerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x23750  ldc.i4.5
0x23751  newarr   [mscorlib]System.String
0x23756  dup
0x23757  ldc.i4.0
0x23758  ldstr    aItemtemplate// "ItemTemplate"
0x2375d  stelem.ref
0x2375e  dup
0x2375f  ldc.i4.1
0x23760  ldstr    aAlternatingite_0// "AlternatingItemTemplate"
0x23765  stelem.ref
0x23766  dup
0x23767  ldc.i4.2
0x23768  ldstr    aEdititemtempla// "EditItemTemplate"
0x2376d  stelem.ref
0x2376e  dup
0x2376f  ldc.i4.3
0x23770  ldstr    aInsertitemtemp// "InsertItemTemplate"
0x23775  stelem.ref
0x23776  dup
0x23777  ldc.i4.4
0x23778  ldstr    aHeadertemplate// "HeaderTemplate"
0x2377d  stelem.ref
0x2377e  stsfld   string[] System.Web.UI.Design.WebControls.DetailsViewDesigner::_rowTemplateNames
0x23783  ldc.i4.5
0x23784  newarr   [mscorlib]System.Boolean
0x23789  dup
0x2378a  ldtoken  valuetype __StaticArrayInitTypeSize=5 <PrivateImplementationDetails>::'499AE0600C64765B309AB3CFEBE22A70F8E51E7955DC791D01D9149A20D6BBD5'
0x2378f  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x23794  stsfld   bool[] System.Web.UI.Design.WebControls.DetailsViewDesigner::_rowTemplateSupportsDataBinding
0x23799  ldc.i4.4
0x2379a  newarr   [mscorlib]System.String
0x2379f  dup
0x237a0  ldc.i4.0
0x237a1  ldstr    aFootertemplate// "FooterTemplate"
0x237a6  stelem.ref
0x237a7  dup
0x237a8  ldc.i4.1
0x237a9  ldstr    aHeadertemplate// "HeaderTemplate"
0x237ae  stelem.ref
0x237af  dup
0x237b0  ldc.i4.2
0x237b1  ldstr    aEmptydatatempl// "EmptyDataTemplate"
0x237b6  stelem.ref
0x237b7  dup
0x237b8  ldc.i4.3
0x237b9  ldstr    aPagertemplate// "PagerTemplate"
0x237be  stelem.ref
0x237bf  stsfld   string[] System.Web.UI.Design.WebControls.DetailsViewDesigner::_controlTemplateNames
0x237c4  ldc.i4.4
0x237c5  newarr   [mscorlib]System.Boolean
0x237ca  dup
0x237cb  ldtoken  int32 <PrivateImplementationDetails>::'27ECD0A598E76F8A2FD264D427DF0A119903E8EAE384E478902541756F089DD1'
0x237d0  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x237d5  stsfld   bool[] System.Web.UI.Design.WebControls.DetailsViewDesigner::_controlTemplateSupportsDataBinding
0x237da  ret
```
