# Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler

- ea: `0x92c0`
- end: `0x92db`
- name: `Microsoft.EventViewer.SnapIn.MessageViewEx::SelectScopeNodeHandler`
- size: `27`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x92c0`

## pseudocode

```c

```

## disassembly

```asm
0x92c0  ldarg.0
0x92c1  ldfld    bool Microsoft.EventViewer.SnapIn.MessageViewEx::activeView
0x92c6  brtrue.s loc_92C9
0x92c8  ret
0x92c9  ldarg.1
0x92ca  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x92cf  stloc.0
0x92d0  ldarg.1
0x92d1  brfalse.s loc_92DA
0x92d3  ldarg.0
0x92d4  ldloc.0
0x92d5  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x92da  ret
```
