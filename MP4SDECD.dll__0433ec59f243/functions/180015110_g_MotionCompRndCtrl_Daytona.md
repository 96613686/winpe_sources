# g_MotionCompRndCtrl_Daytona

- ea: `0x180015110`
- end: `0x180015199`
- name: `g_MotionCompRndCtrl_Daytona`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015110`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x180015155`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x180015168`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001517b`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001518e`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x180015155`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x180015168`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001517b`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001518e`

## pseudocode

```c
__int64 __fastcall g_MotionCompRndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        char a6,
        char a7)
{
  __int64 result; // rax

  result = (unsigned int)(a4 + 1);
  if ( 7 * (int)result < a2 && a2 >= 8 )
  {
    if ( (a7 & 1) != 0 && (a6 & 1) != 0 )
      return ippiCopy8x8HP_8u_C1R(a3, a5, a1);
    else
      return ippiCopy8x8HP_8u_C1R(a3, a5, a1);
  }
  return result;
}

```

## disassembly

```asm
0x180015110  sub     rsp, 38h
0x180015114  lea     eax, [r9+1]
0x180015118  mov     r11, r8
0x18001511b  imul    r10d, eax, 7
0x18001511f  cmp     r10d, edx
0x180015122  jnb     short loc_18001515B
0x180015124  cmp     edx, 8
0x180015127  jb      short loc_18001515B
0x180015129  mov     eax, dword ptr [rsp+38h+arg_28]
0x18001512d  mov     r8, rcx
0x180015130  mov     edx, [rsp+38h+arg_20]
0x180015134  and     eax, 1
0x180015137  test    [rsp+38h+arg_30], 1
0x18001513c  mov     rcx, r11
0x18001513f  mov     [rsp+38h+var_10], 1
0x180015147  jz      short loc_180015160
0x180015149  test    eax, eax
0x18001514b  jz      short loc_180015186
0x18001514d  mov     [rsp+38h+var_18], 3
0x180015155  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x18001515b  add     rsp, 38h
0x18001515f  retn
0x180015160  test    eax, eax
0x180015162  jnz     short loc_180015173
0x180015164  mov     [rsp+38h+var_18], eax
0x180015168  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x18001516e  add     rsp, 38h
0x180015172  retn
0x180015173  mov     [rsp+38h+var_18], 1
0x18001517b  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x180015181  add     rsp, 38h
0x180015185  retn
0x180015186  mov     [rsp+38h+var_18], 2
0x18001518e  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x180015194  add     rsp, 38h
0x180015198  retn
```
