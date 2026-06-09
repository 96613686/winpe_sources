# Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties_HelpRequested

- ea: `0x24830`
- end: `0x248ba`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties_HelpRequested`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x24830`
- `0x328c0`
- `0x49090`
- `0x4d0b0`

## string_xrefs

- `0x24852`: `taskscheduler.chm::/html/8eda9018-6ee6-4a72-b2a4-bdcee28e2828.htm`
- `0x24897`: `taskscheduler.chm::/html/8eda9018-6ee6-4a72-b2a4-bdcee28e2828.htm`

## pseudocode

```c

```

## disassembly

```asm
0x24830  ldarg.0
0x24831  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x24836  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x2483b  ldarg.0
0x2483c  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabGeneral
0x24841  bne.un.s loc_24875
0x24843  ldarg.2
0x24844  ldc.i4.1
0x24845  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x2484a  ldarg.0
0x2484b  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::node
0x24850  brtrue.s loc_2485D
0x24852  ldstr    aTaskschedulerC// "taskscheduler.chm::/html/8eda9018-6ee6-"...
0x24857  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x2485c  ret
0x2485d  ldarg.0
0x2485e  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::node
0x24863  ldarg.0
0x24864  ldc.i4.5
0x24865  ldstr    aEventviewerChm// "eventviewer.chm::/html/386a877a-220a-4a"...
0x2486a  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::.ctor(valuetype RootNodeNotificationType type, object data)
0x2486f  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::NotifyRootNode(object sender, class Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs args)
0x24874  ret
0x24875  ldarg.0
0x24876  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.TabControlEx Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabProperties
0x2487b  callvirt instance class [System.Windows.Forms]System.Windows.Forms.TabPage [System.Windows.Forms]System.Windows.Forms.TabControl::get_SelectedTab()
0x24880  ldarg.0
0x24881  ldfld    class [System.Windows.Forms]System.Windows.Forms.TabPage Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::tabDetails
0x24886  bne.un.s loc_248B9
0x24888  ldarg.2
0x24889  ldc.i4.1
0x2488a  callvirt instance void [System.Windows.Forms]System.Windows.Forms.HelpEventArgs::set_Handled(bool)
0x2488f  ldarg.0
0x24890  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::node
0x24895  brtrue.s loc_248A2
0x24897  ldstr    aTaskschedulerC// "taskscheduler.chm::/html/8eda9018-6ee6-"...
0x2489c  call     void Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::ShowTaskSchedulerHelpTopic(string taskSchedulerHelpTopic)
0x248a1  ret
0x248a2  ldarg.0
0x248a3  ldfld    class Microsoft.Windows.ManagementUI.CombinedControls.EventsNode Microsoft.Windows.ManagementUI.CombinedControls.EventPropertiesControl::node
0x248a8  ldarg.0
0x248a9  ldc.i4.5
0x248aa  ldstr    aEventviewerChm_0// "eventviewer.chm::/html/149bb77f-0e19-4a"...
0x248af  newobj   instance void Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs::.ctor(valuetype RootNodeNotificationType type, object data)
0x248b4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::NotifyRootNode(object sender, class Microsoft.Windows.ManagementUI.CombinedControls.NotifyRootNodeEventArgs args)
0x248b9  ret
```
