# System.Windows.Input.ComponentCommands::LoadDefaultGestureFromResource

- ea: `0x352b0`
- end: `0x35667`
- name: `System.Windows.Input.ComponentCommands::LoadDefaultGestureFromResource`
- size: `951`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x34110`

## callees

- `0x32540`
- `0x32ec0`
- `0x352b0`
- `0x146e40`

## string_xrefs

- `0x353cc`: `MoveLeftKey`
- `0x353d6`: `MoveLeftKeyDisplayString`
- `0x353eb`: `MoveRightKey`
- `0x353f5`: `MoveRightKeyDisplayString`
- `0x3540a`: `MoveUpKey`
- `0x35414`: `MoveUpKeyDisplayString`
- `0x35429`: `MoveDownKey`
- `0x35433`: `MoveDownKeyDisplayString`
- `0x354c4`: `MoveToHomeKey`
- `0x354ce`: `MoveToHomeKeyDisplayString`
- `0x354e3`: `MoveToEndKey`
- `0x354ed`: `MoveToEndKeyDisplayString`
- `0x35502`: `MoveToPageUpKey`
- `0x3550c`: `MoveToPageUpKeyDisplayString`
- `0x35521`: `MoveToPageDownKey`
- `0x3552b`: `MoveToPageDownKeyDisplayString`
- `0x355bc`: `MoveFocusUpKey`
- `0x355c6`: `MoveFocusUpKeyDisplayString`
- `0x355db`: `MoveFocusDownKey`
- `0x355e5`: `MoveFocusDownKeyDisplayString`
- `0x355f7`: `MoveFocusBackKey`
- `0x35601`: `MoveFocusBackKeyDisplayString`
- `0x35613`: `MoveFocusForwardKey`
- `0x3561d`: `MoveFocusForwardKeyDisplayString`
- `0x3562f`: `MoveFocusPageUpKey`
- `0x35639`: `MoveFocusPageUpKeyDisplayString`
- `0x3564b`: `MoveFocusPageDownKey`
- `0x35655`: `MoveFocusPageDownKeyDisplayString`

## pseudocode

```c

