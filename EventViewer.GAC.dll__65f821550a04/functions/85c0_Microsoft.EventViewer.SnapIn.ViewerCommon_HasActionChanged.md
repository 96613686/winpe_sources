# Microsoft.EventViewer.SnapIn.ViewerCommon::HasActionChanged

- ea: `0x85c0`
- end: `0x8621`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::HasActionChanged`
- size: `97`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2470`

## callees

- `0x85c0`

## pseudocode

```c

```

## disassembly

```asm
0x85c0  ldc.i4.0
0x85c1  stloc.0
0x85c2  ldarg.0
0x85c3  switch   loc_85DE, loc_85EA, loc_8615, loc_85FD, loc_8609
0x85dc  br.s     loc_861F
0x85de  ldarg.1
0x85df  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Enabled()
0x85e4  brtrue.s loc_861F
0x85e6  ldc.i4.1
0x85e7  stloc.0
0x85e8  br.s     loc_861F
0x85ea  ldarg.1
0x85eb  ldc.i4.0
0x85ec  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Enabled(bool)
0x85f1  ldarg.1
0x85f2  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Enabled()
0x85f7  brfalse.s loc_861F
0x85f9  ldc.i4.1
0x85fa  stloc.0
0x85fb  br.s     loc_861F
0x85fd  ldarg.1
0x85fe  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Checked()
0x8603  brtrue.s loc_861F
0x8605  ldc.i4.1
0x8606  stloc.0
0x8607  br.s     loc_861F
0x8609  ldarg.1
0x860a  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Checked()
0x860f  brfalse.s loc_861F
0x8611  ldc.i4.1
0x8612  stloc.0
0x8613  br.s     loc_861F
0x8615  ldarg.1
0x8616  callvirt instance bool [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::get_Enabled()
0x861b  brfalse.s loc_861F
0x861d  ldc.i4.1
0x861e  stloc.0
0x861f  ldloc.0
0x8620  ret
```
