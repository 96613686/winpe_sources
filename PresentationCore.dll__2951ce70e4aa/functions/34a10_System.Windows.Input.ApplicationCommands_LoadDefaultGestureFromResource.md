# System.Windows.Input.ApplicationCommands::LoadDefaultGestureFromResource

- ea: `0x34a10`
- end: `0x34cbd`
- name: `System.Windows.Input.ApplicationCommands::LoadDefaultGestureFromResource`
- size: `685`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x34110`

## callees

- `0x32540`
- `0x32ec0`
- `0x34a10`
- `0x146e40`

## string_xrefs

- `0x34a9e`: `CopyKey`
- `0x34aa8`: `CopyKeyDisplayString`
- `0x34b1a`: `DeleteKey`
- `0x34b24`: `DeleteKeyDisplayString`
- `0x34b58`: `ReplaceKey`
- `0x34b62`: `ReplaceKeyDisplayString`
- `0x34bd4`: `OpenKey`
- `0x34bde`: `OpenKeyDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x34a10  newobj   instance void System.Windows.Input.InputGestureCollection::.ctor()
0x34a15  stloc.0
0x34a16  ldarg.0
0x34a17  stloc.1
0x34a18  ldloc.1
0x34a19  switch   loc_34A7F, loc_34A9E, loc_34ABD, loc_34ADC, loc_34AFB, loc_34B1A, loc_34B39, loc_34B58, loc_34B96, loc_34B77, loc_34BB5, loc_34BD4, loc_34BF3, loc_34CBB, loc_34C12, loc_34CBB, loc_34C31, loc_34CBB, loc_34C85, loc_34C4D, loc_34C69, loc_34CA1, loc_34CBB
0x34a7a  br       loc_34CBB
0x34a7f  ldstr    aCutkey// "CutKey"
0x34a84  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34a89  ldstr    aCutkeydisplays// "CutKeyDisplayString"
0x34a8e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34a93  ldloc.0
0x34a94  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34a99  br       loc_34CBB
0x34a9e  ldstr    aCopykey// "CopyKey"
0x34aa3  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34aa8  ldstr    aCopykeydisplay// "CopyKeyDisplayString"
0x34aad  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34ab2  ldloc.0
0x34ab3  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34ab8  br       loc_34CBB
0x34abd  ldstr    aPastekey// "PasteKey"
0x34ac2  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34ac7  ldstr    aPastekeydispla// "PasteKeyDisplayString"
0x34acc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34ad1  ldloc.0
0x34ad2  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34ad7  br       loc_34CBB
0x34adc  ldstr    aUndokey// "UndoKey"
0x34ae1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34ae6  ldstr    aUndokeydisplay// "UndoKeyDisplayString"
0x34aeb  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34af0  ldloc.0
0x34af1  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34af6  br       loc_34CBB
0x34afb  ldstr    aRedokey// "RedoKey"
0x34b00  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b05  ldstr    aRedokeydisplay// "RedoKeyDisplayString"
0x34b0a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b0f  ldloc.0
0x34b10  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34b15  br       loc_34CBB
0x34b1a  ldstr    aDeletekey// "DeleteKey"
0x34b1f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b24  ldstr    aDeletekeydispl// "DeleteKeyDisplayString"
0x34b29  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b2e  ldloc.0
0x34b2f  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34b34  br       loc_34CBB
0x34b39  ldstr    aFindkey// "FindKey"
0x34b3e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b43  ldstr    aFindkeydisplay// "FindKeyDisplayString"
0x34b48  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b4d  ldloc.0
0x34b4e  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34b53  br       loc_34CBB
0x34b58  ldstr    aReplacekey// "ReplaceKey"
0x34b5d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b62  ldstr    aReplacekeydisp// "ReplaceKeyDisplayString"
0x34b67  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b6c  ldloc.0
0x34b6d  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34b72  br       loc_34CBB
0x34b77  ldstr    aSelectallkey// "SelectAllKey"
0x34b7c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b81  ldstr    aSelectallkeydi// "SelectAllKeyDisplayString"
0x34b86  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34b8b  ldloc.0
0x34b8c  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34b91  br       loc_34CBB
0x34b96  ldstr    aHelpkey// "HelpKey"
0x34b9b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34ba0  ldstr    aHelpkeydisplay// "HelpKeyDisplayString"
0x34ba5  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34baa  ldloc.0
0x34bab  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34bb0  br       loc_34CBB
0x34bb5  ldstr    aNewkey// "NewKey"
0x34bba  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34bbf  ldstr    aNewkeydisplays// "NewKeyDisplayString"
0x34bc4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34bc9  ldloc.0
0x34bca  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34bcf  br       loc_34CBB
0x34bd4  ldstr    aOpenkey// "OpenKey"
0x34bd9  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34bde  ldstr    aOpenkeydisplay// "OpenKeyDisplayString"
0x34be3  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34be8  ldloc.0
0x34be9  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34bee  br       loc_34CBB
0x34bf3  ldstr    aSavekey// "SaveKey"
0x34bf8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34bfd  ldstr    aSavekeydisplay// "SaveKeyDisplayString"
0x34c02  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c07  ldloc.0
0x34c08  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c0d  br       loc_34CBB
0x34c12  ldstr    aPrintkey// "PrintKey"
0x34c17  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c1c  ldstr    aPrintkeydispla// "PrintKeyDisplayString"
0x34c21  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c26  ldloc.0
0x34c27  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c2c  br       loc_34CBB
0x34c31  ldstr    aPrintpreviewke// "PrintPreviewKey"
0x34c36  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c3b  ldstr    aPrintpreviewke_0// "PrintPreviewKeyDisplayString"
0x34c40  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c45  ldloc.0
0x34c46  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c4b  br.s     loc_34CBB
0x34c4d  ldstr    aContextmenukey// "ContextMenuKey"
0x34c52  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c57  ldstr    aContextmenukey_0// "ContextMenuKeyDisplayString"
0x34c5c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c61  ldloc.0
0x34c62  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c67  br.s     loc_34CBB
0x34c69  ldstr    aCorrectionlist_1// "CorrectionListKey"
0x34c6e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c73  ldstr    aCorrectionlist_2// "CorrectionListKeyDisplayString"
0x34c78  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c7d  ldloc.0
0x34c7e  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c83  br.s     loc_34CBB
0x34c85  ldstr    aPropertieskey// "PropertiesKey"
0x34c8a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c8f  ldstr    aPropertieskeyd// "PropertiesKeyDisplayString"
0x34c94  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34c99  ldloc.0
0x34c9a  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34c9f  br.s     loc_34CBB
0x34ca1  ldstr    aStopkey// "StopKey"
0x34ca6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34cab  ldstr    aStopkeydisplay// "StopKeyDisplayString"
0x34cb0  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x34cb5  ldloc.0
0x34cb6  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x34cbb  ldloc.0
0x34cbc  ret
```
