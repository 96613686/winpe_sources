# System.Web.UI.Design.WebControls.GridViewDesigner::.cctor

- ea: `0x271c0`
- end: `0x27238`
- name: `System.Web.UI.Design.WebControls.GridViewDesigner::.cctor`
- size: `120`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x271c8`: `ItemTemplate`
- `0x271d8`: `EditItemTemplate`
- `0x271e0`: `HeaderTemplate`
- `0x271e8`: `FooterTemplate`
- `0x271d0`: `AlternatingItemTemplate`
- `0x27211`: `EmptyDataTemplate`
- `0x27219`: `PagerTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x271c0  ldc.i4.5
0x271c1  newarr   [mscorlib]System.String
0x271c6  dup
0x271c7  ldc.i4.0
0x271c8  ldstr    aItemtemplate// "ItemTemplate"
0x271cd  stelem.ref
0x271ce  dup
0x271cf  ldc.i4.1
0x271d0  ldstr    aAlternatingite_0// "AlternatingItemTemplate"
0x271d5  stelem.ref
0x271d6  dup
0x271d7  ldc.i4.2
0x271d8  ldstr    aEdititemtempla// "EditItemTemplate"
0x271dd  stelem.ref
0x271de  dup
0x271df  ldc.i4.3
0x271e0  ldstr    aHeadertemplate// "HeaderTemplate"
0x271e5  stelem.ref
0x271e6  dup
0x271e7  ldc.i4.4
0x271e8  ldstr    aFootertemplate// "FooterTemplate"
0x271ed  stelem.ref
0x271ee  stsfld   string[] System.Web.UI.Design.WebControls.GridViewDesigner::_columnTemplateNames
0x271f3  ldc.i4.5
0x271f4  newarr   [mscorlib]System.Boolean
0x271f9  dup
0x271fa  ldtoken  valuetype __StaticArrayInitTypeSize=5 <PrivateImplementationDetails>::DE772D9E9442A56E05F62C9287A4D28BCCED41CC527935D26A4EB5E5D94B3DB5
0x271ff  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x27204  stsfld   bool[] System.Web.UI.Design.WebControls.GridViewDesigner::_columnTemplateSupportsDataBinding
0x27209  ldc.i4.2
0x2720a  newarr   [mscorlib]System.String
0x2720f  dup
0x27210  ldc.i4.0
0x27211  ldstr    aEmptydatatempl// "EmptyDataTemplate"
0x27216  stelem.ref
0x27217  dup
0x27218  ldc.i4.1
0x27219  ldstr    aPagertemplate// "PagerTemplate"
0x2721e  stelem.ref
0x2721f  stsfld   string[] System.Web.UI.Design.WebControls.GridViewDesigner::_controlTemplateNames
0x27224  ldc.i4.2
0x27225  newarr   [mscorlib]System.Boolean
0x2722a  dup
0x2722b  ldc.i4.0
0x2722c  ldc.i4.1
0x2722d  stelem.i1
0x2722e  dup
0x2722f  ldc.i4.1
0x27230  ldc.i4.1
0x27231  stelem.i1
0x27232  stsfld   bool[] System.Web.UI.Design.WebControls.GridViewDesigner::_controlTemplateSupportsDataBinding
0x27237  ret
```
