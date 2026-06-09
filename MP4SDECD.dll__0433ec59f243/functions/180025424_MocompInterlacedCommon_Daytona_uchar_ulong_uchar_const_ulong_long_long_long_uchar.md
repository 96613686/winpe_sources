# MocompInterlacedCommon_Daytona(uchar *,ulong,uchar const *,ulong,long,long,long,uchar)

- ea: `0x180025424`
- end: `0x180025499`
- name: `?MocompInterlacedCommon_Daytona@@YAXPEAEKPEBEKJJJE@Z`
- size: `117`
- prototype: `void __fastcall(unsigned __int8 *, unsigned int, const unsigned __int8 *, unsigned int, int, int, char, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800253f0`
- `0x180039c10`

## callees

- `0x180025424`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x4HP_8u_C1R` at `0x18002546c`
- `mfperfhelper!__imp_ippiCopy8x4HP_8u_C1R` at `0x18002546c`

## pseudocode

```c
void __fastcall MocompInterlacedCommon_Daytona(
        unsigned __int8 *a1,
        unsigned int a2,
        const unsigned __int8 *a3,
        int a4,
        unsigned int a5)
{
  if ( a4 + 2 * a4 + 7 < a2 && a2 >= 7 )
    ippiCopy8x4HP_8u_C1R(a3, a5, a1);
}

```

## disassembly

```asm
0x180025424  sub     rsp, 38h
0x180025428  lea     eax, ds:7[r9*2]
0x180025430  mov     r10, r8
0x180025433  add     eax, r9d
0x180025436  cmp     eax, edx
0x180025438  jnb     short loc_180025472
0x18002543a  cmp     edx, 7
0x18002543d  jb      short loc_180025472
0x18002543f  movzx   edx, [rsp+38h+arg_38]
0x180025444  mov     r8, rcx
0x180025447  mov     eax, [rsp+38h+arg_28]
0x18002544b  mov     rcx, r10
0x18002544e  and     eax, 1
0x180025451  mov     [rsp+38h+var_10], edx
0x180025455  test    [rsp+38h+arg_30], 1
0x18002545a  mov     edx, [rsp+38h+arg_20]
0x18002545e  jnz     short loc_180025481
0x180025460  test    eax, eax
0x180025462  jz      short loc_180025477
0x180025464  mov     [rsp+38h+var_18], 1
0x18002546c  call    cs:__imp_ippiCopy8x4HP_8u_C1R
0x180025472  add     rsp, 38h
0x180025476  retn
0x180025477  mov     [rsp+38h+var_18], 0
0x18002547f  jmp     short loc_18002546C
0x180025481  test    eax, eax
0x180025483  jnz     short loc_18002548F
0x180025485  mov     [rsp+38h+var_18], 2
0x18002548d  jmp     short loc_18002546C
0x18002548f  mov     [rsp+38h+var_18], 3
0x180025497  jmp     short loc_18002546C
```
