# Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler

- ea: `0x7b30`
- end: `0x7b3f`
- name: `Microsoft.EventViewer.SnapIn.EventViewerHomepage::SelectScopeNodeHandler`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x6960`

## pseudocode

```c

```

## disassembly

```asm
0x7b30  ldarg.1
0x7b31  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x7b36  stloc.0
0x7b37  ldarg.0
0x7b38  ldloc.0
0x7b39  call     instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x7b3e  ret
```
