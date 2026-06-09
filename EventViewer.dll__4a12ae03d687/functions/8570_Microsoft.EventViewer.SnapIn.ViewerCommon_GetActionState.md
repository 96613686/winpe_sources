# Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState

- ea: `0x8570`
- end: `0x85b8`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::GetActionState`
- size: `72`
- prototype: ``
- caller_count: `32`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x22f0`
- `0x28b0`
- `0x2900`
- `0x2950`
- `0x29e0`
- `0x2a30`
- `0x2a80`
- `0x2ad0`
- `0x2b10`
- `0x2ba0`
- `0x2ce0`
- `0x2d30`
- `0x2da0`
- `0x2e10`
- `0x2e60`
- `0x2ec0`
- `0x2f10`
- `0x2f60`
- `0x2fb0`
- `0x3000`
- `0x4cd0`
- `0x4d20`
- `0x5d60`
- `0x6220`
- `0x6270`
- `0x62c0`
- `0x6310`
- `0x6360`
- `0x63b0`
- `0x7fb0`
- `0x8120`
- `0x99a0`

## callees

- `0x8570`

## pseudocode

```c

```

## disassembly

```asm
0x8570  ldarg.0
0x8571  switch   loc_858B, loc_8594, loc_85AF, loc_859D, loc_85A6
0x858a  ret
0x858b  ldarg.1
0x858c  ldind.ref
0x858d  ldc.i4.1
0x858e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Enabled(bool)
0x8593  ret
0x8594  ldarg.1
0x8595  ldind.ref
0x8596  ldc.i4.0
0x8597  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Enabled(bool)
0x859c  ret
0x859d  ldarg.1
0x859e  ldind.ref
0x859f  ldc.i4.1
0x85a0  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Checked(bool)
0x85a5  ret
0x85a6  ldarg.1
0x85a7  ldind.ref
0x85a8  ldc.i4.0
0x85a9  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Checked(bool)
0x85ae  ret
0x85af  ldarg.1
0x85b0  ldind.ref
0x85b1  ldc.i4.0
0x85b2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.ActionBase::set_Enabled(bool)
0x85b7  ret
```
