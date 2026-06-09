# MocompInterlacedErrorUVCommonRndCtrl_Daytona(uchar *,ulong,Buffer const *,bool,uchar const *,ulong,long,long,long,uchar)

- ea: `0x180039a94`
- end: `0x180039b40`
- name: `?MocompInterlacedErrorUVCommonRndCtrl_Daytona@@YAXPEAEKPEBTBuffer@@_NPEBEKJJJE@Z`
- size: `172`
- prototype: `void __fastcall(unsigned __int8 *, unsigned int, const union Buffer *, bool, const unsigned __int8 *, unsigned int, int, int, char, char)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180039b50`
- `0x180039bb0`

## callees

- `0x180039a94`

## import_xrefs

- `mfperfhelper!__imp_ippiMC8x4_8u_C1` at `0x180039b35`
- `mfperfhelper!__imp_ippiMC8x4_8u_C1` at `0x180039b35`

## pseudocode

```c
void __fastcall MocompInterlacedErrorUVCommonRndCtrl_Daytona(
        unsigned __int8 *a1,
        unsigned int a2,
        const union Buffer *a3,
        char a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned int a7,
        char a8,
        char a9,
        unsigned __int8 a10)
{
  if ( a6 + 2 * a6 + 7 < a2 && a2 >= 7 )
  {
    if ( !a4 )
      a3 = (const union Buffer *)((char *)a3 + 16);
    if ( (a9 & 1) != 0 )
    {
      if ( (a8 & 1) != 0 )
        ippiMC8x4_8u_C1(a5, a7, a3, 32, a1, a6, 12, a10);
      else
        ippiMC8x4_8u_C1(a5, a7, a3, 32, a1, a6, 4, a10);
    }
    else if ( (a8 & 1) != 0 )
    {
      ippiMC8x4_8u_C1(a5, a7, a3, 32, a1, a6, 8, a10);
    }
    else
    {
      ippiMC8x4_8u_C1(a5, a7, a3, 32, a1, a6, 0, a10);
    }
  }
}

```

## disassembly

```asm
0x180039a94  sub     rsp, 48h
0x180039a98  mov     r10d, [rsp+48h+arg_28]
0x180039a9d  lea     eax, ds:7[r10*2]
0x180039aa5  add     eax, r10d
0x180039aa8  cmp     eax, edx
0x180039aaa  jnb     loc_180039B3B
0x180039ab0  cmp     edx, 7
0x180039ab3  jb      loc_180039B3B
0x180039ab9  mov     edx, dword ptr [rsp+48h+arg_38]
0x180039ac0  lea     rax, [r8+10h]
0x180039ac4  test    r9b, r9b
0x180039ac7  mov     r9d, 20h ; ' '
0x180039acd  cmovz   r8, rax
0x180039ad1  movzx   eax, [rsp+48h+arg_48]
0x180039ad9  and     edx, 1
0x180039adc  mov     [rsp+48h+var_10], eax
0x180039ae0  test    [rsp+48h+arg_40], 1
0x180039ae8  jnz     short loc_180039B09
0x180039aea  test    edx, edx
0x180039aec  mov     edx, [rsp+48h+arg_30]
0x180039af3  jnz     short loc_180039AFF
0x180039af5  mov     [rsp+48h+var_18], 0
0x180039afd  jmp     short loc_180039B26
0x180039aff  mov     [rsp+48h+var_18], 8
0x180039b07  jmp     short loc_180039B26
0x180039b09  test    edx, edx
0x180039b0b  mov     edx, [rsp+48h+arg_30]
0x180039b12  jnz     short loc_180039B1E
0x180039b14  mov     [rsp+48h+var_18], 4
0x180039b1c  jmp     short loc_180039B26
0x180039b1e  mov     [rsp+48h+var_18], 0Ch
0x180039b26  mov     [rsp+48h+var_20], r10d
0x180039b2b  mov     [rsp+48h+var_28], rcx
0x180039b30  mov     rcx, [rsp+48h+arg_20]
0x180039b35  call    cs:__imp_ippiMC8x4_8u_C1
0x180039b3b  add     rsp, 48h
0x180039b3f  retn
```
