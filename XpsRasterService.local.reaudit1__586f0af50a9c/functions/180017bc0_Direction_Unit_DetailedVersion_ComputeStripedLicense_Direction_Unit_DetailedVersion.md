# Direction::Unit::DetailedVersion::ComputeStripedLicense(Direction::Unit::DetailedVersion &)

- ea: `0x180017bc0`
- end: `0x18001862f`
- name: `?ComputeStripedLicense@DetailedVersion@Unit@Direction@@SA?AW4Result@Setting@@AEAV123@@Z`
- size: `2671`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x18000e4b0`
- `0x180017bc0`
- `0x180018b30`
- `0x1800bf3b0`

## pseudocode

```c
__int64 __fastcall Direction::Unit::DetailedVersion::ComputeStripedLicense(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  void (__fastcall *MixedProvider)(void *, unsigned __int64, __int64); // rax
  __int64 v6; // rcx
  bool v7; // sf
  int v8; // [rsp+38h] [rbp-38h]
  int v9; // [rsp+38h] [rbp-38h]
  int v10; // [rsp+38h] [rbp-38h]
  _BYTE *retaddr; // [rsp+78h] [rbp+8h]

  if ( ~(~(~(~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)
           | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) ^ 0x5D00BCE0
             | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)))
         | 0x90020C)
       | ~(~(~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)
           | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) ^ 0x5D00BCE0
             | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)))
         ^ 0x90020C
         | ~(~(~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)
             | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) ^ 0x5D00BCE0
               | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x5D00BCE0)))
           | 0x90020C))) == ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                            ^ 0x5D90BEEC
                            | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                              | 0x5D90BEEC))
                          + (~(~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                               | 0x5D90BEEC)
                             | (7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                             & 0x5D90BEEC)
                           | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                             ^ 0x5D90BEEC
                             | ~((7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                               | 0x5D90BEEC)))
                          - 7694937 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage
                          - 1569767148 )
    goto LABEL_9;
  v8 = 9781772 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage;
  if ( ~(~(~(~(v8 | 0x878814A4) | v8 & 0x878814A4) | 0x510848) | ~(~(v8 | 0x878814A4) | v8 & 0x878814A4) & 0x510848) != ~(v8 ^ 0x87D91CEC | ~(v8 | 0x87D91CEC)) + (v8 ^ 0x87D91CEC ^ v8 & 0x87D91CEC | (v8 ^ 0x87D91CEC) & v8 & 0x87D91CEC) - v8 + 2015814420 )
  {
    if ( ~(~(~(~((3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x30280431)
             | (3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) & 0x30280431)
           | 0x14020C)
         | ~(~((3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) | 0x30280431)
           | (3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage) & 0x30280431)
         & 0x14020C) == ~((3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                        ^ 0x303C063D
                        | ~((3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                          | 0x303C063D))
                      + ((3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                       ^ 0x303C063D
                       | (3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage)
                       & 0x303C063D)
                      - 3443575 * *(unsigned __int8 *)Direction::Unit::DetailedVersion::RequestMixedPackage
                      - 809240125 )
    {
      v6 = *((char *)Direction::Unit::DetailedVersion::RequestMixedPackage + 1);
      v7 = (v6 & 0x80u) != 0LL;
      if ( (char)v6 > 0 )
      {
        if ( (__int64)&loc_180018B32 > 0x7FFFFFFFFFFFFFFFLL - v6 )
          goto LABEL_21;
        v7 = (v6 & 0x80u) != 0LL;
      }
      if ( !v7 || (__int64)&loc_180018B32 >= (__int64)(0x8000000000000000uLL - v6) )
      {
        v10 = 9781772 * *((unsigned __int8 *)&loc_180018B32 + v6);
        if ( ~(~(~(~(v10 | 0x7670A100) | v10 & 0x7670A100) | 0x800090)
             | ~(~(v10 | 0x7670A100) | v10 & 0x7670A100) & 0x800090) == ~(v10 ^ 0x76F0A190 | ~(v10 | 0x76F0A190))
                                                                      + (v10 ^ 0x76F0A190 | v10 & 0x76F0A190)
                                                                      - v10
                                                                      - 1995481488 )
          goto LABEL_9;
      }
    }
LABEL_21:
    v3 = IntegralRelation::OddMap;
    goto LABEL_10;
  }
  v2 = *(int *)((char *)Direction::Unit::DetailedVersion::RequestMixedPackage + 1);
  if ( v2 <= 0 )
  {
    if ( v2 < 0 && (__int64)&loc_180018B32 + 3 < (__int64)(0x8000000000000000uLL - v2) )
      goto LABEL_21;
    goto LABEL_8;
  }
  if ( (__int64)&loc_180018B32 + 3 <= 0x7FFFFFFFFFFFFFFFLL - v2 )
  {
LABEL_8:
    v9 = 7694937 * *((unsigned __int8 *)&loc_180018B32 + v2 + 3);
    if ( ~(~(~(~(v9 | 0x5D00BCE0) | v9 & 0x5D00BCE0) | 0x90020C) | ~(~(v9 | 0x5D00BCE0) | v9 & 0x5D00BCE0) & 0x90020C) == ~(v9 ^ 0x5D90BEEC | ~(v9 | 0x5D90BEEC)) + (v9 ^ 0x5D90BEEC | v9 & 0x5D90BEEC) - v9 - 1569767148 )
    {
LABEL_9:
      v3 = ++IntegralRelation::OddMap;
      goto LABEL_10;
    }
    goto LABEL_21;
  }
  v3 = IntegralRelation::OddMap;
LABEL_10:
  if ( *retaddr == (unsigned __int8)(((unsigned int)v3 ^ 0xFFF72BBB) / 0x5441E)
    || ((unsigned int)v3 ^ 0xFBA5EA10) != 0x608643 )
  {
    v3 = (unsigned int)(v3 + 1);
    IntegralRelation::OddMap = v3;
  }
  MixedProvider = (void (__fastcall *)(void *, unsigned __int64, __int64))GenerateMixedProvider(
                                                                            0x6FFFFFDFC0005060LL,
                                                                            2168717322LL,
                                                                            v3);
  MixedProvider(
    &Direction::Unit::DetailedVersion::ComputeStripedLicense,
    (unsigned __int64)&Direction::Unit::DetailedVersion::ComputeStripedLicense ^ 0x1791D4,
    496068);
  return Direction::Unit::DetailedVersion::RequestMixedPackage(a1);
}

```

## disassembly

```asm
0x180017bc0  mov     [rsp-8+arg_8], rbx
0x180017bc5  push    rbp
0x180017bc6  mov     rbp, rsp
0x180017bc9  sub     rsp, 70h
0x180017bcd  mov     rbx, rcx
0x180017bd0  mov     [rbp+var_20], 5D00BCE0h
0x180017bd7  lea     r9, ?RequestMixedPackage@DetailedVersion@Unit@Direction@@QEAA?AW4Result@Setting@@XZ; Direction::Unit::DetailedVersion::RequestMixedPackage(void)
0x180017bde  movzx   eax, byte ptr [r9]
0x180017be2  mov     [rbp+var_10], eax
0x180017be5  mov     eax, [rbp+var_10]
0x180017be8  imul    ecx, eax, 756A59h
0x180017bee  mov     eax, [rbp+var_20]
0x180017bf1  mov     [rbp+var_48], eax
0x180017bf4  mov     [rbp+var_28], ecx
0x180017bf7  mov     eax, [rbp+var_28]
0x180017bfa  mov     [rbp+var_38], eax
0x180017bfd  mov     eax, [rbp+var_48]
0x180017c00  mov     [rbp+var_18], eax
0x180017c03  mov     eax, [rbp+var_38]
0x180017c06  mov     [rbp+var_48], eax
0x180017c09  mov     ecx, [rbp+var_48]
0x180017c0c  mov     eax, [rbp+var_18]
0x180017c0f  or      ecx, eax
0x180017c11  mov     [rbp+var_48], ecx
0x180017c14  mov     eax, [rbp+var_48]
0x180017c17  not     eax
0x180017c19  mov     [rbp+var_30], eax
0x180017c1c  mov     eax, [rbp+var_20]
0x180017c1f  mov     [rbp+var_20], eax
0x180017c22  mov     eax, [rbp+var_28]
0x180017c25  mov     [rbp+var_28], eax
0x180017c28  mov     eax, [rbp+var_20]
0x180017c2b  mov     [rbp+var_38], eax
0x180017c2e  mov     eax, [rbp+var_28]
0x180017c31  mov     [rbp+var_48], eax
0x180017c34  mov     ecx, [rbp+var_48]
0x180017c37  mov     eax, [rbp+var_38]
0x180017c3a  xor     ecx, eax
0x180017c3c  mov     eax, [rbp+var_20]
0x180017c3f  mov     [rbp+var_38], eax
0x180017c42  mov     eax, [rbp+var_28]
0x180017c45  mov     [rbp+var_48], eax
0x180017c48  mov     [rbp+var_18], ecx
0x180017c4b  mov     ecx, [rbp+var_48]
0x180017c4e  mov     eax, [rbp+var_38]
0x180017c51  or      ecx, eax
0x180017c53  not     ecx
0x180017c55  mov     [rbp+var_20], 90020Ch
0x180017c5c  mov     [rbp+var_48], ecx
0x180017c5f  mov     ecx, [rbp+var_48]
0x180017c62  mov     eax, [rbp+var_18]
0x180017c65  or      ecx, eax
0x180017c67  not     ecx
0x180017c69  mov     [rbp+var_48], ecx
0x180017c6c  mov     ecx, [rbp+var_48]
0x180017c6f  mov     eax, [rbp+var_30]
0x180017c72  or      ecx, eax
0x180017c74  mov     eax, [rbp+var_20]
0x180017c77  not     ecx
0x180017c79  mov     [rbp+var_30], eax
0x180017c7c  mov     [rbp+var_28], ecx
0x180017c7f  mov     eax, [rbp+var_28]
0x180017c82  mov     [rbp+var_48], eax
0x180017c85  mov     eax, [rbp+var_30]
0x180017c88  mov     [rbp+var_38], eax
0x180017c8b  mov     eax, [rbp+var_48]
0x180017c8e  mov     [rbp+var_30], eax
0x180017c91  mov     ecx, [rbp+var_30]
0x180017c94  mov     eax, [rbp+var_38]
0x180017c97  or      ecx, eax
0x180017c99  mov     [rbp+var_30], ecx
0x180017c9c  mov     eax, [rbp+var_30]
0x180017c9f  not     eax
0x180017ca1  mov     [rbp+var_18], eax
0x180017ca4  mov     eax, [rbp+var_20]
0x180017ca7  mov     [rbp+var_20], eax
0x180017caa  mov     eax, [rbp+var_28]
0x180017cad  mov     [rbp+var_28], eax
0x180017cb0  mov     eax, [rbp+var_20]
0x180017cb3  mov     [rbp+var_48], eax
0x180017cb6  mov     eax, [rbp+var_28]
0x180017cb9  mov     [rbp+var_30], eax
0x180017cbc  mov     ecx, [rbp+var_30]
0x180017cbf  mov     eax, [rbp+var_48]
0x180017cc2  xor     ecx, eax
0x180017cc4  mov     eax, [rbp+var_20]
0x180017cc7  mov     [rbp+var_48], eax
0x180017cca  mov     eax, [rbp+var_28]
0x180017ccd  mov     [rbp+var_30], eax
0x180017cd0  mov     [rbp+var_38], ecx
0x180017cd3  mov     ecx, [rbp+var_30]
0x180017cd6  mov     eax, [rbp+var_48]
0x180017cd9  or      ecx, eax
0x180017cdb  not     ecx
0x180017cdd  mov     [rbp+var_20], 5D00BCE0h
0x180017ce4  mov     [rbp+var_30], ecx
0x180017ce7  mov     ecx, [rbp+var_30]
0x180017cea  mov     eax, [rbp+var_38]
0x180017ced  or      ecx, eax
0x180017cef  not     ecx
0x180017cf1  mov     [rbp+var_28], 90020Ch
0x180017cf8  mov     [rbp+var_30], ecx
0x180017cfb  mov     r8d, [rbp+var_30]
0x180017cff  mov     eax, [rbp+var_18]
0x180017d02  or      r8d, eax
0x180017d05  mov     eax, [rbp+var_20]
0x180017d08  not     r8d
0x180017d0b  mov     [rbp+var_30], eax
0x180017d0e  mov     eax, [rbp+var_28]
0x180017d11  mov     [rbp+var_48], eax
0x180017d14  mov     eax, [rbp+var_30]
0x180017d17  mov     [rbp+var_38], eax
0x180017d1a  mov     eax, [rbp+var_48]
0x180017d1d  mov     [rbp+var_30], eax
0x180017d20  mov     ecx, [rbp+var_30]
0x180017d23  mov     eax, [rbp+var_38]
0x180017d26  or      ecx, eax
0x180017d28  mov     [rbp+var_30], ecx
0x180017d2b  mov     eax, [rbp+var_30]
0x180017d2e  not     eax
0x180017d30  mov     [rbp+var_18], eax
0x180017d33  mov     eax, [rbp+var_20]
0x180017d36  mov     [rbp+var_20], eax
0x180017d39  mov     eax, [rbp+var_28]
0x180017d3c  mov     [rbp+var_28], eax
0x180017d3f  mov     eax, [rbp+var_20]
0x180017d42  mov     [rbp+var_48], eax
0x180017d45  mov     eax, [rbp+var_28]
0x180017d48  mov     [rbp+var_30], eax
0x180017d4b  mov     ecx, [rbp+var_30]
0x180017d4e  mov     eax, [rbp+var_48]
0x180017d51  xor     ecx, eax
0x180017d53  mov     eax, [rbp+var_20]
0x180017d56  mov     [rbp+var_48], eax
0x180017d59  mov     eax, [rbp+var_28]
0x180017d5c  mov     [rbp+var_30], eax
0x180017d5f  mov     [rbp+var_38], ecx
0x180017d62  mov     ecx, [rbp+var_30]
0x180017d65  mov     eax, [rbp+var_48]
0x180017d68  or      ecx, eax
0x180017d6a  not     ecx
0x180017d6c  mov     [rbp+var_30], ecx
0x180017d6f  mov     ecx, [rbp+var_30]
0x180017d72  mov     eax, [rbp+var_38]
0x180017d75  or      ecx, eax
0x180017d77  not     ecx
0x180017d79  mov     [rbp+var_30], ecx
0x180017d7c  mov     ecx, [rbp+var_30]
0x180017d7f  mov     eax, [rbp+var_18]
0x180017d82  or      ecx, eax
0x180017d84  mov     eax, [rbp+var_10]
0x180017d87  not     ecx
0x180017d89  mov     [rbp+var_20], ecx
0x180017d8c  imul    ecx, eax, 756A59h
0x180017d92  mov     eax, [rbp+var_20]
0x180017d95  mov     [rbp+var_38], eax
0x180017d98  mov     [rbp+var_28], ecx
0x180017d9b  mov     eax, [rbp+var_28]
0x180017d9e  mov     [rbp+var_48], eax
0x180017da1  mov     eax, [rbp+var_38]
0x180017da4  mov     [rbp+var_10], eax
0x180017da7  mov     eax, [rbp+var_48]
0x180017daa  mov     [rbp+var_18], eax
0x180017dad  mov     eax, [rbp+var_10]
0x180017db0  mov     [rbp+var_40], eax
0x180017db3  mov     eax, [rbp+var_18]
0x180017db6  mov     [rbp+var_30], eax
0x180017db9  mov     ecx, [rbp+var_30]
0x180017dbc  mov     eax, [rbp+var_40]
0x180017dbf  or      ecx, eax
0x180017dc1  mov     eax, [rbp+var_10]
0x180017dc4  not     ecx
0x180017dc6  mov     [rbp+var_30], eax
0x180017dc9  mov     eax, [rbp+var_18]
0x180017dcc  mov     [rbp+var_40], eax
0x180017dcf  mov     [rbp+var_50], ecx
0x180017dd2  mov     ecx, [rbp+var_40]
0x180017dd5  mov     eax, [rbp+var_30]
0x180017dd8  and     ecx, eax
0x180017dda  mov     [rbp+var_40], ecx
0x180017ddd  mov     ecx, [rbp+var_40]
0x180017de0  mov     eax, [rbp+var_50]
0x180017de3  or      ecx, eax
0x180017de5  mov     eax, [rbp+var_38]
0x180017de8  not     ecx
0x180017dea  mov     [rbp+var_38], eax
0x180017ded  mov     eax, [rbp+var_48]
0x180017df0  mov     [rbp+var_48], eax
0x180017df3  mov     eax, [rbp+var_38]
0x180017df6  mov     [rbp+var_40], eax
0x180017df9  mov     eax, [rbp+var_48]
0x180017dfc  mov     [rbp+var_50], eax
0x180017dff  mov     [rbp+var_18], ecx
0x180017e02  mov     ecx, [rbp+var_50]
0x180017e05  mov     eax, [rbp+var_40]
0x180017e08  xor     ecx, eax
0x180017e0a  mov     eax, [rbp+var_38]
0x180017e0d  mov     [rbp+var_40], eax
0x180017e10  mov     eax, [rbp+var_48]
0x180017e13  mov     [rbp+var_50], eax
0x180017e16  mov     [rbp+var_30], ecx
0x180017e19  mov     ecx, [rbp+var_50]
0x180017e1c  mov     eax, [rbp+var_40]
0x180017e1f  or      ecx, eax
0x180017e21  not     ecx
0x180017e23  mov     [rbp+var_50], ecx
0x180017e26  mov     ecx, [rbp+var_50]
0x180017e29  mov     eax, [rbp+var_30]
0x180017e2c  or      ecx, eax
0x180017e2e  not     ecx
0x180017e30  mov     [rbp+var_50], ecx
0x180017e33  mov     edx, [rbp+var_50]
0x180017e36  mov     eax, [rbp+var_18]
0x180017e39  or      edx, eax
0x180017e3b  mov     eax, [rbp+var_20]
0x180017e3e  mov     [rbp+var_48], eax
0x180017e41  mov     eax, [rbp+var_28]
0x180017e44  mov     [rbp+var_38], eax
0x180017e47  mov     eax, [rbp+var_48]
0x180017e4a  mov     [rbp+var_40], eax
0x180017e4d  mov     eax, [rbp+var_38]
0x180017e50  mov     [rbp+var_50], eax
0x180017e53  mov     ecx, [rbp+var_50]
0x180017e56  mov     eax, [rbp+var_40]
0x180017e59  xor     ecx, eax
0x180017e5b  mov     eax, [rbp+var_48]
0x180017e5e  mov     [rbp+var_30], ecx
0x180017e61  mov     [rbp+var_40], eax
0x180017e64  mov     eax, [rbp+var_38]
0x180017e67  mov     [rbp+var_50], eax
0x180017e6a  mov     ecx, [rbp+var_50]
0x180017e6d  mov     eax, [rbp+var_40]
0x180017e70  or      ecx, eax
0x180017e72  not     ecx
0x180017e74  mov     [rbp+var_50], ecx
0x180017e77  mov     ecx, [rbp+var_50]
0x180017e7a  mov     eax, [rbp+var_30]
0x180017e7d  or      ecx, eax
0x180017e7f  mov     eax, [rbp+var_28]
0x180017e82  not     ecx
0x180017e84  add     edx, ecx
0x180017e86  sub     edx, eax
0x180017e88  mov     eax, [rbp+var_20]
0x180017e8b  sub     edx, eax
0x180017e8d  cmp     r8d, edx
0x180017e90  jz      loc_180018238
0x180017e96  movzx   eax, byte ptr [r9]
0x180017e9a  mov     [rbp+var_18], eax
0x180017e9d  mov     eax, [rbp+var_18]
0x180017ea0  imul    ecx, eax, 95420Ch
0x180017ea6  mov     [rbp+var_48], 878814A4h
0x180017ead  mov     eax, [rbp+var_48]
0x180017eb0  mov     [rbp+var_40], eax
0x180017eb3  mov     [rbp+var_38], ecx
0x180017eb6  mov     eax, [rbp+var_38]
0x180017eb9  mov     [rbp+var_50], eax
0x180017ebc  mov     ecx, [rbp+var_50]
0x180017ebf  mov     eax, [rbp+var_40]
0x180017ec2  or      ecx, eax
0x180017ec4  mov     eax, [rbp+var_48]
0x180017ec7  not     ecx
0x180017ec9  mov     [rbp+var_40], eax
0x180017ecc  mov     eax, [rbp+var_38]
0x180017ecf  mov     [rbp+var_50], eax
0x180017ed2  mov     [rbp+var_30], ecx
0x180017ed5  mov     ecx, [rbp+var_50]
0x180017ed8  mov     eax, [rbp+var_40]
0x180017edb  and     ecx, eax
0x180017edd  mov     [rbp+var_50], ecx
0x180017ee0  mov     ecx, [rbp+var_50]
0x180017ee3  mov     eax, [rbp+var_30]
0x180017ee6  or      ecx, eax
0x180017ee8  not     ecx
0x180017eea  mov     [rbp+var_48], 510848h
0x180017ef1  mov     eax, [rbp+var_48]
0x180017ef4  mov     [rbp+var_38], ecx
0x180017ef7  mov     [rbp+var_40], eax
0x180017efa  mov     eax, [rbp+var_38]
0x180017efd  mov     [rbp+var_50], eax
0x180017f00  mov     ecx, [rbp+var_50]
0x180017f03  mov     eax, [rbp+var_40]
0x180017f06  or      ecx, eax
0x180017f08  mov     eax, [rbp+var_48]
0x180017f0b  not     ecx
0x180017f0d  mov     [rbp+var_40], eax
0x180017f10  mov     eax, [rbp+var_38]
0x180017f13  mov     [rbp+var_50], eax
0x180017f16  mov     [rbp+var_30], ecx
0x180017f19  mov     ecx, [rbp+var_50]
0x180017f1c  mov     eax, [rbp+var_40]
0x180017f1f  and     ecx, eax
0x180017f21  mov     [rbp+var_50], ecx
0x180017f24  mov     r8d, [rbp+var_50]
0x180017f28  mov     eax, [rbp+var_30]
0x180017f2b  or      r8d, eax
0x180017f2e  mov     [rbp+var_48], 878814A4h
0x180017f35  not     r8d
0x180017f38  mov     eax, [rbp+var_48]
0x180017f3b  mov     [rbp+var_40], eax
0x180017f3e  mov     [rbp+var_38], 510848h
  ... truncated ...
```
