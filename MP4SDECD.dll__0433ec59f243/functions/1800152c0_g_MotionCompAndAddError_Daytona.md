# g_MotionCompAndAddError_Daytona

- ea: `0x1800152c0`
- end: `0x180015349`
- name: `g_MotionCompAndAddError_Daytona`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800152c0`

## import_xrefs

- `mfperfhelper!__imp_ippiMC8x8_8u_C1` at `0x180015329`
- `mfperfhelper!__imp_ippiMC8x8_8u_C1` at `0x180015329`

## pseudocode

```c
__int64 __fastcall g_MotionCompAndAddError_Daytona(
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
        return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 12, 0);
      else
        return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 4, 0);
    }
    else if ( (a7 & 1) != 0 )
    {
      return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 8, 0);
    }
    else
    {
      return ippiMC8x8_8u_C1(a4, a6, a3, 16, a1, a5, 0, 0);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800152c0  push    rbx
0x1800152c2  sub     rsp, 40h
0x1800152c6  mov     r11d, [rsp+48h+arg_20]
0x1800152cb  mov     rbx, r9
0x1800152ce  lea     eax, [r11+1]
0x1800152d2  imul    r10d, eax, 7
0x1800152d6  cmp     r10d, edx
0x1800152d9  jnb     short loc_18001532F
0x1800152db  cmp     edx, 8
0x1800152de  jb      short loc_18001532F
0x1800152e0  mov     eax, dword ptr [rsp+48h+arg_30]
0x1800152e7  mov     r9d, 10h
0x1800152ed  mov     edx, [rsp+48h+arg_28]
0x1800152f1  and     eax, 1
0x1800152f4  test    [rsp+48h+arg_38], 1
0x1800152fc  mov     [rsp+48h+var_10], 0
0x180015304  jnz     short loc_180015310
0x180015306  test    eax, eax
0x180015308  jnz     short loc_180015335
0x18001530a  mov     [rsp+48h+var_18], eax
0x18001530e  jmp     short loc_18001531C
0x180015310  test    eax, eax
0x180015312  jz      short loc_18001533F
0x180015314  mov     [rsp+48h+var_18], 0Ch
0x18001531c  mov     [rsp+48h+var_20], r11d
0x180015321  mov     [rsp+48h+var_28], rcx
0x180015326  mov     rcx, rbx
0x180015329  call    cs:__imp_ippiMC8x8_8u_C1
0x18001532f  add     rsp, 40h
0x180015333  pop     rbx
0x180015334  retn
0x180015335  mov     [rsp+48h+var_18], 8
0x18001533d  jmp     short loc_18001531C
0x18001533f  mov     [rsp+48h+var_18], 4
0x180015347  jmp     short loc_18001531C
```