```

## disassembly

```asm
0x352b0  newobj   instance void System.Windows.Input.InputGestureCollection::.ctor()
0x352b5  stloc.0
0x352b6  ldarg.0
0x352b7  stloc.1
0x352b8  ldloc.1
0x352b9  ldc.i4.1
0x352ba  sub
0x352bb  switch   loc_35331, loc_35350, loc_3536F, loc_3538E, loc_353AD, loc_353CC, loc_353EB, loc_3540A, loc_35429, loc_354C4, loc_354E3, loc_35502, loc_35521, loc_35540, loc_3555F, loc_3559D, loc_3557E, loc_355BC, loc_355DB, loc_35613, loc_355F7, loc_3562F, loc_3564B, loc_35486, loc_354A5, loc_35448, loc_35467
0x3532c  br       loc_35665
0x35331  ldstr    aScrollpageupke// "ScrollPageUpKey"
0x35336  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3533b  ldstr    aScrollpageupke_0// "ScrollPageUpKeyDisplayString"
0x35340  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35345  ldloc.0
0x35346  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3534b  br       loc_35665
0x35350  ldstr    aScrollpagedown_1// "ScrollPageDownKey"
0x35355  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3535a  ldstr    aScrollpagedown_2// "ScrollPageDownKeyDisplayString"
0x3535f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35364  ldloc.0
0x35365  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3536a  br       loc_35665
0x3536f  ldstr    aScrollpageleft_1// "ScrollPageLeftKey"
0x35374  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35379  ldstr    aScrollpageleft_2// "ScrollPageLeftKeyDisplayString"
0x3537e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35383  ldloc.0
0x35384  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35389  br       loc_35665
0x3538e  ldstr    aScrollpagerigh_1// "ScrollPageRightKey"
0x35393  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35398  ldstr    aScrollpagerigh_2// "ScrollPageRightKeyDisplayString"
0x3539d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353a2  ldloc.0
0x353a3  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x353a8  br       loc_35665
0x353ad  ldstr    aScrollbylineke// "ScrollByLineKey"
0x353b2  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353b7  ldstr    aScrollbylineke_0// "ScrollByLineKeyDisplayString"
0x353bc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353c1  ldloc.0
0x353c2  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x353c7  br       loc_35665
0x353cc  ldstr    aMoveleftkey// "MoveLeftKey"
0x353d1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353d6  ldstr    aMoveleftkeydis// "MoveLeftKeyDisplayString"
0x353db  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353e0  ldloc.0
0x353e1  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x353e6  br       loc_35665
0x353eb  ldstr    aMoverightkey// "MoveRightKey"
0x353f0  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353f5  ldstr    aMoverightkeydi// "MoveRightKeyDisplayString"
0x353fa  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x353ff  ldloc.0
0x35400  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35405  br       loc_35665
0x3540a  ldstr    aMoveupkey// "MoveUpKey"
0x3540f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35414  ldstr    aMoveupkeydispl// "MoveUpKeyDisplayString"
0x35419  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3541e  ldloc.0
0x3541f  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35424  br       loc_35665
0x35429  ldstr    aMovedownkey// "MoveDownKey"
0x3542e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35433  ldstr    aMovedownkeydis// "MoveDownKeyDisplayString"
0x35438  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3543d  ldloc.0
0x3543e  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35443  br       loc_35665
0x35448  ldstr    aExtendselectio_7// "ExtendSelectionUpKey"
0x3544d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35452  ldstr    aExtendselectio_8// "ExtendSelectionUpKeyDisplayString"
0x35457  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3545c  ldloc.0
0x3545d  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35462  br       loc_35665
0x35467  ldstr    aExtendselectio_9// "ExtendSelectionDownKey"
0x3546c  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35471  ldstr    aExtendselectio_10// "ExtendSelectionDownKeyDisplayString"
0x35476  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3547b  ldloc.0
0x3547c  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35481  br       loc_35665
0x35486  ldstr    aExtendselectio_11// "ExtendSelectionLeftKey"
0x3548b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35490  ldstr    aExtendselectio_12// "ExtendSelectionLeftKeyDisplayString"
0x35495  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3549a  ldloc.0
0x3549b  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x354a0  br       loc_35665
0x354a5  ldstr    aExtendselectio_13// "ExtendSelectionRightKey"
0x354aa  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354af  ldstr    aExtendselectio_14// "ExtendSelectionRightKeyDisplayString"
0x354b4  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354b9  ldloc.0
0x354ba  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x354bf  br       loc_35665
0x354c4  ldstr    aMovetohomekey// "MoveToHomeKey"
0x354c9  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354ce  ldstr    aMovetohomekeyd// "MoveToHomeKeyDisplayString"
0x354d3  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354d8  ldloc.0
0x354d9  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x354de  br       loc_35665
0x354e3  ldstr    aMovetoendkey// "MoveToEndKey"
0x354e8  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354ed  ldstr    aMovetoendkeydi// "MoveToEndKeyDisplayString"
0x354f2  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x354f7  ldloc.0
0x354f8  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x354fd  br       loc_35665
0x35502  ldstr    aMovetopageupke// "MoveToPageUpKey"
0x35507  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3550c  ldstr    aMovetopageupke_0// "MoveToPageUpKeyDisplayString"
0x35511  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35516  ldloc.0
0x35517  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3551c  br       loc_35665
0x35521  ldstr    aMovetopagedown_1// "MoveToPageDownKey"
0x35526  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3552b  ldstr    aMovetopagedown_2// "MoveToPageDownKeyDisplayString"
0x35530  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35535  ldloc.0
0x35536  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3553b  br       loc_35665
0x35540  ldstr    aSelecttohomeke// "SelectToHomeKey"
0x35545  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3554a  ldstr    aSelecttohomeke_0// "SelectToHomeKeyDisplayString"
0x3554f  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35554  ldloc.0
0x35555  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3555a  br       loc_35665
0x3555f  ldstr    aSelecttoendkey// "SelectToEndKey"
0x35564  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35569  ldstr    aSelecttoendkey_0// "SelectToEndKeyDisplayString"
0x3556e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35573  ldloc.0
0x35574  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35579  br       loc_35665
0x3557e  ldstr    aSelecttopagedo_1// "SelectToPageDownKey"
0x35583  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35588  ldstr    aSelecttopagedo_2// "SelectToPageDownKeyDisplayString"
0x3558d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35592  ldloc.0
0x35593  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35598  br       loc_35665
0x3559d  ldstr    aSelecttopageup_1// "SelectToPageUpKey"
0x355a2  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355a7  ldstr    aSelecttopageup_2// "SelectToPageUpKeyDisplayString"
0x355ac  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355b1  ldloc.0
0x355b2  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x355b7  br       loc_35665
0x355bc  ldstr    aMovefocusupkey// "MoveFocusUpKey"
0x355c1  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355c6  ldstr    aMovefocusupkey_0// "MoveFocusUpKeyDisplayString"
0x355cb  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355d0  ldloc.0
0x355d1  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x355d6  br       loc_35665
0x355db  ldstr    aMovefocusdownk// "MoveFocusDownKey"
0x355e0  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355e5  ldstr    aMovefocusdownk_0// "MoveFocusDownKeyDisplayString"
0x355ea  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x355ef  ldloc.0
0x355f0  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x355f5  br.s     loc_35665
0x355f7  ldstr    aMovefocusbackk// "MoveFocusBackKey"
0x355fc  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35601  ldstr    aMovefocusbackk_0// "MoveFocusBackKeyDisplayString"
0x35606  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3560b  ldloc.0
0x3560c  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35611  br.s     loc_35665
0x35613  ldstr    aMovefocusforwa_1// "MoveFocusForwardKey"
0x35618  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3561d  ldstr    aMovefocusforwa_2// "MoveFocusForwardKeyDisplayString"
0x35622  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35627  ldloc.0
0x35628  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x3562d  br.s     loc_35665
0x3562f  ldstr    aMovefocuspageu_1// "MoveFocusPageUpKey"
0x35634  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35639  ldstr    aMovefocuspageu_2// "MoveFocusPageUpKeyDisplayString"
0x3563e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35643  ldloc.0
0x35644  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35649  br.s     loc_35665
0x3564b  ldstr    aMovefocuspaged_1// "MoveFocusPageDownKey"
0x35650  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35655  ldstr    aMovefocuspaged_2// "MoveFocusPageDownKeyDisplayString"
0x3565a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3565f  ldloc.0
0x35660  call     void System.Windows.Input.KeyGesture::AddGesturesFromResourceStrings(string keyGestures, string displayStrings, class System.Windows.Input.InputGestureCollection gestures)
0x35665  ldloc.0
0x35666  ret
```
