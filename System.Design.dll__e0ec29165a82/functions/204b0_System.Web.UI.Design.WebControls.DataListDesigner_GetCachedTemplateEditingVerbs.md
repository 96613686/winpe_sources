# System.Web.UI.Design.WebControls.DataListDesigner::GetCachedTemplateEditingVerbs

- ea: `0x204b0`
- end: `0x20523`
- name: `System.Web.UI.Design.WebControls.DataListDesigner::GetCachedTemplateEditingVerbs`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x10f00`
- `0x20470`
- `0x204b0`
- `0x8ef40`

## string_xrefs

- `0x204d1`: `DataList_ItemTemplates`
- `0x204ea`: `DataList_HeaderFooterTemplates`
- `0x20503`: `DataList_SeparatorTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x204b0  ldarg.0
0x204b1  ldfld    bool System.Web.UI.Design.WebControls.DataListDesigner::templateVerbsDirty
0x204b6  brfalse.s loc_2051C
0x204b8  ldarg.0
0x204b9  call     instance void System.Web.UI.Design.WebControls.DataListDesigner::DisposeTemplateVerbs()
0x204be  ldarg.0
0x204bf  ldc.i4.3
0x204c0  newarr   System.Web.UI.Design.TemplateEditingVerb
0x204c5  stfld    class System.Web.UI.Design.TemplateEditingVerb[] System.Web.UI.Design.WebControls.DataListDesigner::templateVerbs
0x204ca  ldarg.0
0x204cb  ldfld    class System.Web.UI.Design.TemplateEditingVerb[] System.Web.UI.Design.WebControls.DataListDesigner::templateVerbs
0x204d0  ldc.i4.0
0x204d1  ldstr    aDatalistItemte// "DataList_ItemTemplates"
0x204d6  call     string System.Design.SR::GetString(string name)
0x204db  ldc.i4.0
0x204dc  ldarg.0
0x204dd  newobj   instance void System.Web.UI.Design.TemplateEditingVerb::.ctor(string text, int32 index, class System.Web.UI.Design.TemplatedControlDesigner designer)
0x204e2  stelem.ref
0x204e3  ldarg.0
0x204e4  ldfld    class System.Web.UI.Design.TemplateEditingVerb[] System.Web.UI.Design.WebControls.DataListDesigner::templateVerbs
0x204e9  ldc.i4.1
0x204ea  ldstr    aDatalistHeader// "DataList_HeaderFooterTemplates"
0x204ef  call     string System.Design.SR::GetString(string name)
0x204f4  ldc.i4.1
0x204f5  ldarg.0
0x204f6  newobj   instance void System.Web.UI.Design.TemplateEditingVerb::.ctor(string text, int32 index, class System.Web.UI.Design.TemplatedControlDesigner designer)
0x204fb  stelem.ref
0x204fc  ldarg.0
0x204fd  ldfld    class System.Web.UI.Design.TemplateEditingVerb[] System.Web.UI.Design.WebControls.DataListDesigner::templateVerbs
0x20502  ldc.i4.2
0x20503  ldstr    aDatalistSepara// "DataList_SeparatorTemplate"
0x20508  call     string System.Design.SR::GetString(string name)
0x2050d  ldc.i4.2
0x2050e  ldarg.0
0x2050f  newobj   instance void System.Web.UI.Design.TemplateEditingVerb::.ctor(string text, int32 index, class System.Web.UI.Design.TemplatedControlDesigner designer)
0x20514  stelem.ref
0x20515  ldarg.0
0x20516  ldc.i4.0
0x20517  stfld    bool System.Web.UI.Design.WebControls.DataListDesigner::templateVerbsDirty
0x2051c  ldarg.0
0x2051d  ldfld    class System.Web.UI.Design.TemplateEditingVerb[] System.Web.UI.Design.WebControls.DataListDesigner::templateVerbs
0x20522  ret
```
