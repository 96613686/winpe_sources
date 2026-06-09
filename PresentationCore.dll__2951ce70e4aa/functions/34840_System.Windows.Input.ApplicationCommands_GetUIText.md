# System.Windows.Input.ApplicationCommands::GetUIText

- ea: `0x34840`
- end: `0x34a01`
- name: `System.Windows.Input.ApplicationCommands::GetUIText`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x34480`

## callees

- `0x34840`
- `0x146e40`

## string_xrefs

- `0x348bf`: `CopyText`
- `0x348ff`: `DeleteText`
- `0x3491f`: `ReplaceText`
- `0x3495f`: `OpenText`
- `0x349f4`: `NotACommandText`

## pseudocode

```c

```

## disassembly

```asm
0x34840  ldsfld   string [mscorlib]System.String::Empty
0x34845  stloc.0
0x34846  ldarg.0
0x34847  stloc.1
0x34848  ldloc.1
0x34849  switch   loc_348AF, loc_348BF, loc_348CF, loc_348DF, loc_348EF, loc_348FF, loc_3490F, loc_3491F, loc_3493F, loc_3492F, loc_3494F, loc_3495F, loc_3496F, loc_3497F, loc_3498C, loc_34999, loc_349A6, loc_349B3, loc_349DA, loc_349C0, loc_349CD, loc_349E7, loc_349F4
0x348aa  br       loc_349FF
0x348af  ldstr    aCuttext// "CutText"
0x348b4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x348b9  stloc.0
0x348ba  br       loc_349FF
0x348bf  ldstr    aCopytext// "CopyText"
0x348c4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x348c9  stloc.0
0x348ca  br       loc_349FF
0x348cf  ldstr    aPastetext// "PasteText"
0x348d4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x348d9  stloc.0
0x348da  br       loc_349FF
0x348df  ldstr    aUndotext// "UndoText"
0x348e4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x348e9  stloc.0
0x348ea  br       loc_349FF
0x348ef  ldstr    aRedotext// "RedoText"
0x348f4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x348f9  stloc.0
0x348fa  br       loc_349FF
0x348ff  ldstr    aDeletetext// "DeleteText"
0x34904  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34909  stloc.0
0x3490a  br       loc_349FF
0x3490f  ldstr    aFindtext// "FindText"
0x34914  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34919  stloc.0
0x3491a  br       loc_349FF
0x3491f  ldstr    aReplacetext// "ReplaceText"
0x34924  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34929  stloc.0
0x3492a  br       loc_349FF
0x3492f  ldstr    aSelectalltext// "SelectAllText"
0x34934  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34939  stloc.0
0x3493a  br       loc_349FF
0x3493f  ldstr    aHelptext// "HelpText"
0x34944  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34949  stloc.0
0x3494a  br       loc_349FF
0x3494f  ldstr    aNewtext// "NewText"
0x34954  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34959  stloc.0
0x3495a  br       loc_349FF
0x3495f  ldstr    aOpentext// "OpenText"
0x34964  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34969  stloc.0
0x3496a  br       loc_349FF
0x3496f  ldstr    aSavetext// "SaveText"
0x34974  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34979  stloc.0
0x3497a  br       loc_349FF
0x3497f  ldstr    aSaveastext// "SaveAsText"
0x34984  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34989  stloc.0
0x3498a  br.s     loc_349FF
0x3498c  ldstr    aPrinttext// "PrintText"
0x34991  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34996  stloc.0
0x34997  br.s     loc_349FF
0x34999  ldstr    aCancelprinttex// "CancelPrintText"
0x3499e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349a3  stloc.0
0x349a4  br.s     loc_349FF
0x349a6  ldstr    aPrintpreviewte// "PrintPreviewText"
0x349ab  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349b0  stloc.0
0x349b1  br.s     loc_349FF
0x349b3  ldstr    aClosetext// "CloseText"
0x349b8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349bd  stloc.0
0x349be  br.s     loc_349FF
0x349c0  ldstr    aContextmenutex// "ContextMenuText"
0x349c5  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349ca  stloc.0
0x349cb  br.s     loc_349FF
0x349cd  ldstr    aCorrectionlist_0// "CorrectionListText"
0x349d2  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349d7  stloc.0
0x349d8  br.s     loc_349FF
0x349da  ldstr    aPropertiestext// "PropertiesText"
0x349df  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349e4  stloc.0
0x349e5  br.s     loc_349FF
0x349e7  ldstr    aStoptext// "StopText"
0x349ec  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349f1  stloc.0
0x349f2  br.s     loc_349FF
0x349f4  ldstr    aNotacommandtex// "NotACommandText"
0x349f9  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x349fe  stloc.0
0x349ff  ldloc.0
0x34a00  ret
```
