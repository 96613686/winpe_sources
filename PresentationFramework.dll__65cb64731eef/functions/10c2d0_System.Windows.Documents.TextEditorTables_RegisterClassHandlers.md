# System.Windows.Documents.TextEditorTables::_RegisterClassHandlers

- ea: `0x10c2d0`
- end: `0x10c38c`
- name: `System.Windows.Documents.TextEditorTables::_RegisterClassHandlers`
- size: `188`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x104c00`

## callees

- `0xd0b60`
- `0xd0b70`
- `0xd0b80`
- `0xd0b90`
- `0xd0ba0`
- `0xd0bb0`
- `0xd0bc0`
- `0x23eaa0`

## string_xrefs

- `0x10c337`: `KeyDeleteRows`
- `0x10c33c`: `KeyDeleteRowsDisplayString`
- `0x10c34e`: `KeyDeleteColumns`
- `0x10c353`: `KeyDeleteColumnsDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x10c2d0  ldnull
0x10c2d1  ldftn    void System.Windows.Documents.TextEditorTables::OnTableCommand(object target, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventArgs args)
0x10c2d7  newobj   instance void [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler::.ctor(object, native int)
0x10c2dc  stloc.0
0x10c2dd  ldnull
0x10c2de  ldftn    void System.Windows.Documents.TextEditorTables::OnQueryStatusNYI(object target, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventArgs args)
0x10c2e4  newobj   instance void [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler::.ctor(object, native int)
0x10c2e9  stloc.1
0x10c2ea  ldarg.0
0x10c2eb  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_InsertTable()
0x10c2f0  ldloc.0
0x10c2f1  ldloc.1
0x10c2f2  ldstr    aKeyinserttable// "KeyInsertTable"
0x10c2f7  ldstr    aKeyinserttable_0// "KeyInsertTableDisplayString"
0x10c2fc  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c301  ldarg.0
0x10c302  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_InsertRows()
0x10c307  ldloc.0
0x10c308  ldloc.1
0x10c309  ldstr    aKeyinsertrows// "KeyInsertRows"
0x10c30e  ldstr    aKeyinsertrowsd// "KeyInsertRowsDisplayString"
0x10c313  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c318  ldarg.0
0x10c319  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_InsertColumns()
0x10c31e  ldloc.0
0x10c31f  ldloc.1
0x10c320  ldstr    aKeyinsertcolum// "KeyInsertColumns"
0x10c325  ldstr    aKeyinsertcolum_0// "KeyInsertColumnsDisplayString"
0x10c32a  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c32f  ldarg.0
0x10c330  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_DeleteRows()
0x10c335  ldloc.0
0x10c336  ldloc.1
0x10c337  ldstr    aKeydeleterows// "KeyDeleteRows"
0x10c33c  ldstr    aKeydeleterowsd// "KeyDeleteRowsDisplayString"
0x10c341  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c346  ldarg.0
0x10c347  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_DeleteColumns()
0x10c34c  ldloc.0
0x10c34d  ldloc.1
0x10c34e  ldstr    aKeydeletecolum// "KeyDeleteColumns"
0x10c353  ldstr    aKeydeletecolum_0// "KeyDeleteColumnsDisplayString"
0x10c358  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c35d  ldarg.0
0x10c35e  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_MergeCells()
0x10c363  ldloc.0
0x10c364  ldloc.1
0x10c365  ldstr    aKeymergecells// "KeyMergeCells"
0x10c36a  ldstr    aKeymergecellsd// "KeyMergeCellsDisplayString"
0x10c36f  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c374  ldarg.0
0x10c375  call     class [PresentationCore]System.Windows.Input.RoutedUICommand System.Windows.Documents.EditingCommands::get_SplitCell()
0x10c37a  ldloc.0
0x10c37b  ldloc.1
0x10c37c  ldstr    aKeysplitcell// "KeySplitCell"
0x10c381  ldstr    aKeysplitcelldi// "KeySplitCellDisplayString"
0x10c386  call     void MS.Internal.Commands.CommandHelpers::RegisterCommandHandler(class [mscorlib]System.Type controlType, class [PresentationCore]System.Windows.Input.RoutedCommand command, class [PresentationCore]System.Windows.Input.ExecutedRoutedEventHandler executedRoutedEventHandler, class [PresentationCore]System.Windows.Input.CanExecuteRoutedEventHandler canExecuteRoutedEventHandler, string srid1, string srid2)
0x10c38b  ret
```
