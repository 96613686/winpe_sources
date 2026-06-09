# Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnConfiguration

- ea: `0x83330`
- end: `0x8362c`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnConfiguration`
- size: `764`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x80490`

## callees

- `0x12ed0`
- `0x83220`
- `0x83330`
- `0x83630`
- `0x83660`
- `0x837c0`

## string_xrefs

- `0x8335f`: `ColumnTaskSchedulerStatus`
- `0x8344d`: `ColumnTaskSchedulerStatus`
- `0x8353b`: `ColumnTaskSchedulerStatus`
- `0x8337c`: `ColumnTaskSchedulerTriggers`
- `0x8346a`: `ColumnTaskSchedulerTriggers`
- `0x83558`: `ColumnTaskSchedulerTriggers`
- `0x83399`: `ColumnTaskSchedulerNextRun`
- `0x83487`: `ColumnTaskSchedulerNextRun`
- `0x83575`: `ColumnTaskSchedulerNextRun`
- `0x833b6`: `ColumnTaskSchedulerLastRun`
- `0x834a4`: `ColumnTaskSchedulerLastRun`
- `0x83592`: `ColumnTaskSchedulerLastRun`
- `0x833d3`: `ColumnTaskSchedulerLastResult`
- `0x834c1`: `ColumnTaskSchedulerLastResult`
- `0x835af`: `ColumnTaskSchedulerLastResult`
- `0x833f0`: `ColumnTaskSchedulerAuthor`
- `0x834de`: `ColumnTaskSchedulerAuthor`
- `0x835cc`: `ColumnTaskSchedulerAuthor`
- `0x8340d`: `ColumnTaskSchedulerCreatedOn`
- `0x834fb`: `ColumnTaskSchedulerCreatedOn`
- `0x835e9`: `ColumnTaskSchedulerCreatedOn`

## pseudocode

```c

```

## disassembly

