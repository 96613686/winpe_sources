# System.Windows.Input.ApplicationCommands::GetPropertyName

- ea: `0x34700`
- end: `0x3483d`
- name: `System.Windows.Input.ApplicationCommands::GetPropertyName`
- size: `317`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x34cc0`

## callees

- `0x34700`

## string_xrefs

- `0x347a4`: `Delete`
- `0x347ba`: `Replace`
- `0x34835`: `NotACommand`

## pseudocode

```c

```

## disassembly

```asm
0x34700  ldsfld   string [mscorlib]System.String::Empty
0x34705  stloc.0
0x34706  ldarg.0
0x34707  switch   loc_3476D, loc_34778, loc_34783, loc_3478E, loc_34799, loc_347A4, loc_347AF, loc_347BA, loc_347C5, loc_34825, loc_347CD, loc_347D5, loc_347DD, loc_347E5, loc_347F5, loc_347FD, loc_34805, loc_347ED, loc_3480D, loc_34815, loc_3481D, loc_3482D, loc_34835
0x34768  br       loc_3483B
0x3476d  ldstr    aCut// "Cut"
0x34772  stloc.0
0x34773  br       loc_3483B
0x34778  ldstr    aCopy// "Copy"
0x3477d  stloc.0
0x3477e  br       loc_3483B
0x34783  ldstr    aPaste// "Paste"
0x34788  stloc.0
0x34789  br       loc_3483B
0x3478e  ldstr    aUndo// "Undo"
0x34793  stloc.0
0x34794  br       loc_3483B
0x34799  ldstr    aRedo// "Redo"
0x3479e  stloc.0
0x3479f  br       loc_3483B
0x347a4  ldstr    aDelete// "Delete"
0x347a9  stloc.0
0x347aa  br       loc_3483B
0x347af  ldstr    aFind// "Find"
0x347b4  stloc.0
0x347b5  br       loc_3483B
0x347ba  ldstr    aReplace// "Replace"
0x347bf  stloc.0
0x347c0  br       loc_3483B
0x347c5  ldstr    aHelp// "Help"
0x347ca  stloc.0
0x347cb  br.s     loc_3483B
0x347cd  ldstr    aNew// "New"
0x347d2  stloc.0
0x347d3  br.s     loc_3483B
0x347d5  ldstr    aOpen// "Open"
0x347da  stloc.0
0x347db  br.s     loc_3483B
0x347dd  ldstr    aSave// "Save"
0x347e2  stloc.0
0x347e3  br.s     loc_3483B
0x347e5  ldstr    aSaveas// "SaveAs"
0x347ea  stloc.0
0x347eb  br.s     loc_3483B
0x347ed  ldstr    aClose// "Close"
0x347f2  stloc.0
0x347f3  br.s     loc_3483B
0x347f5  ldstr    aPrint// "Print"
0x347fa  stloc.0
0x347fb  br.s     loc_3483B
0x347fd  ldstr    aCancelprint// "CancelPrint"
0x34802  stloc.0
0x34803  br.s     loc_3483B
0x34805  ldstr    aPrintpreview// "PrintPreview"
0x3480a  stloc.0
0x3480b  br.s     loc_3483B
0x3480d  ldstr    aProperties// "Properties"
0x34812  stloc.0
0x34813  br.s     loc_3483B
0x34815  ldstr    aContextmenu// "ContextMenu"
0x3481a  stloc.0
0x3481b  br.s     loc_3483B
0x3481d  ldstr    aCorrectionlist// "CorrectionList"
0x34822  stloc.0
0x34823  br.s     loc_3483B
0x34825  ldstr    aSelectall// "SelectAll"
0x3482a  stloc.0
0x3482b  br.s     loc_3483B
0x3482d  ldstr    aStop// "Stop"
0x34832  stloc.0
0x34833  br.s     loc_3483B
0x34835  ldstr    aNotacommand// "NotACommand"
0x3483a  stloc.0
0x3483b  ldloc.0
0x3483c  ret
```
