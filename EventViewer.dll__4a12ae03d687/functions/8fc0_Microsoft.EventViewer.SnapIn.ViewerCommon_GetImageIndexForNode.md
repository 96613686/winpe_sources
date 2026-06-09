# Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForNode

- ea: `0x8fc0`
- end: `0x9070`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::GetImageIndexForNode`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4090`

## callees

- `0x8fc0`

## pseudocode

```c

```

## disassembly

```asm
0x8fc0  ldc.i4.0
0x8fc1  stloc.0
0x8fc2  ldarg.0
0x8fc3  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventNodeType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_NodeType()
0x8fc8  stloc.1
0x8fc9  ldloc.1
0x8fca  switch   loc_9012, loc_902C, loc_9005, loc_9023, loc_901E, loc_9028, loc_9067, loc_900D, loc_9009, loc_9062, loc_901A, loc_906B, loc_9016
0x9003  br.s     loc_906E
0x9005  ldc.i4.2
0x9006  stloc.0
0x9007  br.s     loc_906E
0x9009  ldc.i4.7
0x900a  stloc.0
0x900b  br.s     loc_906E
0x900d  ldc.i4.s 9
0x900f  stloc.0
0x9010  br.s     loc_906E
0x9012  ldc.i4.5
0x9013  stloc.0
0x9014  br.s     loc_906E
0x9016  ldc.i4.5
0x9017  stloc.0
0x9018  br.s     loc_906E
0x901a  ldc.i4.5
0x901b  stloc.0
0x901c  br.s     loc_906E
0x901e  ldc.i4.s 0xB
0x9020  stloc.0
0x9021  br.s     loc_906E
0x9023  ldc.i4.s 0xA
0x9025  stloc.0
0x9026  br.s     loc_906E
0x9028  ldc.i4.8
0x9029  stloc.0
0x902a  br.s     loc_906E
0x902c  ldc.i4.s 0x10
0x902e  stloc.0
0x902f  ldarg.0
0x9030  callvirt instance valuetype [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.CrimsonChannelType [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EventsNode::get_ChannelType()
0x9035  stloc.2
0x9036  ldloc.2
0x9037  switch   loc_904E, loc_905D, loc_9053, loc_9058
0x904c  br.s     loc_906E
0x904e  ldc.i4.s 0xD
0x9050  stloc.0
0x9051  br.s     loc_906E
0x9053  ldc.i4.s 0xE
0x9055  stloc.0
0x9056  br.s     loc_906E
0x9058  ldc.i4.s 0xF
0x905a  stloc.0
0x905b  br.s     loc_906E
0x905d  ldc.i4.s 0x11
0x905f  stloc.0
0x9060  br.s     loc_906E
0x9062  ldc.i4.s 0x17
0x9064  stloc.0
0x9065  br.s     loc_906E
0x9067  ldc.i4.4
0x9068  stloc.0
0x9069  br.s     loc_906E
0x906b  ldc.i4.s 0x25
0x906d  stloc.0
0x906e  ldloc.0
0x906f  ret
```
