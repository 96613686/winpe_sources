# Microsoft.EventViewer.SnapIn.ViewerCommon::AddImages

- ea: `0x86e0`
- end: `0x8fbf`
- name: `Microsoft.EventViewer.SnapIn.ViewerCommon::AddImages`
- size: `2271`
- prototype: ``
- caller_count: `2`
- callee_count: `30`
- tags: `broker_com_uri`

## callers

- `0x430`
- `0x1340`

## callees

- `0xa390`
- `0xa3b0`
- `0xa3d0`
- `0xa3f0`
- `0xa410`
- `0xa430`
- `0xa450`
- `0xa470`
- `0xa490`
- `0xa4b0`
- `0xa4d0`
- `0xa4f0`
- `0xa510`
- `0xa530`
- `0xa550`
- `0xa5b0`
- `0xa5d0`
- `0xa5f0`
- `0xa610`
- `0xa630`
- `0xa650`
- `0xa670`
- `0xa690`
- `0xa6b0`
- `0xa6d0`
- `0xa6f0`
- `0xa710`
- `0xa750`
- `0xa770`
- `0xa790`

## pseudocode

```c

```

## disassembly

```asm
0x86e0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x86e5  callvirt instance class [mscorlib]System.Globalization.TextInfo [mscorlib]System.Globalization.CultureInfo::get_TextInfo()
0x86ea  callvirt instance bool [mscorlib]System.Globalization.TextInfo::get_IsRightToLeft()
0x86ef  stloc.0
0x86f0  ldarg.0
0x86f1  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x86f6  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_EmptyIcon()
0x86fb  ldc.i4   0xFF
0x8700  ldc.i4.0
0x8701  ldc.i4   0xFF
0x8706  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x870b  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image, valuetype [System.Drawing]System.Drawing.Color)
0x8710  pop
0x8711  ldarg.0
0x8712  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8717  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Copy_16()
0x871c  ldc.i4.s 0x10
0x871e  ldc.i4.s 0x10
0x8720  ldloc.0
0x8721  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8726  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x872b  ldarg.0
0x872c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8731  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_EventViewerRootNode_16()
0x8736  ldc.i4.s 0x10
0x8738  ldc.i4.s 0x10
0x873a  ldloc.0
0x873b  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8740  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8745  ldarg.0
0x8746  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x874b  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_EventViewerRootNode_16()
0x8750  ldc.i4.s 0x10
0x8752  ldc.i4.s 0x10
0x8754  ldloc.0
0x8755  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x875a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x875f  ldarg.0
0x8760  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8765  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_SaveLogAs_16()
0x876a  ldc.i4.s 0x10
0x876c  ldc.i4.s 0x10
0x876e  ldloc.0
0x876f  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8774  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8779  ldarg.0
0x877a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x877f  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Folder_16()
0x8784  ldc.i4.s 0x10
0x8786  ldc.i4.s 0x10
0x8788  ldloc.0
0x8789  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x878e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8793  ldarg.0
0x8794  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8799  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewsFolder_16()
0x879e  ldc.i4.s 0x10
0x87a0  ldc.i4.s 0x10
0x87a2  ldloc.0
0x87a3  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x87a8  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x87ad  ldarg.0
0x87ae  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x87b3  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewsFolder_16()
0x87b8  ldc.i4.s 0x10
0x87ba  ldc.i4.s 0x10
0x87bc  ldloc.0
0x87bd  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x87c2  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x87c7  ldarg.0
0x87c8  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x87cd  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_OfflineLogsFolder_16()
0x87d2  ldc.i4.s 0x10
0x87d4  ldc.i4.s 0x10
0x87d6  ldloc.0
0x87d7  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x87dc  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x87e1  ldarg.0
0x87e2  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x87e7  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ViewsFolder_16()
0x87ec  ldc.i4.s 0x10
0x87ee  ldc.i4.s 0x10
0x87f0  ldloc.0
0x87f1  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x87f6  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x87fb  ldarg.0
0x87fc  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8801  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_GlobalLogsFolder_16()
0x8806  ldc.i4.s 0x10
0x8808  ldc.i4.s 0x10
0x880a  ldloc.0
0x880b  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8810  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8815  ldarg.0
0x8816  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x881b  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_ApplicationLogsFolder_16()
0x8820  ldc.i4.s 0x10
0x8822  ldc.i4.s 0x10
0x8824  ldloc.0
0x8825  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x882a  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x882f  ldarg.0
0x8830  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8835  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_Help_16()
0x883a  ldc.i4.s 0x10
0x883c  ldc.i4.s 0x10
0x883e  ldloc.0
0x883f  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8844  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8849  ldarg.0
0x884a  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x884f  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_AdminLog()
0x8854  ldc.i4.s 0x10
0x8856  ldc.i4.s 0x10
0x8858  ldloc.0
0x8859  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x885e  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8863  ldarg.0
0x8864  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8869  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_AnalyticLog()
0x886e  ldc.i4.s 0x10
0x8870  ldc.i4.s 0x10
0x8872  ldloc.0
0x8873  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8878  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x887d  ldarg.0
0x887e  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8883  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_DebugLog()
0x8888  ldc.i4.s 0x10
0x888a  ldc.i4.s 0x10
0x888c  ldloc.0
0x888d  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8892  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8897  ldarg.0
0x8898  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x889d  call     class [System.Drawing]System.Drawing.Bitmap Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_log_generic_16x()
0x88a2  ldc.i4   0xFF
0x88a7  ldc.i4.0
0x88a8  ldc.i4   0xFF
0x88ad  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x88b2  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image, valuetype [System.Drawing]System.Drawing.Color)
0x88b7  pop
0x88b8  ldarg.0
0x88b9  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x88be  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_OperationalLog()
0x88c3  ldc.i4.s 0x10
0x88c5  ldc.i4.s 0x10
0x88c7  ldloc.0
0x88c8  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x88cd  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x88d2  ldarg.0
0x88d3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x88d8  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_OpenLogFile_16()
0x88dd  ldc.i4.s 0x10
0x88df  ldc.i4.s 0x10
0x88e1  ldloc.0
0x88e2  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x88e7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x88ec  ldarg.0
0x88ed  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x88f2  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_LogProperties_16()
0x88f7  ldc.i4.s 0x10
0x88f9  ldc.i4.s 0x10
0x88fb  ldloc.0
0x88fc  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8901  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8906  ldarg.0
0x8907  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x890c  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Refresh_16()
0x8911  ldc.i4.s 0x10
0x8913  ldc.i4.s 0x10
0x8915  ldloc.0
0x8916  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x891b  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8920  ldarg.0
0x8921  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8926  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_SaveLogAs_16()
0x892b  ldc.i4.s 0x10
0x892d  ldc.i4.s 0x10
0x892f  ldloc.0
0x8930  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8935  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x893a  ldarg.0
0x893b  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8940  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Find_16()
0x8945  ldc.i4.s 0x10
0x8947  ldc.i4.s 0x10
0x8949  ldloc.0
0x894a  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x894f  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8954  ldarg.0
0x8955  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x895a  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Filter_16()
0x895f  ldc.i4.s 0x10
0x8961  ldc.i4.s 0x10
0x8963  ldloc.0
0x8964  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8969  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x896e  ldarg.0
0x896f  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8974  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_CreateView_16()
0x8979  ldc.i4.s 0x10
0x897b  ldc.i4.s 0x10
0x897d  ldloc.0
0x897e  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8983  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8988  ldarg.0
0x8989  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x898e  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_Error_16()
0x8993  ldc.i4.s 0x10
0x8995  ldc.i4.s 0x10
0x8997  ldloc.0
0x8998  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x899d  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x89a2  ldarg.0
0x89a3  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x89a8  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_DeleteTask_16()
0x89ad  ldc.i4.s 0x10
0x89af  ldc.i4.s 0x10
0x89b1  ldloc.0
0x89b2  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x89b7  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x89bc  ldarg.0
0x89bd  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x89c2  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_Group()
0x89c7  ldc.i4.s 0x10
0x89c9  ldc.i4.s 0x10
0x89cb  ldloc.0
0x89cc  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x89d1  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x89d6  ldarg.0
0x89d7  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x89dc  call     class [System.Drawing]System.Drawing.Bitmap [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_Checked()
0x89e1  ldc.i4   0xFF
0x89e6  ldc.i4.0
0x89e7  ldc.i4   0xFF
0x89ec  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x89f1  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image, valuetype [System.Drawing]System.Drawing.Color)
0x89f6  pop
0x89f7  ldarg.0
0x89f8  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x89fd  call     class [System.Drawing]System.Drawing.Icon Microsoft.EventViewer.SnapIn.Properties.EventViewerResources::get_LogProperties_16()
0x8a02  ldc.i4.s 0x10
0x8a04  ldc.i4.s 0x10
0x8a06  ldloc.0
0x8a07  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8a0c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8a11  ldarg.0
0x8a12  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8a17  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_statusUnknown()
0x8a1c  ldc.i4.s 0x10
0x8a1e  ldc.i4.s 0x10
0x8a20  ldloc.0
0x8a21  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8a26  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8a2b  ldarg.0
0x8a2c  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8a31  call     class [System.Drawing]System.Drawing.Bitmap [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_UnChecked()
0x8a36  ldc.i4   0xFF
0x8a3b  ldc.i4.0
0x8a3c  ldc.i4   0xFF
0x8a41  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x8a46  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image, valuetype [System.Drawing]System.Drawing.Color)
0x8a4b  pop
0x8a4c  ldarg.0
0x8a4d  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8a52  call     class [System.Drawing]System.Drawing.Bitmap [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_BlueArrow()
0x8a57  ldc.i4   0xFF
0x8a5c  ldc.i4.0
0x8a5d  ldc.i4   0xFF
0x8a62  call     valuetype [System.Drawing]System.Drawing.Color [System.Drawing]System.Drawing.Color::FromArgb(int32, int32, int32)
0x8a67  callvirt instance int32 [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image, valuetype [System.Drawing]System.Drawing.Color)
0x8a6c  pop
0x8a6d  ldarg.0
0x8a6e  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8a73  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_Tour()
0x8a78  ldc.i4.s 0x10
0x8a7a  ldc.i4.s 0x10
0x8a7c  ldloc.0
0x8a7d  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8a82  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8a87  ldarg.0
0x8a88  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8a8d  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIResources::get_Warning_16()
0x8a92  ldc.i4.s 0x10
0x8a94  ldc.i4.s 0x10
0x8a96  ldloc.0
0x8a97  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8a9c  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8aa1  ldarg.0
0x8aa2  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8aa7  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_SubscriptionStatusTrying_16()
0x8aac  ldc.i4.s 0x10
0x8aae  ldc.i4.s 0x10
0x8ab0  ldloc.0
0x8ab1  call     class [System.Drawing]System.Drawing.Image [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.UIGlobals::LoadImageAndDisposeIcon(class [System.Drawing]System.Drawing.Icon, int32, int32, bool)
0x8ab6  callvirt instance void [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList::Add(class [System.Drawing]System.Drawing.Image)
0x8abb  ldarg.0
0x8abc  callvirt instance class [Microsoft.ManagementConsole]Microsoft.ManagementConsole.SnapInImageList [Microsoft.ManagementConsole]Microsoft.ManagementConsole.NamespaceSnapInBase::get_SmallImages()
0x8ac1  call     class [System.Drawing]System.Drawing.Icon [MIGUIControls]Microsoft.Windows.ManagementUI.CombinedControls.EvtResources::get_SubscriptionStatusOK_16()
  ... truncated ...
```
