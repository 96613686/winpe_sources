# g_MotionComp_Daytona

- ea: `0x1800151a0`
- end: `0x180015229`
- name: `g_MotionComp_Daytona`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800151a0`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x1800151e5`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x1800151f8`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001520b`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001521e`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x1800151e5`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x1800151f8`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001520b`
- `mfperfhelper!__imp_ippiCopy8x8HP_8u_C1R` at `0x18001521e`

## pseudocode

```c
__int64 __fastcall g_MotionComp_Daytona(
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
0x1800151a0  sub     rsp, 38h
0x1800151a4  lea     eax, [r9+1]
0x1800151a8  mov     r11, r8
0x1800151ab  imul    r10d, eax, 7
0x1800151af  cmp     r10d, edx
0x1800151b2  jnb     short loc_1800151EB
0x1800151b4  cmp     edx, 8
0x1800151b7  jb      short loc_1800151EB
0x1800151b9  mov     eax, dword ptr [rsp+38h+arg_28]
0x1800151bd  mov     r8, rcx
0x1800151c0  mov     edx, [rsp+38h+arg_20]
0x1800151c4  and     eax, 1
0x1800151c7  test    [rsp+38h+arg_30], 1
0x1800151cc  mov     rcx, r11
0x1800151cf  mov     [rsp+38h+var_10], 0
0x1800151d7  jz      short loc_1800151F0
0x1800151d9  test    eax, eax
0x1800151db  jz      short loc_180015216
0x1800151dd  mov     [rsp+38h+var_18], 3
0x1800151e5  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x1800151eb  add     rsp, 38h
0x1800151ef  retn
0x1800151f0  test    eax, eax
0x1800151f2  jnz     short loc_180015203
0x1800151f4  mov     [rsp+38h+var_18], eax
0x1800151f8  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x1800151fe  add     rsp, 38h
0x180015202  retn
0x180015203  mov     [rsp+38h+var_18], 1
0x18001520b  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x180015211  add     rsp, 38h
0x180015215  retn
0x180015216  mov     [rsp+38h+var_18], 2
0x18001521e  call    cs:__imp_ippiCopy8x8HP_8u_C1R
0x180015224  add     rsp, 38h
0x180015228  retn
```
