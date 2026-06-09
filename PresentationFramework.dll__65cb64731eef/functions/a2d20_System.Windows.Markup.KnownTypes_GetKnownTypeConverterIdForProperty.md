# System.Windows.Markup.KnownTypes::GetKnownTypeConverterIdForProperty

- ea: `0xa2d20`
- end: `0xa4f6e`
- name: `System.Windows.Markup.KnownTypes::GetKnownTypeConverterIdForProperty`
- size: `8782`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8a620`
- `0x25d830`

## callees

- `0xa21f0`
- `0xa2d20`

## string_xrefs

- `0xa4e40`: `Command`
- `0xa4e70`: `Command`
- `0xa4ea0`: `Command`
- `0xa49bb`: `FontRenderingEmSize`

## pseudocode

```c

```

## disassembly

```asm
0xa2d20  ldc.i4.0
0xa2d21  stloc.0
0xa2d22  ldarg.0
0xa2d23  ldc.i4   0x15F
0xa2d28  bgt      loc_A300D
0xa2d2d  ldarg.0
0xa2d2e  ldc.i4.s 0x6B
0xa2d30  bgt      loc_A2E39
0xa2d35  ldarg.0
0xa2d36  ldc.i4.s 0x29
0xa2d38  bgt.s    loc_A2D99
0xa2d3a  ldarg.0
0xa2d3b  ldc.i4.s 0x18
0xa2d3d  bgt.s    loc_A2D7C
0xa2d3f  ldarg.0
0xa2d40  ldc.i4.1
0xa2d41  sub
0xa2d42  switch   loc_A37DE, loc_A3824, loc_A33E0, loc_A4631, loc_A4647, loc_A4F6C, loc_A4F6C, loc_A4693
0xa2d67  ldarg.0
0xa2d68  ldc.i4.s 0x14
0xa2d6a  beq      loc_A45B9
0xa2d6f  ldarg.0
0xa2d70  ldc.i4.s 0x18
0xa2d72  beq      loc_A45D1
0xa2d77  br       loc_A4F6C
0xa2d7c  ldarg.0
0xa2d7d  ldc.i4.s 0x24
0xa2d7f  beq      loc_A46C6
0xa2d84  ldarg.0
0xa2d85  ldc.i4.s 0x25
0xa2d87  beq      loc_A46F9
0xa2d8c  ldarg.0
0xa2d8d  ldc.i4.s 0x29
0xa2d8f  beq      loc_A4747
0xa2d94  br       loc_A4F6C
0xa2d99  ldarg.0
0xa2d9a  ldc.i4.s 0x4A
0xa2d9c  bgt.s    loc_A2DD8
0xa2d9e  ldarg.0
0xa2d9f  ldc.i4.s 0x32
0xa2da1  sub
0xa2da2  switch   loc_A3850, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A3F44, loc_A3894, loc_A3866
0xa2dc3  ldarg.0
0xa2dc4  ldc.i4.s 0x42
0xa2dc6  beq      loc_A343A
0xa2dcb  ldarg.0
0xa2dcc  ldc.i4.s 0x4A
0xa2dce  beq      loc_A3908
0xa2dd3  br       loc_A4F6C
0xa2dd8  ldarg.0
0xa2dd9  ldc.i4.s 0x50
0xa2ddb  bgt.s    loc_A2DF2
0xa2ddd  ldarg.0
0xa2dde  ldc.i4.s 0x4F
0xa2de0  beq      loc_A35F8
0xa2de5  ldarg.0
0xa2de6  ldc.i4.s 0x50
0xa2de8  beq      loc_A45E9
0xa2ded  br       loc_A4F6C
0xa2df2  ldarg.0
0xa2df3  ldc.i4.s 0x5A
0xa2df5  sub
0xa2df6  switch   loc_A3364, loc_A4F6C, loc_A3994, loc_A3A20
0xa2e0b  ldarg.0
0xa2e0c  ldc.i4.s 0x64
0xa2e0e  sub
0xa2e0f  switch   loc_A34DE, loc_A4F6C, loc_A3A4E, loc_A4F6C, loc_A4F6C, loc_A369A, loc_A3A64, loc_A34B0
0xa2e34  br       loc_A4F6C
0xa2e39  ldarg.0
0xa2e3a  ldc.i4   0x111
0xa2e3f  bgt      loc_A2F6B
0xa2e44  ldarg.0
0xa2e45  ldc.i4   0xBF
0xa2e4a  bgt.s    loc_A2E87
0xa2e4c  ldarg.0
0xa2e4d  ldc.i4   0x85
0xa2e52  beq      loc_A383A
0xa2e57  ldarg.0
0xa2e58  ldc.i4   0xA3
0xa2e5d  sub
0xa2e5e  switch   loc_A3A97, loc_A3F5A, loc_A4762, loc_A3AAD, loc_A3782
0xa2e77  ldarg.0
0xa2e78  ldc.i4   0xBF
0xa2e7d  beq      loc_A4C9B
0xa2e82  br       loc_A4F6C
0xa2e87  ldarg.0
0xa2e88  ldc.i4   0xE0
0xa2e8d  bgt.s    loc_A2EE3
0xa2e8f  ldarg.0
0xa2e90  ldc.i4   0xC7
0xa2e95  sub
0xa2e96  switch   loc_A3B09, loc_A4F6C, loc_A4F6C, loc_A4778, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A47DB, loc_A4851, loc_A489C, loc_A37B0, loc_A3B37, loc_A3754
0xa2ed3  ldarg.0
0xa2ed4  ldc.i4   0xE0
0xa2ed9  beq      loc_A3B65
0xa2ede  br       loc_A4F6C
0xa2ee3  ldarg.0
0xa2ee4  ldc.i4   0xE2
0xa2ee9  beq      loc_A33CA
0xa2eee  ldarg.0
0xa2eef  ldc.i4   0xF7
0xa2ef4  sub
0xa2ef5  switch   loc_A4EE4, loc_A4F6C, loc_A4F6C, loc_A49A7, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A3B93, loc_A4F6C, loc_A4F6C, loc_A3C62, loc_A4F6C, loc_A3BA9, loc_A3BC4, loc_A3C08, loc_A3C1E, loc_A3BF2, loc_A3C90, loc_A3CBE, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A3ADB, loc_A36F8, loc_A4F6C, loc_A4F6C, loc_A4A05
0xa2f66  br       loc_A4F6C
0xa2f6b  ldarg.0
0xa2f6c  ldc.i4   0x14B
0xa2f71  bgt.s    loc_A2FCF
0xa2f73  ldarg.0
0xa2f74  ldc.i4   0x119
0xa2f79  beq      loc_A3CEC
0xa2f7e  ldarg.0
0xa2f7f  ldc.i4   0x120
0xa2f84  sub
0xa2f85  switch   loc_A3D02, loc_A3D78, loc_A4678, loc_A4F6C, loc_A4A20, loc_A4E3F, loc_A4F6C, loc_A4EB7
0xa2faa  ldarg.0
0xa2fab  ldc.i4   0x147
0xa2fb0  sub
0xa2fb1  switch   loc_A4A3B, loc_A3D8E, loc_A363E, loc_A4F6C, loc_A3DA6
0xa2fca  br       loc_A4F6C
0xa2fcf  ldarg.0
0xa2fd0  ldc.i4   0x15A
0xa2fd5  bgt.s    loc_A2FF2
0xa2fd7  ldarg.0
0xa2fd8  ldc.i4   0x151
0xa2fdd  beq      loc_A4E57
0xa2fe2  ldarg.0
0xa2fe3  ldc.i4   0x15A
0xa2fe8  beq      loc_A3DBC
0xa2fed  br       loc_A4F6C
0xa2ff2  ldarg.0
0xa2ff3  ldc.i4   0x15E
0xa2ff8  beq      loc_A4CC9
0xa2ffd  ldarg.0
0xa2ffe  ldc.i4   0x15F
0xa3003  beq      loc_A4A56
0xa3008  br       loc_A4F6C
0xa300d  ldarg.0
0xa300e  ldc.i4   0x20F
0xa3013  bgt      loc_A3173
0xa3018  ldarg.0
0xa3019  ldc.i4   0x1BA
0xa301e  bgt      loc_A30EA
0xa3023  ldarg.0
0xa3024  ldc.i4   0x19C
0xa3029  bgt.s    loc_A3087
0xa302b  ldarg.0
0xa302c  ldc.i4   0x174
0xa3031  sub
0xa3032  switch   loc_A4A71, loc_A3DEA, loc_A39F2, loc_A4601, loc_A4ABC, loc_A3E30, loc_A3E76
0xa3053  ldarg.0
0xa3054  ldc.i4   0x18E
0xa3059  sub
0xa305a  switch   loc_A3EA4, loc_A4F6C, loc_A4F6C, loc_A3EBA, loc_A366C, loc_A3726
0xa3077  ldarg.0
0xa3078  ldc.i4   0x19C
0xa307d  beq      loc_A4E87
0xa3082  br       loc_A4F6C
0xa3087  ldarg.0
0xa3088  ldc.i4   0x1A5
0xa308d  bgt.s    loc_A30AA
0xa308f  ldarg.0
0xa3090  ldc.i4   0x1A0
0xa3095  beq      loc_A4619
0xa309a  ldarg.0
0xa309b  ldc.i4   0x1A5
0xa30a0  beq      loc_A3582
0xa30a5  br       loc_A4F6C
0xa30aa  ldarg.0
0xa30ab  ldc.i4   0x1A9
0xa30b0  beq      loc_A4F5C
0xa30b5  ldarg.0
0xa30b6  ldc.i4   0x1B2
0xa30bb  sub
0xa30bc  switch   loc_A3EE8, loc_A4AEF, loc_A4C6D, loc_A3424, loc_A4B05, loc_A4F6C, loc_A4F6C, loc_A3F16, loc_A4D57
0xa30e5  br       loc_A4F6C
0xa30ea  ldarg.0
0xa30eb  ldc.i4   0x1F8
0xa30f0  bgt.s    loc_A3135
0xa30f2  ldarg.0
0xa30f3  ldc.i4   0x1E3
0xa30f8  sub
0xa30f9  switch   loc_A4D85, loc_A4DB3, loc_A3F70, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A41A8
0xa311a  ldarg.0
0xa311b  ldc.i4   0x1F7
0xa3120  beq      loc_A41D6
0xa3125  ldarg.0
0xa3126  ldc.i4   0x1F8
0xa312b  beq      loc_A3FB6
0xa3130  br       loc_A4F6C
0xa3135  ldarg.0
0xa3136  ldc.i4   0x20A
0xa313b  bgt.s    loc_A3158
0xa313d  ldarg.0
0xa313e  ldc.i4   0x202
0xa3143  beq      loc_A4DE1
0xa3148  ldarg.0
0xa3149  ldc.i4   0x20A
0xa314e  beq      loc_A3FE4
0xa3153  br       loc_A4F6C
0xa3158  ldarg.0
0xa3159  ldc.i4   0x20B
0xa315e  beq      loc_A4012
0xa3163  ldarg.0
0xa3164  ldc.i4   0x20F
0xa3169  beq      loc_A421C
0xa316e  br       loc_A4F6C
0xa3173  ldarg.0
0xa3174  ldc.i4   0x288
0xa3179  bgt      loc_A3285
0xa317e  ldarg.0
0xa317f  ldc.i4   0x241
0xa3184  bgt.s    loc_A31E5
0xa3186  ldarg.0
0xa3187  ldc.i4   0x21D
0xa318c  sub
0xa318d  switch   loc_A3397, loc_A4B50, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4040, loc_A406E, loc_A424A, loc_A4B6B, loc_A4F6C, loc_A394E, loc_A4278
0xa31ca  ldarg.0
0xa31cb  ldc.i4   0x22E
0xa31d0  beq      loc_A33F6
0xa31d5  ldarg.0
0xa31d6  ldc.i4   0x241
0xa31db  beq      loc_A42A6
0xa31e0  br       loc_A4F6C
0xa31e5  ldarg.0
0xa31e6  ldc.i4   0x25E
0xa31eb  bgt.s    loc_A3221
0xa31ed  ldarg.0
0xa31ee  ldc.i4   0x244
0xa31f3  beq      loc_A472C
0xa31f8  ldarg.0
0xa31f9  ldc.i4   0x259
0xa31fe  sub
0xa31ff  switch   loc_A4150, loc_A4F6C, loc_A4F6C, loc_A4084, loc_A40B2, loc_A3610
0xa321c  br       loc_A4F6C
0xa3221  ldarg.0
0xa3222  ldc.i4   0x26F
0xa3227  sub
0xa3228  switch   loc_A42D4, loc_A431A, loc_A40E0, loc_A4B9E, loc_A4BE9, loc_A4F6C, loc_A4C1C, loc_A4C37, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4348, loc_A438E, loc_A40F6
0xa3275  ldarg.0
0xa3276  ldc.i4   0x288
0xa327b  beq      loc_A465D
0xa3280  br       loc_A4F6C
0xa3285  ldarg.0
0xa3286  ldc.i4   0x2AF
0xa328b  bgt.s    loc_A32FC
0xa328d  ldarg.0
0xa328e  ldc.i4   0x292
0xa3293  sub
0xa3294  switch   loc_A3C34, loc_A4124, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A4F6C, loc_A38C2, loc_A43BC, loc_A413A, loc_A4166, loc_A43EA, loc_A4400, loc_A445E, loc_A417C
0xa32e1  ldarg.0
0xa32e2  ldc.i4   0x2AE
0xa32e7  beq      loc_A4491
0xa32ec  ldarg.0
0xa32ed  ldc.i4   0x2AF
0xa32f2  beq      loc_A44BF
0xa32f7  br       loc_A4F6C
0xa32fc  ldarg.0
0xa32fd  ldc.i4   0x2DC
0xa3302  bgt.s    loc_A3349
0xa3304  ldarg.0
0xa3305  ldc.i4   0x2BE
0xa330a  sub
0xa330b  switch   loc_A4C52, loc_A4192, loc_A4F6C, loc_A4F6C, loc_A44ED
0xa3324  ldarg.0
0xa3325  ldc.i4   0x2D8
0xa332a  sub
0xa332b  switch   loc_A451B, loc_A4531, loc_A4F6C, loc_A4547, loc_A455D
0xa3344  br       loc_A4F6C
0xa3349  ldarg.0
0xa334a  ldc.i4   0x2E3
0xa334f  beq      loc_A350C
0xa3354  ldarg.0
0xa3355  ldc.i4   0x2E6
0xa335a  beq      loc_A4573
0xa335f  br       loc_A4F6C
0xa3364  ldarg.1
0xa3365  ldstr    aMinwidth// "MinWidth"
0xa336a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xa336f  brtrue.s loc_A337C
0xa3371  ldc.i4   0x15C
0xa3376  stloc.0
0xa3377  br       loc_A4F6C
0xa337c  ldarg.1
0xa337d  ldstr    aMaxwidth// "MaxWidth"
0xa3382  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xa3387  brtrue   loc_A4F6C
0xa338c  ldc.i4   0x15C
0xa3391  stloc.0
0xa3392  br       loc_A4F6C
0xa3397  ldarg.1
0xa3398  ldstr    aMinheight// "MinHeight"
0xa339d  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xa33a2  brtrue.s loc_A33AF
0xa33a4  ldc.i4   0x15C
0xa33a9  stloc.0
0xa33aa  br       loc_A4F6C
0xa33af  ldarg.1
0xa33b0  ldstr    aMaxheight// "MaxHeight"
0xa33b5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0xa33ba  brtrue   loc_A4F6C
  ... truncated ...
```
