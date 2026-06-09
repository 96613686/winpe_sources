# Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler

- ea: `0x8050`
- end: `0x8077`
- name: `Microsoft.EventViewer.SnapIn.FormControlBase::SelectScopeNodeHandler`
- size: `39`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x7d50`

## callees

- `0x8050`

## pseudocode

```c

```

## disassembly

```asm
0x8050  ldarg.1
0x8051  castclass [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode
0x8056  stloc.0
0x8057  ldarg.0
0x8058  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x805d  brfalse.s loc_8076
0x805f  ldarg.1
0x8060  brfalse.s loc_8076
0x8062  ldarg.0
0x8063  ldfld    bool Microsoft.EventViewer.SnapIn.FormControlBase::viewIsActive
0x8068  brfalse.s loc_8076
0x806a  ldarg.0
0x806b  ldfld    class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.FormView Microsoft.EventViewer.SnapIn.FormControlBase::view
0x8070  ldloc.0
0x8071  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.View::SelectScopeNode(class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ScopeNode)
0x8076  ret
```
