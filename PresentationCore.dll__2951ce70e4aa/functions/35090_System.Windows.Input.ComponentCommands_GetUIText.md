# System.Windows.Input.ComponentCommands::GetUIText

- ea: `0x35090`
- end: `0x352a3`
- name: `System.Windows.Input.ComponentCommands::GetUIText`
- size: `531`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x34480`

## callees

- `0x35090`
- `0x146e40`

## string_xrefs

- `0x35161`: `MoveLeftText`
- `0x35171`: `MoveRightText`
- `0x35181`: `MoveUpText`
- `0x35191`: `MoveDownText`
- `0x351e1`: `MoveToHomeText`
- `0x351f1`: `MoveToEndText`
- `0x35201`: `MoveToPageUpText`
- `0x35211`: `MoveToPageDownText`
- `0x35255`: `MoveFocusUpText`
- `0x35262`: `MoveFocusDownText`
- `0x3526f`: `MoveFocusBackText`
- `0x3527c`: `MoveFocusForwardText`
- `0x35289`: `MoveFocusPageUpText`
- `0x35296`: `MoveFocusPageDownText`

## pseudocode

```c

```

## disassembly

```asm
0x35090  ldsfld   string [mscorlib]System.String::Empty
0x35095  stloc.0
0x35096  ldarg.0
0x35097  stloc.1
0x35098  ldloc.1
0x35099  ldc.i4.1
0x3509a  sub
0x3509b  switch   loc_35111, loc_35121, loc_35131, loc_35141, loc_35151, loc_35161, loc_35171, loc_35181, loc_35191, loc_351E1, loc_351F1, loc_35201, loc_35211, loc_35221, loc_3522E, loc_35248, loc_3523B, loc_35255, loc_35262, loc_3527C, loc_3526F, loc_35289, loc_35296, loc_351C1, loc_351D1, loc_351A1, loc_351B1
0x3510c  br       loc_352A1
0x35111  ldstr    aScrollpageupte// "ScrollPageUpText"
0x35116  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3511b  stloc.0
0x3511c  br       loc_352A1
0x35121  ldstr    aScrollpagedown_0// "ScrollPageDownText"
0x35126  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3512b  stloc.0
0x3512c  br       loc_352A1
0x35131  ldstr    aScrollpageleft_0// "ScrollPageLeftText"
0x35136  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3513b  stloc.0
0x3513c  br       loc_352A1
0x35141  ldstr    aScrollpagerigh_0// "ScrollPageRightText"
0x35146  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3514b  stloc.0
0x3514c  br       loc_352A1
0x35151  ldstr    aScrollbylinete// "ScrollByLineText"
0x35156  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3515b  stloc.0
0x3515c  br       loc_352A1
0x35161  ldstr    aMovelefttext// "MoveLeftText"
0x35166  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3516b  stloc.0
0x3516c  br       loc_352A1
0x35171  ldstr    aMoverighttext// "MoveRightText"
0x35176  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3517b  stloc.0
0x3517c  br       loc_352A1
0x35181  ldstr    aMoveuptext// "MoveUpText"
0x35186  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3518b  stloc.0
0x3518c  br       loc_352A1
0x35191  ldstr    aMovedowntext// "MoveDownText"
0x35196  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3519b  stloc.0
0x3519c  br       loc_352A1
0x351a1  ldstr    aExtendselectio_3// "ExtendSelectionUpText"
0x351a6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351ab  stloc.0
0x351ac  br       loc_352A1
0x351b1  ldstr    aExtendselectio_4// "ExtendSelectionDownText"
0x351b6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351bb  stloc.0
0x351bc  br       loc_352A1
0x351c1  ldstr    aExtendselectio_5// "ExtendSelectionLeftText"
0x351c6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351cb  stloc.0
0x351cc  br       loc_352A1
0x351d1  ldstr    aExtendselectio_6// "ExtendSelectionRightText"
0x351d6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351db  stloc.0
0x351dc  br       loc_352A1
0x351e1  ldstr    aMovetohometext// "MoveToHomeText"
0x351e6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351eb  stloc.0
0x351ec  br       loc_352A1
0x351f1  ldstr    aMovetoendtext// "MoveToEndText"
0x351f6  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x351fb  stloc.0
0x351fc  br       loc_352A1
0x35201  ldstr    aMovetopageupte// "MoveToPageUpText"
0x35206  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3520b  stloc.0
0x3520c  br       loc_352A1
0x35211  ldstr    aMovetopagedown_0// "MoveToPageDownText"
0x35216  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3521b  stloc.0
0x3521c  br       loc_352A1
0x35221  ldstr    aSelecttohomete// "SelectToHomeText"
0x35226  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3522b  stloc.0
0x3522c  br.s     loc_352A1
0x3522e  ldstr    aSelecttoendtex// "SelectToEndText"
0x35233  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35238  stloc.0
0x35239  br.s     loc_352A1
0x3523b  ldstr    aSelecttopagedo_0// "SelectToPageDownText"
0x35240  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35245  stloc.0
0x35246  br.s     loc_352A1
0x35248  ldstr    aSelecttopageup_0// "SelectToPageUpText"
0x3524d  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35252  stloc.0
0x35253  br.s     loc_352A1
0x35255  ldstr    aMovefocusuptex// "MoveFocusUpText"
0x3525a  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3525f  stloc.0
0x35260  br.s     loc_352A1
0x35262  ldstr    aMovefocusdownt// "MoveFocusDownText"
0x35267  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x3526c  stloc.0
0x3526d  br.s     loc_352A1
0x3526f  ldstr    aMovefocusbackt// "MoveFocusBackText"
0x35274  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35279  stloc.0
0x3527a  br.s     loc_352A1
0x3527c  ldstr    aMovefocusforwa_0// "MoveFocusForwardText"
0x35281  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35286  stloc.0
0x35287  br.s     loc_352A1
0x35289  ldstr    aMovefocuspageu_0// "MoveFocusPageUpText"
0x3528e  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x35293  stloc.0
0x35294  br.s     loc_352A1
0x35296  ldstr    aMovefocuspaged_0// "MoveFocusPageDownText"
0x3529b  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x352a0  stloc.0
0x352a1  ldloc.0
0x352a2  ret
```
