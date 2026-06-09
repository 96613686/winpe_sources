# Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::.cctor

- ea: `0x838e0`
- end: `0x83960`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::.cctor`
- size: `128`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x12ed0`

## string_xrefs

- `0x838ef`: `TSConfigFolderName`
- `0x838fe`: `ColumnConfiguration`
- `0x83949`: `TaskConfiguration`

## pseudocode

```c

```

## disassembly

```asm
0x838e0  ldstr    aTssnapinroot// "TSSNAPINROOT"
0x838e5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x838ea  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ConfigRootName
0x838ef  ldstr    aTsconfigfolder// "TSConfigFolderName"
0x838f4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x838f9  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ConfigName
0x838fe  ldstr    aColumnconfigur// "ColumnConfiguration"
0x83903  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83908  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ColumnConfiguration
0x8390d  ldstr    aSelectedcolumn// "SelectedColumns"
0x83912  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83917  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::SelectedColumns
0x8391c  ldstr    aAvailablecolum// "AvailableColumns"
0x83921  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83926  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::AvailableColumns
0x8392b  ldstr    aDefaultcolumns// "DefaultColumns"
0x83930  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83935  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::DefaultColumns
0x8393a  ldstr    aNamecolumnwidt// "NameColumnWidth"
0x8393f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83944  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::NameColumnWidth
0x83949  ldstr    aTaskconfigurat// "TaskConfiguration"
0x8394e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83953  stsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::TaskConfiguration
0x83958  ldc.i4.s 0x64
0x8395a  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::DefaultNameColumnWidth
0x8395f  ret
```
