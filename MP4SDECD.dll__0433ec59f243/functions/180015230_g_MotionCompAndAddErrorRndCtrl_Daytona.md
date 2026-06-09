# g_MotionCompAndAddErrorRndCtrl_Daytona

- ea: `0x180015230`
- end: `0x1800152b9`
- name: `g_MotionCompAndAddErrorRndCtrl_Daytona`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180015230`

## import_xrefs

- `mfperfhelper!__imp_ippiMC8x8_8u_C1` at `0x180015299`
- `mfperfhelper!__imp_ippiMC8x8_8u_C1` at `0x180015299`

## pseudocode

```c
__int64 __fastcall g_MotionCompAndAddErrorRndCtrl_Daytona(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned int a6,
        char a7,
        char a8)
{
  __int64 result; // rax

  result = (unsigned int)(a5 + 1);
  if ( 7 * (int)result < a2 && a2 >= 8 )
  {
    if ( (a8 & 1) != 0 )
    {
      if ( (a7 & 1) != 0 )
        return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 12, 1);
      else
        return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 4, 1);
    }
    else if ( (a7 & 1) != 0 )
    {
      return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 8, 1);
    }
    else
    {
      return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 0, 1);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180015230  push    rbx
0x180015232  sub     rsp, 40h
0x180015236  mov     r11d, [rsp+48h+arg_20]
0x18001523b  mov     rbx, r9
0x18001523e  lea     eax, [r11+1]
0x180015242  imul    r10d, eax, 7
0x180015246  cmp     r10d, edx
0x180015249  jnb     short loc_18001529F
0x18001524b  cmp     edx, 8
0x18001524e  jb      short loc_18001529F
0x180015250  mov     eax, dword ptr [rsp+48h+arg_30]
0x180015257  mov     r9d, 10h
0x18001525d  mov     edx, [rsp+48h+arg_28]
0x180015261  and     eax, 1
0x180015264  test    [rsp+48h+arg_38], 1
0x18001526c  mov     [rsp+48h+var_10], 1
0x180015274  jnz     short loc_180015280
0x180015276  test    eax, eax
0x180015278  jnz     short loc_1800152A5
0x18001527a  mov     [rsp+48h+var_18], eax
0x18001527e  jmp     short loc_18001528C
0x180015280  test    eax, eax
0x180015282  jz      short loc_1800152AF
0x180015284  mov     [rsp+48h+var_18], 0Ch
0x18001528c  mov     [rsp+48h+var_20], r11d
0x180015291  mov     [rsp+48h+var_28], rcx
0x180015296  mov     rcx, rbx
0x180015299  call    cs:__imp_ippiMC8x8_8u_C1
0x18001529f  add     rsp, 40h
0x1800152a3  pop     rbx
0x1800152a4  retn
0x1800152a5  mov     [rsp+48h+var_18], 8
0x1800152ad  jmp     short loc_18001528C
0x1800152af  mov     [rsp+48h+var_18], 4
0x1800152b7  jmp     short loc_18001528C
```
