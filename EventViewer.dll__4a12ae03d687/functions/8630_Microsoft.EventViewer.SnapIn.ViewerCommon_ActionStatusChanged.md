# Microsoft.EventViewer.SnapIn.ViewerCommon::ActionStatusChanged

- ea: `0x8630`
- end: `0x8678`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::ActionStatusChanged`
- size: `72`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x8120`

## callees

- `0x8630`

## pseudocode

```c

```

## disassembly

```asm
0x8630  ldc.i4.0
0x8631  stloc.0
0x8632  ldarg.0
0x8633  switch   loc_864E, loc_865A, loc_8676, loc_8663, loc_866F
0x864c  br.s     loc_8676
0x864e  ldarg.1
0x864f  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Enabled()
0x8654  ldc.i4.0
0x8655  ceq
0x8657  stloc.0
0x8658  br.s     loc_8676
0x865a  ldarg.1
0x865b  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Enabled()
0x8660  stloc.0
0x8661  br.s     loc_8676
0x8663  ldarg.1
0x8664  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Checked()
0x8669  ldc.i4.0
0x866a  ceq
0x866c  stloc.0
0x866d  br.s     loc_8676
0x866f  ldarg.1
0x8670  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Checked()
0x8675  stloc.0
0x8676  ldloc.0
0x8677  ret
```
