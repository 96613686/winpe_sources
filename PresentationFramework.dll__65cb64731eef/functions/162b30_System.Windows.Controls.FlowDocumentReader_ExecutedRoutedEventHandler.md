# System.Windows.Controls.FlowDocumentReader::ExecutedRoutedEventHandler

- ea: `0x162b30`
- end: `0x162c2d`
- name: `System.Windows.Controls.FlowDocumentReader::ExecutedRoutedEventHandler`
- size: `253`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x161fb0`
- `0x161fd0`
- `0x161ff0`
- `0x162010`
- `0x162050`
- `0x162b30`
- `0x162c30`
- `0x162c70`
- `0x162c90`
- `0x162cb0`
- `0x162cd0`

## string_xrefs

- `0x162c22`: `Command not handled in ExecutedRoutedEventHandler.`
- `0x162b3b`: `Target of ExecutedRoutedEventHandler must be FlowDocumentReader.`

## pseudocode

```c

```

## disassembly

```asm
0x162b30  ldarg.0
0x162b31  isinst   System.Windows.Controls.FlowDocumentReader
0x162b36  stloc.0
0x162b37  ldloc.0
0x162b38  ldnull
0x162b39  cgt.un
0x162b3b  ldstr    aTargetOfExecut_0// "Target of ExecutedRoutedEventHandler mu"...
0x162b40  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x162b45  ldarg.1
0x162b46  ldnull
0x162b47  cgt.un
0x162b49  ldstr    aArgsCannotBeNu// "args cannot be null."
0x162b4e  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x162b53  ldarg.1
0x162b54  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162b59  ldsfld   class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Controls.FlowDocumentReader::SwitchViewingModeCommand
0x162b5e  bne.un.s loc_162B6D
0x162b60  ldloc.0
0x162b61  ldarg.1
0x162b62  callvirt instance object [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Parameter()
0x162b67  callvirt instance void System.Windows.Controls.FlowDocumentReader::TrySwitchViewingMode(object parameter)
0x162b6c  ret
0x162b6d  ldarg.1
0x162b6e  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162b73  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Find()
0x162b78  bne.un.s loc_162B81
0x162b7a  ldloc.0
0x162b7b  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnFindCommand()
0x162b80  ret
0x162b81  ldarg.1
0x162b82  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162b87  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_Print()
0x162b8c  bne.un.s loc_162B95
0x162b8e  ldloc.0
0x162b8f  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnPrintCommand()
0x162b94  ret
0x162b95  ldarg.1
0x162b96  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162b9b  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.ApplicationCommands::get_CancelPrint()
0x162ba0  bne.un.s loc_162BA9
0x162ba2  ldloc.0
0x162ba3  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnCancelPrintCommand()
0x162ba8  ret
0x162ba9  ldarg.1
0x162baa  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162baf  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_IncreaseZoom()
0x162bb4  bne.un.s loc_162BBD
0x162bb6  ldloc.0
0x162bb7  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnIncreaseZoomCommand()
0x162bbc  ret
0x162bbd  ldarg.1
0x162bbe  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162bc3  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_DecreaseZoom()
0x162bc8  bne.un.s loc_162BD1
0x162bca  ldloc.0
0x162bcb  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnDecreaseZoomCommand()
0x162bd0  ret
0x162bd1  ldarg.1
0x162bd2  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162bd7  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_PreviousPage()
0x162bdc  bne.un.s loc_162BE5
0x162bde  ldloc.0
0x162bdf  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnPreviousPageCommand()
0x162be4  ret
0x162be5  ldarg.1
0x162be6  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162beb  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_NextPage()
0x162bf0  bne.un.s loc_162BF9
0x162bf2  ldloc.0
0x162bf3  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnNextPageCommand()
0x162bf8  ret
0x162bf9  ldarg.1
0x162bfa  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162bff  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_FirstPage()
0x162c04  bne.un.s loc_162C0D
0x162c06  ldloc.0
0x162c07  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnFirstPageCommand()
0x162c0c  ret
0x162c0d  ldarg.1
0x162c0e  callvirt instance class [System]System.Windows.Input.ICommand [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs::get_Command()
0x162c13  call     class [PresentationCore]System.Windows.Input.RoutedUICommand [PresentationCore]System.Windows.Input.NavigationCommands::get_LastPage()
0x162c18  bne.un.s loc_162C21
0x162c1a  ldloc.0
0x162c1b  callvirt instance void System.Windows.Controls.FlowDocumentReader::OnLastPageCommand()
0x162c20  ret
0x162c21  ldc.i4.0
0x162c22  ldstr    aCommandNotHand_0// "Command not handled in ExecutedRoutedEv"...
0x162c27  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x162c2c  ret
```
