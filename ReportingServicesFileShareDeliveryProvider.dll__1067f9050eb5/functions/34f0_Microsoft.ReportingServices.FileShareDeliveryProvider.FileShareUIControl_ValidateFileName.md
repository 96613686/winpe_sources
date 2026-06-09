# Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ValidateFileName

- ea: `0x34f0`
- end: `0x36e8`
- name: `Microsoft.ReportingServices.FileShareDeliveryProvider.FileShareUIControl::ValidateFileName`
- size: `504`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0xe10`
- `0x2350`
- `0x4090`

## callees

- `0x34f0`
- `0x3e60`

## pseudocode

```c

```

## disassembly

```asm
0x34f0  ldc.i4.1
0x34f1  stloc.0
0x34f2  ldc.i4.0
0x34f3  stloc.1
0x34f4  br       loc_36DA
0x34f9  ldarg.0
0x34fa  ldloc.1
0x34fb  ldc.i4.1
0x34fc  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x3501  stloc.2
0x3502  ldloc.2
0x3503  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x3508  stloc.3
0x3509  ldloc.3
0x350a  ldc.i4   0x390CAEFB
0x350f  bgt.un.s loc_357D
0x3511  ldloc.3
0x3512  ldc.i4   0x290C95CB
0x3517  bgt.un.s loc_353F
0x3519  ldloc.3
0x351a  ldc.i4   0x230C8C59
0x351f  beq      loc_36C7
0x3524  ldloc.3
0x3525  ldc.i4   0x270C92A5
0x352a  beq      loc_36B8
0x352f  ldloc.3
0x3530  ldc.i4   0x290C95CB
0x3535  beq      loc_368B
0x353a  br       loc_36D6
0x353f  ldloc.3
0x3540  ldc.i4   0x2E0C9DAA
0x3545  bgt.un.s loc_3562
0x3547  ldloc.3
0x3548  ldc.i4   0x2A0C975E
0x354d  beq      loc_35E6
0x3552  ldloc.3
0x3553  ldc.i4   0x2E0C9DAA
0x3558  beq      loc_367C
0x355d  br       loc_36D6
0x3562  ldloc.3
0x3563  ldc.i4   0x2F0C9F3D
0x3568  beq      loc_3625
0x356d  ldloc.3
0x356e  ldc.i4   0x390CAEFB
0x3573  beq      loc_364F
0x3578  br       loc_36D6
0x357d  ldloc.3
0x357e  ldc.i4   0x3F0CB86D
0x3583  bgt.un.s loc_35AB
0x3585  ldloc.3
0x3586  ldc.i4   0x3A0CB08E
0x358b  beq      loc_3610
0x3590  ldloc.3
0x3591  ldc.i4   0x3B0CB221
0x3596  beq      loc_365E
0x359b  ldloc.3
0x359c  ldc.i4   0x3F0CB86D
0x35a1  beq      loc_363A
0x35a6  br       loc_36D6
0x35ab  ldloc.3
0x35ac  ldc.i4   0xD90C17DB
0x35b1  bgt.un.s loc_35CB
0x35b3  ldloc.3
0x35b4  ldc.i4   0xD80C1648
0x35b9  beq      loc_36A9
0x35be  ldloc.3
0x35bf  ldc.i4   0xD90C17DB
0x35c4  beq.s    loc_35FB
0x35c6  br       loc_36D6
0x35cb  ldloc.3
0x35cc  ldc.i4   0xDE0C1FBA
0x35d1  beq      loc_369A
0x35d6  ldloc.3
0x35d7  ldc.i4   0xF90C4A3B
0x35dc  beq      loc_366D
0x35e1  br       loc_36D6
0x35e6  ldloc.2
0x35e7  ldstr    asc_55EA// "/"
0x35ec  call     bool [mscorlib]System.String::op_Equality(string, string)
0x35f1  brtrue   loc_36D4
0x35f6  br       loc_36D6
0x35fb  ldloc.2
0x35fc  ldstr    asc_55E6// "\\"
0x3601  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3606  brtrue   loc_36D4
0x360b  br       loc_36D6
0x3610  ldloc.2
0x3611  ldstr    asc_55EE// "?"
0x3616  call     bool [mscorlib]System.String::op_Equality(string, string)
0x361b  brtrue   loc_36D4
0x3620  br       loc_36D6
0x3625  ldloc.2
0x3626  ldstr    asc_55F2// "*"
0x362b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3630  brtrue   loc_36D4
0x3635  br       loc_36D6
0x363a  ldloc.2
0x363b  ldstr    asc_55F6// ":"
0x3640  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3645  brtrue   loc_36D4
0x364a  br       loc_36D6
0x364f  ldloc.2
0x3650  ldstr    asc_55FA// "<"
0x3655  call     bool [mscorlib]System.String::op_Equality(string, string)
0x365a  brtrue.s loc_36D4
0x365c  br.s     loc_36D6
0x365e  ldloc.2
0x365f  ldstr    asc_55FE// ">"
0x3664  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3669  brtrue.s loc_36D4
0x366b  br.s     loc_36D6
0x366d  ldloc.2
0x366e  ldstr    asc_5602// "|"
0x3673  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3678  brtrue.s loc_36D4
0x367a  br.s     loc_36D6
0x367c  ldloc.2
0x367d  ldstr    asc_5606// "+"
0x3682  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3687  brtrue.s loc_36D4
0x3689  br.s     loc_36D6
0x368b  ldloc.2
0x368c  ldstr    asc_560A// ","
0x3691  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3696  brtrue.s loc_36D4
0x3698  br.s     loc_36D6
0x369a  ldloc.2
0x369b  ldstr    asc_560E// "["
0x36a0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36a5  brtrue.s loc_36D4
0x36a7  br.s     loc_36D6
0x36a9  ldloc.2
0x36aa  ldstr    asc_5612// "]"
0x36af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36b4  brtrue.s loc_36D4
0x36b6  br.s     loc_36D6
0x36b8  ldloc.2
0x36b9  ldstr    asc_5616// "\""
0x36be  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36c3  brtrue.s loc_36D4
0x36c5  br.s     loc_36D6
0x36c7  ldloc.2
0x36c8  ldstr    asc_561A// "&"
0x36cd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x36d2  brfalse.s loc_36D6
0x36d4  ldc.i4.0
0x36d5  stloc.0
0x36d6  ldloc.1
0x36d7  ldc.i4.1
0x36d8  add
0x36d9  stloc.1
0x36da  ldloc.1
0x36db  ldarg.0
0x36dc  callvirt instance int32 [mscorlib]System.String::get_Length()
0x36e1  blt      loc_34F9
0x36e6  ldloc.0
0x36e7  ret
```