```asm
0x83330  ldc.i4.1
0x83331  ldarg.s  4
0x83333  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::DefaultNameColumnWidth
0x83338  stind.i4
0x83339  ldarg.0
0x8333a  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::SelectedColumns
0x8333f  ldarg.0
0x83340  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::configReadDocument
0x83345  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::FindNode(string nodeToFind, class [System.Xml]System.Xml.XmlDocument doc)
0x8334a  stloc.0
0x8334b  ldloc.0
0x8334c  brfalse.s loc_8335C
0x8334e  ldarg.1
0x8334f  ldarg.0
0x83350  ldloc.0
0x83351  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ExtractColumnNamesFromNode(class [System.Xml]System.Xml.XmlNode columnsToProcess)
0x83356  stind.ref
0x83357  br       loc_83427
0x8335c  ldarg.1
0x8335d  ldind.ref
0x8335e  ldarg.0
0x8335f  ldstr    aColumntasksche_0// "ColumnTaskSchedulerStatus"
0x83364  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83369  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8336e  box      ColumnInfo
0x83373  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83378  pop
0x83379  ldarg.1
0x8337a  ldind.ref
0x8337b  ldarg.0
0x8337c  ldstr    aColumntasksche_1// "ColumnTaskSchedulerTriggers"
0x83381  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83386  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8338b  box      ColumnInfo
0x83390  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83395  pop
0x83396  ldarg.1
0x83397  ldind.ref
0x83398  ldarg.0
0x83399  ldstr    aColumntasksche_2// "ColumnTaskSchedulerNextRun"
0x8339e  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x833a3  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x833a8  box      ColumnInfo
0x833ad  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x833b2  pop
0x833b3  ldarg.1
0x833b4  ldind.ref
0x833b5  ldarg.0
0x833b6  ldstr    aColumntasksche_3// "ColumnTaskSchedulerLastRun"
0x833bb  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x833c0  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x833c5  box      ColumnInfo
0x833ca  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x833cf  pop
0x833d0  ldarg.1
0x833d1  ldind.ref
0x833d2  ldarg.0
0x833d3  ldstr    aColumntasksche_4// "ColumnTaskSchedulerLastResult"
0x833d8  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x833dd  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x833e2  box      ColumnInfo
0x833e7  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x833ec  pop
0x833ed  ldarg.1
0x833ee  ldind.ref
0x833ef  ldarg.0
0x833f0  ldstr    aColumntasksche_5// "ColumnTaskSchedulerAuthor"
0x833f5  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x833fa  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x833ff  box      ColumnInfo
0x83404  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83409  pop
0x8340a  ldarg.1
0x8340b  ldind.ref
0x8340c  ldarg.0
0x8340d  ldstr    aColumntasksche_6// "ColumnTaskSchedulerCreatedOn"
0x83412  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83417  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8341c  box      ColumnInfo
0x83421  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83426  pop
0x83427  ldarg.0
0x83428  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::AvailableColumns
0x8342d  ldarg.0
0x8342e  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::configReadDocument
0x83433  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::FindNode(string nodeToFind, class [System.Xml]System.Xml.XmlDocument doc)
0x83438  stloc.0
0x83439  ldloc.0
0x8343a  brfalse.s loc_8344A
0x8343c  ldarg.2
0x8343d  ldarg.0
0x8343e  ldloc.0
0x8343f  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ExtractColumnNamesFromNode(class [System.Xml]System.Xml.XmlNode columnsToProcess)
0x83444  stind.ref
0x83445  br       loc_83515
0x8344a  ldarg.2
0x8344b  ldind.ref
0x8344c  ldarg.0
0x8344d  ldstr    aColumntasksche_0// "ColumnTaskSchedulerStatus"
0x83452  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83457  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8345c  box      ColumnInfo
0x83461  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83466  pop
0x83467  ldarg.2
0x83468  ldind.ref
0x83469  ldarg.0
0x8346a  ldstr    aColumntasksche_1// "ColumnTaskSchedulerTriggers"
0x8346f  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83474  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x83479  box      ColumnInfo
0x8347e  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83483  pop
0x83484  ldarg.2
0x83485  ldind.ref
0x83486  ldarg.0
0x83487  ldstr    aColumntasksche_2// "ColumnTaskSchedulerNextRun"
0x8348c  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83491  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x83496  box      ColumnInfo
0x8349b  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x834a0  pop
0x834a1  ldarg.2
0x834a2  ldind.ref
0x834a3  ldarg.0
0x834a4  ldstr    aColumntasksche_3// "ColumnTaskSchedulerLastRun"
0x834a9  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x834ae  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x834b3  box      ColumnInfo
0x834b8  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x834bd  pop
0x834be  ldarg.2
0x834bf  ldind.ref
0x834c0  ldarg.0
0x834c1  ldstr    aColumntasksche_4// "ColumnTaskSchedulerLastResult"
0x834c6  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x834cb  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x834d0  box      ColumnInfo
0x834d5  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x834da  pop
0x834db  ldarg.2
0x834dc  ldind.ref
0x834dd  ldarg.0
0x834de  ldstr    aColumntasksche_5// "ColumnTaskSchedulerAuthor"
0x834e3  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x834e8  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x834ed  box      ColumnInfo
0x834f2  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x834f7  pop
0x834f8  ldarg.2
0x834f9  ldind.ref
0x834fa  ldarg.0
0x834fb  ldstr    aColumntasksche_6// "ColumnTaskSchedulerCreatedOn"
0x83500  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83505  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8350a  box      ColumnInfo
0x8350f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83514  pop
0x83515  ldarg.0
0x83516  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::DefaultColumns
0x8351b  ldarg.0
0x8351c  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::configReadDocument
0x83521  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::FindNode(string nodeToFind, class [System.Xml]System.Xml.XmlDocument doc)
0x83526  stloc.0
0x83527  ldloc.0
0x83528  brfalse.s loc_83538
0x8352a  ldarg.3
0x8352b  ldarg.0
0x8352c  ldloc.0
0x8352d  call     instance class [mscorlib]System.Collections.ArrayList Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ExtractColumnNamesFromNode(class [System.Xml]System.Xml.XmlNode columnsToProcess)
0x83532  stind.ref
0x83533  br       loc_83603
0x83538  ldarg.3
0x83539  ldind.ref
0x8353a  ldarg.0
0x8353b  ldstr    aColumntasksche_0// "ColumnTaskSchedulerStatus"
0x83540  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83545  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x8354a  box      ColumnInfo
0x8354f  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83554  pop
0x83555  ldarg.3
0x83556  ldind.ref
0x83557  ldarg.0
0x83558  ldstr    aColumntasksche_1// "ColumnTaskSchedulerTriggers"
0x8355d  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x83562  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x83567  box      ColumnInfo
0x8356c  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83571  pop
0x83572  ldarg.3
0x83573  ldind.ref
0x83574  ldarg.0
0x83575  ldstr    aColumntasksche_2// "ColumnTaskSchedulerNextRun"
0x8357a  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8357f  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x83584  box      ColumnInfo
0x83589  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x8358e  pop
0x8358f  ldarg.3
0x83590  ldind.ref
0x83591  ldarg.0
0x83592  ldstr    aColumntasksche_3// "ColumnTaskSchedulerLastRun"
0x83597  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x8359c  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x835a1  box      ColumnInfo
0x835a6  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x835ab  pop
0x835ac  ldarg.3
0x835ad  ldind.ref
0x835ae  ldarg.0
0x835af  ldstr    aColumntasksche_4// "ColumnTaskSchedulerLastResult"
0x835b4  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x835b9  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x835be  box      ColumnInfo
0x835c3  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x835c8  pop
0x835c9  ldarg.3
0x835ca  ldind.ref
0x835cb  ldarg.0
0x835cc  ldstr    aColumntasksche_5// "ColumnTaskSchedulerAuthor"
0x835d1  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x835d6  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x835db  box      ColumnInfo
0x835e0  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x835e5  pop
0x835e6  ldarg.3
0x835e7  ldind.ref
0x835e8  ldarg.0
0x835e9  ldstr    aColumntasksche_6// "ColumnTaskSchedulerCreatedOn"
0x835ee  call     string Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::GetString(string strToGet)
0x835f3  call     instance valuetype ColumnInfo Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::GetColumnInfoForSpecifiedColumn(string columnName)
0x835f8  box      ColumnInfo
0x835fd  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x83602  pop
0x83603  ldarg.0
0x83604  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::NameColumnWidth
0x83609  ldarg.0
0x8360a  ldfld    class [System.Xml]System.Xml.XmlDocument Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::configReadDocument
0x8360f  call     instance class [System.Xml]System.Xml.XmlNode Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::FindNode(string nodeToFind, class [System.Xml]System.Xml.XmlDocument doc)
0x83614  stloc.0
0x83615  ldloc.0
0x83616  brfalse.s loc_83623
0x83618  ldarg.s  4
0x8361a  ldarg.0
0x8361b  ldloc.0
0x8361c  call     instance int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::ExtractNameColumnWidthFromNode(class [System.Xml]System.Xml.XmlNode columnsToProcess)
0x83621  stind.i4
0x83622  ret
0x83623  ldarg.s  4
0x83625  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.TaskSchedUiConfiguration::DefaultNameColumnWidth
0x8362a  stind.i4
0x8362b  ret
```
