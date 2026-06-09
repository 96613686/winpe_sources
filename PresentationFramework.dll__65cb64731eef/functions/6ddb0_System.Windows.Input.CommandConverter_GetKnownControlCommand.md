# System.Windows.Input.CommandConverter::GetKnownControlCommand

- ea: `0x6ddb0`
- end: `0x6df37`
- name: `System.Windows.Input.CommandConverter::GetKnownControlCommand`
- size: `391`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x43420`
- `0x207a70`

## callees

- `0x6ddb0`
- `0x18f840`
- `0x18f850`
- `0x251300`

## string_xrefs

- `0x6de42`: `LineUpCommand`
- `0x6de54`: `LineDownCommand`
- `0x6de66`: `LineLeftCommand`
- `0x6de78`: `LineRightCommand`
- `0x6de8a`: `PageUpCommand`
- `0x6de9c`: `PageDownCommand`
- `0x6deae`: `PageLeftCommand`
- `0x6debd`: `PageRightCommand`

## pseudocode

```c

```

## disassembly

```asm
0x6ddb0  ldarg.0
0x6ddb1  ldtoken  System.Windows.Controls.Primitives.ScrollBar
0x6ddb6  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6ddbb  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6ddc0  brfalse  loc_6DEFB
0x6ddc5  ldarg.1
0x6ddc6  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x6ddcb  stloc.0
0x6ddcc  ldloc.0
0x6ddcd  ldc.i4   0x90DE3DB0
0x6ddd2  bgt.un.s loc_6DE0C
0x6ddd4  ldloc.0
0x6ddd5  ldc.i4   0x3FD710E0
0x6ddda  bgt.un.s loc_6DDF4
0x6dddc  ldloc.0
0x6dddd  ldc.i4   0xD6FFA20
0x6dde2  beq.s    loc_6DE53
0x6dde4  ldloc.0
0x6dde5  ldc.i4   0x3FD710E0
0x6ddea  beq      loc_6DEAD
0x6ddef  br       loc_6DF35
0x6ddf4  ldloc.0
0x6ddf5  ldc.i4   0x61E2CE48
0x6ddfa  beq      loc_6DE89
0x6ddff  ldloc.0
0x6de00  ldc.i4   0x90DE3DB0
0x6de05  beq.s    loc_6DE77
0x6de07  br       loc_6DF35
0x6de0c  ldloc.0
0x6de0d  ldc.i4   0xC21F4E53
0x6de12  bgt.un.s loc_6DE29
0x6de14  ldloc.0
0x6de15  ldc.i4   0x9194925F
0x6de1a  beq.s    loc_6DE65
0x6de1c  ldloc.0
0x6de1d  ldc.i4   0xC21F4E53
0x6de22  beq.s    loc_6DE41
0x6de24  br       loc_6DF35
0x6de29  ldloc.0
0x6de2a  ldc.i4   0xD22C0475
0x6de2f  beq      loc_6DEBC
0x6de34  ldloc.0
0x6de35  ldc.i4   0xE4F04EEF
0x6de3a  beq.s    loc_6DE9B
0x6de3c  br       loc_6DF35
0x6de41  ldarg.1
0x6de42  ldstr    aLineupcommand// "LineUpCommand"
0x6de47  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de4c  brtrue.s loc_6DECB
0x6de4e  br       loc_6DF35
0x6de53  ldarg.1
0x6de54  ldstr    aLinedowncomman// "LineDownCommand"
0x6de59  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de5e  brtrue.s loc_6DED1
0x6de60  br       loc_6DF35
0x6de65  ldarg.1
0x6de66  ldstr    aLineleftcomman// "LineLeftCommand"
0x6de6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de70  brtrue.s loc_6DED7
0x6de72  br       loc_6DF35
0x6de77  ldarg.1
0x6de78  ldstr    aLinerightcomma// "LineRightCommand"
0x6de7d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de82  brtrue.s loc_6DEDD
0x6de84  br       loc_6DF35
0x6de89  ldarg.1
0x6de8a  ldstr    aPageupcommand// "PageUpCommand"
0x6de8f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6de94  brtrue.s loc_6DEE3
0x6de96  br       loc_6DF35
0x6de9b  ldarg.1
0x6de9c  ldstr    aPagedowncomman// "PageDownCommand"
0x6dea1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6dea6  brtrue.s loc_6DEE9
0x6dea8  br       loc_6DF35
0x6dead  ldarg.1
0x6deae  ldstr    aPageleftcomman// "PageLeftCommand"
0x6deb3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6deb8  brtrue.s loc_6DEEF
0x6deba  br.s     loc_6DF35
0x6debc  ldarg.1
0x6debd  ldstr    aPagerightcomma// "PageRightCommand"
0x6dec2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6dec7  brtrue.s loc_6DEF5
0x6dec9  br.s     loc_6DF35
0x6decb  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::LineUpCommand
0x6ded0  ret
0x6ded1  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::LineDownCommand
0x6ded6  ret
0x6ded7  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::LineLeftCommand
0x6dedc  ret
0x6dedd  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::LineRightCommand
0x6dee2  ret
0x6dee3  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::PageUpCommand
0x6dee8  ret
0x6dee9  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::PageDownCommand
0x6deee  ret
0x6deef  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::PageLeftCommand
0x6def4  ret
0x6def5  ldsfld   class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Primitives.ScrollBar::PageRightCommand
0x6defa  ret
0x6defb  ldarg.0
0x6defc  ldtoken  System.Windows.Controls.Slider
0x6df01  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x6df06  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x6df0b  brfalse.s loc_6DF35
0x6df0d  ldarg.1
0x6df0e  ldstr    aIncreaselarge// "IncreaseLarge"
0x6df13  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6df18  brtrue.s loc_6DF29
0x6df1a  ldarg.1
0x6df1b  ldstr    aDecreaselarge// "DecreaseLarge"
0x6df20  call     bool [mscorlib]System.String::op_Equality(string, string)
0x6df25  brtrue.s loc_6DF2F
0x6df27  br.s     loc_6DF35
0x6df29  call     class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Slider::get_IncreaseLarge()
0x6df2e  ret
0x6df2f  call     class [PresentationCore]System.Windows.Input.RoutedCommand System.Windows.Controls.Slider::get_DecreaseLarge()
0x6df34  ret
0x6df35  ldnull
0x6df36  ret
```
