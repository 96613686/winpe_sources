# Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDeviceTypeValue

- ea: `0x390`
- end: `0x46f`
- name: `Microsoft.Windows.Diagnosis.Audio.EndpointCtrl::GetDeviceTypeValue`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x160`

## callees

- `0x390`

## pseudocode

```c

```

## disassembly

```asm
0x390  ldc.i4.0
0x391  stloc.0
0x392  ldarg.0
0x393  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x398  callvirt instance string [mscorlib]System.String::ToLower(class [mscorlib]System.Globalization.CultureInfo)
0x39d  stloc.1
0x39e  ldloc.1
0x39f  brfalse  loc_46D
0x3a4  ldloc.1
0x3a5  call     instance int32 [mscorlib]System.String::get_Length()
0x3aa  stloc.2
0x3ab  ldloc.2
0x3ac  ldc.i4.7
0x3ad  sub
0x3ae  switch   loc_448, loc_3EE, loc_46D, loc_3DA, loc_46D, loc_439
0x3cb  ldloc.2
0x3cc  ldc.i4.s 0x10
0x3ce  beq.s    loc_41B
0x3d0  ldloc.2
0x3d1  ldc.i4.s 0x12
0x3d3  beq.s    loc_42A
0x3d5  br       loc_46D
0x3da  ldloc.1
0x3db  ldc.i4.0
0x3dc  call     instance char [mscorlib]System.String::get_Chars(int32)
0x3e1  stloc.3
0x3e2  ldloc.3
0x3e3  ldc.i4.s 0x68
0x3e5  beq.s    loc_3FD
0x3e7  ldloc.3
0x3e8  ldc.i4.s 0x6D
0x3ea  beq.s    loc_40C
0x3ec  br.s     loc_46D
0x3ee  ldloc.1
0x3ef  ldstr    aSpeakers// "speakers"
0x3f4  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3f9  brtrue.s loc_457
0x3fb  br.s     loc_46D
0x3fd  ldloc.1
0x3fe  ldstr    aHeadphones// "headphones"
0x403  call     bool [mscorlib]System.String::op_Equality(string, string)
0x408  brtrue.s loc_45B
0x40a  br.s     loc_46D
0x40c  ldloc.1
0x40d  ldstr    aMicrophone// "microphone"
0x412  call     bool [mscorlib]System.String::op_Equality(string, string)
0x417  brtrue.s loc_45F
0x419  br.s     loc_46D
0x41b  ldloc.1
0x41c  ldstr    aHeadsetEarphon// "headset earphone"
0x421  call     bool [mscorlib]System.String::op_Equality(string, string)
0x426  brtrue.s loc_463
0x428  br.s     loc_46D
0x42a  ldloc.1
0x42b  ldstr    aHeadsetMicroph// "headset microphone"
0x430  call     bool [mscorlib]System.String::op_Equality(string, string)
0x435  brtrue.s loc_463
0x437  br.s     loc_46D
0x439  ldloc.1
0x43a  ldstr    aSpeakerphone// "speakerphone"
0x43f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x444  brtrue.s loc_467
0x446  br.s     loc_46D
0x448  ldloc.1
0x449  ldstr    aHandset// "handset"
0x44e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x453  brtrue.s loc_46B
0x455  br.s     loc_46D
0x457  ldc.i4.1
0x458  stloc.0
0x459  br.s     loc_46D
0x45b  ldc.i4.3
0x45c  stloc.0
0x45d  br.s     loc_46D
0x45f  ldc.i4.4
0x460  stloc.0
0x461  br.s     loc_46D
0x463  ldc.i4.5
0x464  stloc.0
0x465  br.s     loc_46D
0x467  ldc.i4.6
0x468  stloc.0
0x469  br.s     loc_46D
0x46b  ldc.i4.7
0x46c  stloc.0
0x46d  ldloc.0
0x46e  ret
```
