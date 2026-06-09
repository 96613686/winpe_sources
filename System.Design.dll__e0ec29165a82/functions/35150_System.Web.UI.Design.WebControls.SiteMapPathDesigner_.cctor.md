# System.Web.UI.Design.WebControls.SiteMapPathDesigner::.cctor

- ea: `0x35150`
- end: `0x3517c`
- name: `System.Web.UI.Design.WebControls.SiteMapPathDesigner::.cctor`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## string_xrefs

- `0x35158`: `NodeTemplate`
- `0x35160`: `CurrentNodeTemplate`
- `0x35168`: `RootNodeTemplate`
- `0x35170`: `PathSeparatorTemplate`

## pseudocode

```c

```

## disassembly

```asm
0x35150  ldc.i4.4
0x35151  newarr   [mscorlib]System.String
0x35156  dup
0x35157  ldc.i4.0
0x35158  ldstr    aNodetemplate// "NodeTemplate"
0x3515d  stelem.ref
0x3515e  dup
0x3515f  ldc.i4.1
0x35160  ldstr    aCurrentnodetem// "CurrentNodeTemplate"
0x35165  stelem.ref
0x35166  dup
0x35167  ldc.i4.2
0x35168  ldstr    aRootnodetempla// "RootNodeTemplate"
0x3516d  stelem.ref
0x3516e  dup
0x3516f  ldc.i4.3
0x35170  ldstr    aPathseparatort// "PathSeparatorTemplate"
0x35175  stelem.ref
0x35176  stsfld   string[] System.Web.UI.Design.WebControls.SiteMapPathDesigner::_controlTemplateNames
0x3517b  ret
```
