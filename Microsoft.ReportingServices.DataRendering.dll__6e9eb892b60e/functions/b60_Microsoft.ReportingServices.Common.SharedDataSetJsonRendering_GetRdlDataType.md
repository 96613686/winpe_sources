# Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlDataType

- ea: `0xb60`
- end: `0xdac`
- name: `Microsoft.ReportingServices.Common.SharedDataSetJsonRendering::GetRdlDataType`
- size: `588`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xb60`

## pseudocode

```c

```

## disassembly

```asm
0xb60  ldarg.0
0xb61  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb66  brfalse.s loc_B6A
0xb68  ldc.i4.0
0xb69  ret
0xb6a  ldarg.0
0xb6b  ldc.i4.1
0xb6c  newarr   [mscorlib]System.Char
0xb71  dup
0xb72  ldc.i4.0
0xb73  ldc.i4.s 0x2E
0xb75  stelem.i2
0xb76  callvirt instance string[] [mscorlib]System.String::Split(char[])
0xb7b  call     T0x2B000008
0xb80  starg.s  0
0xb82  ldarg.0
0xb83  brfalse  loc_DAA
0xb88  ldarg.0
0xb89  call     instance int32 [mscorlib]System.String::get_Length()
0xb8e  stloc.0
0xb8f  ldloc.0
0xb90  ldc.i4.4
0xb91  sub
0xb92  switch   loc_C19, loc_C36, loc_BCD, loc_BB0, loc_D91
0xbab  br       loc_DAA
0xbb0  ldarg.0
0xbb1  ldc.i4.0
0xbb2  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbb7  stloc.1
0xbb8  ldloc.1
0xbb9  ldc.i4.s 0x42
0xbbb  beq      loc_C70
0xbc0  ldloc.1
0xbc1  ldc.i4.s 0x44
0xbc3  beq      loc_C85
0xbc8  br       loc_DAA
0xbcd  ldarg.0
0xbce  ldc.i4.5
0xbcf  call     instance char [mscorlib]System.String::get_Chars(int32)
0xbd4  stloc.1
0xbd5  ldloc.1
0xbd6  ldc.i4.s 0x65
0xbd8  bgt.un.s loc_C04
0xbda  ldloc.1
0xbdb  ldc.i4.s 0x32
0xbdd  sub
0xbde  switch   loc_CD4, loc_DAA, loc_CE9, loc_DAA, loc_CBF
0xbf7  ldloc.1
0xbf8  ldc.i4.s 0x65
0xbfa  beq      loc_C9A
0xbff  br       loc_DAA
0xc04  ldloc.1
0xc05  ldc.i4.s 0x67
0xc07  beq      loc_CFE
0xc0c  ldloc.1
0xc0d  ldc.i4.s 0x6C
0xc0f  beq      loc_D13
0xc14  br       loc_DAA
0xc19  ldarg.0
0xc1a  ldc.i4.0
0xc1b  call     instance char [mscorlib]System.String::get_Chars(int32)
0xc20  stloc.1
0xc21  ldloc.1
0xc22  ldc.i4.s 0x42
0xc24  beq      loc_D28
0xc29  ldloc.1
0xc2a  ldc.i4.s 0x43
0xc2c  beq      loc_D37
0xc31  br       loc_DAA
0xc36  ldarg.0
0xc37  ldc.i4.4
0xc38  call     instance char [mscorlib]System.String::get_Chars(int32)
0xc3d  stloc.1
0xc3e  ldloc.1
0xc3f  ldc.i4.s 0x32
0xc41  sub
0xc42  switch   loc_D64, loc_DAA, loc_D73, loc_DAA, loc_D55
0xc5b  ldloc.1
0xc5c  ldc.i4.s 0x65
0xc5e  beq      loc_D46
0xc63  ldloc.1
0xc64  ldc.i4.s 0x79
0xc66  beq      loc_D82
0xc6b  br       loc_DAA
0xc70  ldarg.0
0xc71  ldstr    aBoolean// "Boolean"
0xc76  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc7b  brtrue   loc_DA0
0xc80  br       loc_DAA
0xc85  ldarg.0
0xc86  ldstr    aDecimal// "Decimal"
0xc8b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xc90  brtrue   loc_DA2
0xc95  br       loc_DAA
0xc9a  ldarg.0
0xc9b  ldstr    aSingle// "Single"
0xca0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xca5  brtrue   loc_DA2
0xcaa  ldarg.0
0xcab  ldstr    aDouble// "Double"
0xcb0  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcb5  brtrue   loc_DA2
0xcba  br       loc_DAA
0xcbf  ldarg.0
0xcc0  ldstr    aUint16// "UInt16"
0xcc5  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcca  brtrue   loc_DA4
0xccf  br       loc_DAA
0xcd4  ldarg.0
0xcd5  ldstr    aUint32// "UInt32"
0xcda  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcdf  brtrue   loc_DA4
0xce4  br       loc_DAA
0xce9  ldarg.0
0xcea  ldstr    aUint64// "UInt64"
0xcef  call     bool [mscorlib]System.String::op_Equality(string, string)
0xcf4  brtrue   loc_DA4
0xcf9  br       loc_DAA
0xcfe  ldarg.0
0xcff  ldstr    aString// "String"
0xd04  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd09  brtrue   loc_DA8
0xd0e  br       loc_DAA
0xd13  ldarg.0
0xd14  ldstr    aDbnull// "DBNull"
0xd19  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd1e  brtrue   loc_DA8
0xd23  br       loc_DAA
0xd28  ldarg.0
0xd29  ldstr    aByte// "Byte"
0xd2e  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd33  brtrue.s loc_DA4
0xd35  br.s     loc_DAA
0xd37  ldarg.0
0xd38  ldstr    aChar// "Char"
0xd3d  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd42  brtrue.s loc_DA8
0xd44  br.s     loc_DAA
0xd46  ldarg.0
0xd47  ldstr    aSbyte// "SByte"
0xd4c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd51  brtrue.s loc_DA4
0xd53  br.s     loc_DAA
0xd55  ldarg.0
0xd56  ldstr    aInt16// "Int16"
0xd5b  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd60  brtrue.s loc_DA4
0xd62  br.s     loc_DAA
0xd64  ldarg.0
0xd65  ldstr    aInt32// "Int32"
0xd6a  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd6f  brtrue.s loc_DA4
0xd71  br.s     loc_DAA
0xd73  ldarg.0
0xd74  ldstr    aInt64// "Int64"
0xd79  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd7e  brtrue.s loc_DA4
0xd80  br.s     loc_DAA
0xd82  ldarg.0
0xd83  ldstr    aEmpty// "Empty"
0xd88  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd8d  brtrue.s loc_DA8
0xd8f  br.s     loc_DAA
0xd91  ldarg.0
0xd92  ldstr    aDatetime// "DateTime"
0xd97  call     bool [mscorlib]System.String::op_Equality(string, string)
0xd9c  brtrue.s loc_DA6
0xd9e  br.s     loc_DAA
0xda0  ldc.i4.1
0xda1  ret
0xda2  ldc.i4.4
0xda3  ret
0xda4  ldc.i4.3
0xda5  ret
0xda6  ldc.i4.2
0xda7  ret
0xda8  ldc.i4.0
0xda9  ret
0xdaa  ldc.i4.0
0xdab  ret
```
