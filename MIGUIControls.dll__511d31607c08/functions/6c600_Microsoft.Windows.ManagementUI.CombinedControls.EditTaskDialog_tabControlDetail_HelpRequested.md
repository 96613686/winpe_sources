# Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail_HelpRequested

- ea: `0x6c600`
- end: `0x6c6de`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail_HelpRequested`
- size: `222`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callees

- `0x328c0`
- `0x6c600`

## string_xrefs

- `0x6c6d3`: `taskscheduler.chm::/html/8eda9018-6ee6-4a72-b2a4-bdcee28e2828.htm`
- `0x6c63f`: `taskscheduler.chm::/html/04ea6e78-1d5c-464d-8ba2-b6a441adbdd7.htm`
- `0x6c664`: `taskscheduler.chm::/html/a7df21e3-cdd6-450d-94e8-58579cb7be04.htm`
- `0x6c61a`: `taskscheduler.chm::/html/a922c2b5-6a43-4503-ab7f-4f3d77b3cc8a.htm`
- `0x6c689`: `taskscheduler.chm::/html/687d6377-ee3a-404c-b211-a7b36e3dd619.htm`
- `0x6c6ae`: `taskscheduler.chm::/html/d758ff5d-27d3-4090-b1c2-14ecaa83ff12.htm`

## pseudocode

```c

```

## disassembly

```asm
0x6c600  ldarg.0
0x6c601  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c606  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c60b  ldarg.0
0x6c60c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSummary
0x6c611  bne.un.s loc_6C625
0x6c613  ldarg.2
0x6c614  ldc.i4.1
0x6c615  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c61a  ldstr    aTaskschedulerC_2// "taskscheduler.chm::/html/a922c2b5-6a43-"...
0x6c61f  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c624  ret
0x6c625  ldarg.0
0x6c626  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c62b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c630  ldarg.0
0x6c631  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTriggers
0x6c636  bne.un.s loc_6C64A
0x6c638  ldarg.2
0x6c639  ldc.i4.1
0x6c63a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c63f  ldstr    aTaskschedulerC_0// "taskscheduler.chm::/html/04ea6e78-1d5c-"...
0x6c644  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c649  ret
0x6c64a  ldarg.0
0x6c64b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c650  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c655  ldarg.0
0x6c656  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabTasks
0x6c65b  bne.un.s loc_6C66F
0x6c65d  ldarg.2
0x6c65e  ldc.i4.1
0x6c65f  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c664  ldstr    aTaskschedulerC_1// "taskscheduler.chm::/html/a7df21e3-cdd6-"...
0x6c669  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c66e  ret
0x6c66f  ldarg.0
0x6c670  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c675  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c67a  ldarg.0
0x6c67b  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabConditions
0x6c680  bne.un.s loc_6C694
0x6c682  ldarg.2
0x6c683  ldc.i4.1
0x6c684  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c689  ldstr    aTaskschedulerC_3// "taskscheduler.chm::/html/687d6377-ee3a-"...
0x6c68e  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c693  ret
0x6c694  ldarg.0
0x6c695  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c69a  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c69f  ldarg.0
0x6c6a0  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabSettings
0x6c6a5  bne.un.s loc_6C6B9
0x6c6a7  ldarg.2
0x6c6a8  ldc.i4.1
0x6c6a9  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c6ae  ldstr    aTaskschedulerC_4// "taskscheduler.chm::/html/d758ff5d-27d3-"...
0x6c6b3  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c6b8  ret
0x6c6b9  ldarg.0
0x6c6ba  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabControl Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabControlDetail
0x6c6bf  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x6c6c4  ldarg.0
0x6c6c5  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EditTaskDialog::tabHistory
0x6c6ca  bne.un.s loc_6C6DD
0x6c6cc  ldarg.2
0x6c6cd  ldc.i4.1
0x6c6ce  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x6c6d3  ldstr    aTaskschedulerC// "taskscheduler.chm::/html/8eda9018-6ee6-"...
0x6c6d8  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x6c6dd  ret
```
