# MocompAverageAddError8x8_Daytona(uchar *,uchar *,long,uchar *,ulong,ulong,Buffer *)

- ea: `0x18000d67c`
- end: `0x18000d6ef`
- name: `?MocompAverageAddError8x8_Daytona@@YAXPEAE0J0KKPEATBuffer@@@Z`
- size: `115`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, int, unsigned __int8 *, unsigned int, unsigned int, union Buffer *)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000bbd4`
- `0x18000ca20`

## callees

- `0x18000d67c`

## import_xrefs

- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d6e4`
- `mfperfhelper!__imp_ippiMC8x8B_8u_C1` at `0x18000d6e4`

## pseudocode

```c
void __fastcall MocompAverageAddError8x8_Daytona(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned int a3,
        unsigned __int8 *a4,
        unsigned int a5,
        unsigned int a6,
        union Buffer *a7)
{
  if ( 7 * (a6 + 1) < a5 && a5 >= 8 )
    ippiMC8x8B_8u_C1(a1, a3, 0, a2, a3, 0, a7, 16, a4, a6, 0);
}

```

## disassembly

```asm
0x18000d67c  sub     rsp, 68h
0x18000d680  mov     r11d, r8d
0x18000d683  mov     r8d, [rsp+68h+arg_28]
0x18000d68b  lea     eax, [r8+1]
0x18000d68f  imul    r10d, eax, 7
0x18000d693  cmp     r10d, [rsp+68h+arg_20]
0x18000d69b  jnb     short loc_18000D6EA
0x18000d69d  cmp     [rsp+68h+arg_20], 8
0x18000d6a5  jb      short loc_18000D6EA
0x18000d6a7  mov     rax, [rsp+68h+arg_30]
0x18000d6af  mov     [rsp+68h+var_18], 0
0x18000d6b7  mov     [rsp+68h+var_20], r8d
0x18000d6bc  xor     r8d, r8d
0x18000d6bf  mov     [rsp+68h+var_28], r9
0x18000d6c4  mov     r9, rdx
0x18000d6c7  mov     [rsp+68h+var_30], 10h
0x18000d6cf  mov     edx, r11d
0x18000d6d2  mov     [rsp+68h+var_38], rax
0x18000d6d7  mov     [rsp+68h+var_40], 0
0x18000d6df  mov     [rsp+68h+var_48], r11d
0x18000d6e4  call    cs:__imp_ippiMC8x8B_8u_C1
0x18000d6ea  add     rsp, 68h
0x18000d6ee  retn
```
