# Microsoft.Reporting.WebForms.PanelUpdater::MarkPanelsForUpdate

- ea: `0xc0f0`
- end: `0xc0ff`
- name: `Microsoft.Reporting.WebForms.PanelUpdater::MarkPanelsForUpdate`
- size: `15`
- prototype: ``
- caller_count: `24`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x12070`
- `0x124a0`
- `0x12500`
- `0x12590`
- `0x125f0`
- `0x12650`
- `0x126b0`
- `0x12710`
- `0x12770`
- `0x127d0`
- `0x12830`
- `0x12ba0`
- `0x12be0`
- `0x12ca0`
- `0x13000`
- `0x131c0`
- `0x13670`
- `0x139f0`
- `0x14610`
- `0x14e00`
- `0x152e0`
- `0x155a0`
- `0x15a10`
- `0x15a60`

## pseudocode

```c

```

## disassembly

```asm
0xc0f0  ldarg.0
0xc0f1  ldarg.0
0xc0f2  ldfld    valuetype Microsoft.Reporting.WebForms.UpdateGroup Microsoft.Reporting.WebForms.PanelUpdater::m_groupsToUpdate
0xc0f7  ldarg.1
0xc0f8  or
0xc0f9  stfld    valuetype Microsoft.Reporting.WebForms.UpdateGroup Microsoft.Reporting.WebForms.PanelUpdater::m_groupsToUpdate
0xc0fe  ret
```
