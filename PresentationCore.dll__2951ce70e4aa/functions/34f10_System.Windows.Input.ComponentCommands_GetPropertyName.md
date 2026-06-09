# System.Windows.Input.ComponentCommands::GetPropertyName

- ea: `0x34f10`
- end: `0x3508b`
- name: `System.Windows.Input.ComponentCommands::GetPropertyName`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x35670`

## callees

- `0x34f10`

## string_xrefs

- `0x34fc6`: `MoveLeft`
- `0x34fd1`: `MoveRight`
- `0x34fdc`: `MoveUp`
- `0x34fe7`: `MoveDown`
- `0x3501b`: `MoveToHome`
- `0x35023`: `MoveToEnd`
- `0x3502b`: `MoveToPageUp`
- `0x35033`: `MoveToPageDown`
- `0x3505b`: `MoveFocusUp`
- `0x35063`: `MoveFocusDown`
- `0x3506b`: `MoveFocusBack`
- `0x35073`: `MoveFocusForward`
- `0x3507b`: `MoveFocusPageUp`
- `0x35083`: `MoveFocusPageDown`

## pseudocode

```c

```

## disassembly

```asm
0x34f10  ldsfld   string [mscorlib]System.String::Empty
0x34f15  stloc.0
0x34f16  ldarg.0
0x34f17  ldc.i4.1
0x34f18  sub
0x34f19  switch   loc_34F8F, loc_34F9A, loc_34FA5, loc_34FB0, loc_34FBB, loc_34FC6, loc_34FD1, loc_34FDC, loc_34FE7, loc_3501B, loc_35023, loc_3502B, loc_35033, loc_3503B, loc_35043, loc_35053, loc_3504B, loc_3505B, loc_35063, loc_35073, loc_3506B, loc_3507B, loc_35083, loc_35008, loc_35013, loc_34FF2, loc_34FFD
0x34f8a  br       loc_35089
0x34f8f  ldstr    aScrollpageup// "ScrollPageUp"
0x34f94  stloc.0
0x34f95  br       loc_35089
0x34f9a  ldstr    aScrollpagedown// "ScrollPageDown"
0x34f9f  stloc.0
0x34fa0  br       loc_35089
0x34fa5  ldstr    aScrollpageleft// "ScrollPageLeft"
0x34faa  stloc.0
0x34fab  br       loc_35089
0x34fb0  ldstr    aScrollpagerigh// "ScrollPageRight"
0x34fb5  stloc.0
0x34fb6  br       loc_35089
0x34fbb  ldstr    aScrollbyline// "ScrollByLine"
0x34fc0  stloc.0
0x34fc1  br       loc_35089
0x34fc6  ldstr    aMoveleft// "MoveLeft"
0x34fcb  stloc.0
0x34fcc  br       loc_35089
0x34fd1  ldstr    aMoveright// "MoveRight"
0x34fd6  stloc.0
0x34fd7  br       loc_35089
0x34fdc  ldstr    aMoveup// "MoveUp"
0x34fe1  stloc.0
0x34fe2  br       loc_35089
0x34fe7  ldstr    aMovedown// "MoveDown"
0x34fec  stloc.0
0x34fed  br       loc_35089
0x34ff2  ldstr    aExtendselectio// "ExtendSelectionUp"
0x34ff7  stloc.0
0x34ff8  br       loc_35089
0x34ffd  ldstr    aExtendselectio_0// "ExtendSelectionDown"
0x35002  stloc.0
0x35003  br       loc_35089
0x35008  ldstr    aExtendselectio_1// "ExtendSelectionLeft"
0x3500d  stloc.0
0x3500e  br       loc_35089
0x35013  ldstr    aExtendselectio_2// "ExtendSelectionRight"
0x35018  stloc.0
0x35019  br.s     loc_35089
0x3501b  ldstr    aMovetohome// "MoveToHome"
0x35020  stloc.0
0x35021  br.s     loc_35089
0x35023  ldstr    aMovetoend// "MoveToEnd"
0x35028  stloc.0
0x35029  br.s     loc_35089
0x3502b  ldstr    aMovetopageup// "MoveToPageUp"
0x35030  stloc.0
0x35031  br.s     loc_35089
0x35033  ldstr    aMovetopagedown// "MoveToPageDown"
0x35038  stloc.0
0x35039  br.s     loc_35089
0x3503b  ldstr    aSelecttohome// "SelectToHome"
0x35040  stloc.0
0x35041  br.s     loc_35089
0x35043  ldstr    aSelecttoend// "SelectToEnd"
0x35048  stloc.0
0x35049  br.s     loc_35089
0x3504b  ldstr    aSelecttopagedo// "SelectToPageDown"
0x35050  stloc.0
0x35051  br.s     loc_35089
0x35053  ldstr    aSelecttopageup// "SelectToPageUp"
0x35058  stloc.0
0x35059  br.s     loc_35089
0x3505b  ldstr    aMovefocusup// "MoveFocusUp"
0x35060  stloc.0
0x35061  br.s     loc_35089
0x35063  ldstr    aMovefocusdown// "MoveFocusDown"
0x35068  stloc.0
0x35069  br.s     loc_35089
0x3506b  ldstr    aMovefocusback// "MoveFocusBack"
0x35070  stloc.0
0x35071  br.s     loc_35089
0x35073  ldstr    aMovefocusforwa// "MoveFocusForward"
0x35078  stloc.0
0x35079  br.s     loc_35089
0x3507b  ldstr    aMovefocuspageu// "MoveFocusPageUp"
0x35080  stloc.0
0x35081  br.s     loc_35089
0x35083  ldstr    aMovefocuspaged// "MoveFocusPageDown"
0x35088  stloc.0
0x35089  ldloc.0
0x3508a  ret
```
