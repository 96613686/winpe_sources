# System.Windows.Input.KeyConverter::GetKey

- ea: `0x3fe00`
- end: `0x4072f`
- name: `System.Windows.Input.KeyConverter::GetKey`
- size: `2351`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x3fd00`

## callees

- `0x2c130`
- `0x3fe00`
- `0x4f880`

## string_xrefs

- `0x4040d`: `COMMA`
- `0x40476`: `OPENBRACKETS`

## pseudocode

```c

```

## disassembly

```asm
0x3fe00  ldarg.1
0x3fe01  ldsfld   string [mscorlib]System.String::Empty
0x3fe06  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3fe0b  brfalse.s loc_3FE14
0x3fe0d  ldc.i4.0
0x3fe0e  box      System.Windows.Input.Key
0x3fe13  ret
0x3fe14  ldarg.1
0x3fe15  ldarg.2
0x3fe16  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x3fe1b  starg.s  1
0x3fe1d  ldarg.1
0x3fe1e  callvirt instance int32 [mscorlib]System.String::get_Length()
0x3fe23  ldc.i4.1
0x3fe24  bne.un   loc_3FECF
0x3fe29  ldarg.1
0x3fe2a  ldc.i4.0
0x3fe2b  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe30  call     bool [mscorlib]System.Char::IsLetterOrDigit(char)
0x3fe35  brfalse  loc_3FECF
0x3fe3a  ldarg.1
0x3fe3b  ldc.i4.0
0x3fe3c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe41  call     bool [mscorlib]System.Char::IsDigit(char)
0x3fe46  brfalse.s loc_3FE71
0x3fe48  ldarg.1
0x3fe49  ldc.i4.0
0x3fe4a  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe4f  ldc.i4.s 0x30
0x3fe51  blt.s    loc_3FE71
0x3fe53  ldarg.1
0x3fe54  ldc.i4.0
0x3fe55  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe5a  ldc.i4.s 0x39
0x3fe5c  bgt.s    loc_3FE71
0x3fe5e  ldc.i4.s 0x22
0x3fe60  ldarg.1
0x3fe61  ldc.i4.0
0x3fe62  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe67  add
0x3fe68  ldc.i4.s 0x30
0x3fe6a  sub
0x3fe6b  box      [mscorlib]System.Int32
0x3fe70  ret
0x3fe71  ldarg.1
0x3fe72  ldc.i4.0
0x3fe73  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe78  call     bool [mscorlib]System.Char::IsLetter(char)
0x3fe7d  brfalse.s loc_3FEA8
0x3fe7f  ldarg.1
0x3fe80  ldc.i4.0
0x3fe81  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe86  ldc.i4.s 0x41
0x3fe88  blt.s    loc_3FEA8
0x3fe8a  ldarg.1
0x3fe8b  ldc.i4.0
0x3fe8c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe91  ldc.i4.s 0x5A
0x3fe93  bgt.s    loc_3FEA8
0x3fe95  ldc.i4.s 0x2C
0x3fe97  ldarg.1
0x3fe98  ldc.i4.0
0x3fe99  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x3fe9e  add
0x3fe9f  ldc.i4.s 0x41
0x3fea1  sub
0x3fea2  box      [mscorlib]System.Int32
0x3fea7  ret
0x3fea8  ldstr    aCannotconverts// "CannotConvertStringToType"
0x3fead  ldc.i4.2
0x3feae  newarr   [mscorlib]System.Object
0x3feb3  dup
0x3feb4  ldc.i4.0
0x3feb5  ldarg.1
0x3feb6  stelem.ref
0x3feb7  dup
0x3feb8  ldc.i4.1
0x3feb9  ldtoken  System.Windows.Input.Key
0x3febe  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3fec3  stelem.ref
0x3fec4  call     string MS.Internal.WindowsBase.SR::Get(string id, object[] args)
0x3fec9  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x3fece  throw
0x3fecf  ldc.i4.m1
0x3fed0  stloc.0
0x3fed1  ldarg.1
0x3fed2  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3fed7  stloc.1
0x3fed8  ldloc.1
0x3fed9  ldc.i4   0x76910F1A
0x3fede  bgt.un   loc_40043
0x3fee3  ldloc.1
0x3fee4  ldc.i4   0x3DDD47D7
0x3fee9  bgt.un   loc_3FF93
0x3feee  ldloc.1
0x3feef  ldc.i4   0x2863C218
0x3fef4  bgt.un.s loc_3FF3F
0x3fef6  ldloc.1
0x3fef7  ldc.i4   0xAE24DCB
0x3fefc  bgt.un.s loc_3FF19
0x3fefe  ldloc.1
0x3feff  ldc.i4   0x36A77A4
0x3ff04  beq      loc_40364
0x3ff09  ldloc.1
0x3ff0a  ldc.i4   0xAE24DCB
0x3ff0f  beq      loc_403B8
0x3ff14  br       loc_4070B
0x3ff19  ldloc.1
0x3ff1a  ldc.i4   0xB0BC6A1
0x3ff1f  beq      loc_40571
0x3ff24  ldloc.1
0x3ff25  ldc.i4   0x1FF2DA7C
0x3ff2a  beq      loc_403CD
0x3ff2f  ldloc.1
0x3ff30  ldc.i4   0x2863C218
0x3ff35  beq      loc_4040C
0x3ff3a  br       loc_4070B
0x3ff3f  ldloc.1
0x3ff40  ldc.i4   0x36C0B212
0x3ff45  bgt.un.s loc_3FF6D
0x3ff47  ldloc.1
0x3ff48  ldc.i4   0x2DDD71E2
0x3ff4d  beq      loc_402FB
0x3ff52  ldloc.1
0x3ff53  ldc.i4   0x2F8E2584
0x3ff58  beq      loc_40436
0x3ff5d  ldloc.1
0x3ff5e  ldc.i4   0x36C0B212
0x3ff63  beq      loc_404DE
0x3ff68  br       loc_4070B
0x3ff6d  ldloc.1
0x3ff6e  ldc.i4   0x3A2DE351
0x3ff73  beq      loc_402E6
0x3ff78  ldloc.1
0x3ff79  ldc.i4   0x3CC956EC
0x3ff7e  beq      loc_404B4
0x3ff83  ldloc.1
0x3ff84  ldc.i4   0x3DDD47D7
0x3ff89  beq      loc_401FF
0x3ff8e  br       loc_4070B
0x3ff93  ldloc.1
0x3ff94  ldc.i4   0x54770F4A
0x3ff99  bgt.un.s loc_3FFEF
0x3ff9b  ldloc.1
0x3ff9c  ldc.i4   0x51C97D59
0x3ffa1  bgt.un.s loc_3FFC9
0x3ffa3  ldloc.1
0x3ffa4  ldc.i4   0x4E327EB9
0x3ffa9  beq      loc_40253
0x3ffae  ldloc.1
0x3ffaf  ldc.i4   0x500C65D7
0x3ffb4  beq      loc_404C9
0x3ffb9  ldloc.1
0x3ffba  ldc.i4   0x51C97D59
0x3ffbf  beq      loc_40379
0x3ffc4  br       loc_4070B
0x3ffc9  ldloc.1
0x3ffca  ldc.i4   0x533C86FE
0x3ffcf  beq      loc_403E2
0x3ffd4  ldloc.1
0x3ffd5  ldc.i4   0x540F0F6A
0x3ffda  beq      loc_40229
0x3ffdf  ldloc.1
0x3ffe0  ldc.i4   0x54770F4A
0x3ffe5  beq      loc_4027D
0x3ffea  br       loc_4070B
0x3ffef  ldloc.1
0x3fff0  ldc.i4   0x6802BAC5
0x3fff5  bgt.un.s loc_4001D
0x3fff7  ldloc.1
0x3fff8  ldc.i4   0x58FA844D
0x3fffd  beq      loc_40268
0x40002  ldloc.1
0x40003  ldc.i4   0x5D619EBC
0x40008  beq      loc_403A3
0x4000d  ldloc.1
0x4000e  ldc.i4   0x6802BAC5
0x40013  beq      loc_4044B
0x40018  br       loc_4070B
0x4001d  ldloc.1
0x4001e  ldc.i4   0x6E6774B5
0x40023  beq      loc_403F7
0x40028  ldloc.1
0x40029  ldc.i4   0x7628D78F
0x4002e  beq      loc_40421
0x40033  ldloc.1
0x40034  ldc.i4   0x76910F1A
0x40039  beq      loc_4049F
0x4003e  br       loc_4070B
0x40043  ldloc.1
0x40044  ldc.i4   0xB01613E4
0x40049  bgt.un   loc_400FE
0x4004e  ldloc.1
0x4004f  ldc.i4   0xA213CB2E
0x40054  bgt.un.s loc_400AA
0x40056  ldloc.1
0x40057  ldc.i4   0x988FCA0D
0x4005c  bgt.un.s loc_40084
0x4005e  ldloc.1
0x4005f  ldc.i4   0x7E87C0B4
0x40064  beq      loc_40325
0x40069  ldloc.1
0x4006a  ldc.i4   0x90852664
0x4006f  beq      loc_4038E
0x40074  ldloc.1
0x40075  ldc.i4   0x988FCA0D
0x4007a  beq      loc_40292
0x4007f  br       loc_4070B
0x40084  ldloc.1
0x40085  ldc.i4   0x9B2CD058
0x4008a  beq      loc_402BC
0x4008f  ldloc.1
0x40090  ldc.i4   0xA064A500
0x40095  beq      loc_4051D
0x4009a  ldloc.1
0x4009b  ldc.i4   0xA213CB2E
0x400a0  beq      loc_401EA
0x400a5  br       loc_4070B
0x400aa  ldloc.1
0x400ab  ldc.i4   0xA794E5F8
0x400b0  bgt.un.s loc_400D8
0x400b2  ldloc.1
0x400b3  ldc.i4   0xA4513139
0x400b8  beq      loc_4048A
0x400bd  ldloc.1
0x400be  ldc.i4   0xA513AE72
0x400c3  beq      loc_4055C
0x400c8  ldloc.1
0x400c9  ldc.i4   0xA794E5F8
0x400ce  beq      loc_40508
0x400d3  br       loc_4070B
0x400d8  ldloc.1
0x400d9  ldc.i4   0xAA1B6D65
0x400de  beq      loc_402A7
0x400e3  ldloc.1
0x400e4  ldc.i4   0xAC85EB63
0x400e9  beq      loc_40547
0x400ee  ldloc.1
0x400ef  ldc.i4   0xB01613E4
0x400f4  beq      loc_40475
0x400f9  br       loc_4070B
0x400fe  ldloc.1
0x400ff  ldc.i4   0xDE0DE97E
0x40104  bgt.un.s loc_4015A
0x40106  ldloc.1
0x40107  ldc.i4   0xC9707909
0x4010c  bgt.un.s loc_40134
0x4010e  ldloc.1
0x4010f  ldc.i4   0xB57994AD
0x40114  beq      loc_401AB
0x40119  ldloc.1
0x4011a  ldc.i4   0xBC6ACFE7
0x4011f  beq      loc_40310
0x40124  ldloc.1
0x40125  ldc.i4   0xC9707909
0x4012a  beq      loc_40460
0x4012f  br       loc_4070B
0x40134  ldloc.1
0x40135  ldc.i4   0xD1EDB2E5
0x4013a  beq      loc_401D5
0x4013f  ldloc.1
0x40140  ldc.i4   0xDBC39A37
0x40145  beq      loc_40214
0x4014a  ldloc.1
0x4014b  ldc.i4   0xDE0DE97E
0x40150  beq      loc_4034F
0x40155  br       loc_4070B
0x4015a  ldloc.1
0x4015b  ldc.i4   0xEA50BADE
0x40160  bgt.un.s loc_40185
0x40162  ldloc.1
0x40163  ldc.i4   0xE2D8628A
0x40168  beq      loc_4023E
0x4016d  ldloc.1
0x4016e  ldc.i4   0xE710EAAE
0x40173  beq      loc_404F3
0x40178  ldloc.1
0x40179  ldc.i4   0xEA50BADE
0x4017e  beq.s    loc_401C0
0x40180  br       loc_4070B
0x40185  ldloc.1
0x40186  ldc.i4   0xED22354C
0x4018b  beq      loc_402D1
0x40190  ldloc.1
0x40191  ldc.i4   0xF12C0DA7
0x40196  beq      loc_4033A
0x4019b  ldloc.1
0x4019c  ldc.i4   0xF4AE5A51
0x401a1  beq      loc_40532
0x401a6  br       loc_4070B
0x401ab  ldarg.1
0x401ac  ldstr    aEnter// "ENTER"
0x401b1  call     bool [mscorlib]System.String::op_Equality(string, string)
0x401b6  brtrue   loc_40586
0x401bb  br       loc_4070B
0x401c0  ldarg.1
0x401c1  ldstr    aEsc// "ESC"
0x401c6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x401cb  brtrue   loc_4058D
0x401d0  br       loc_4070B
  ... truncated ...
```
