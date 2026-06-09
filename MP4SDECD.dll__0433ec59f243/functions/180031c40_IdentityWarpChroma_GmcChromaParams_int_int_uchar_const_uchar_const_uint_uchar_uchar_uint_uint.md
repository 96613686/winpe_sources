# IdentityWarpChroma(GmcChromaParams *,int,int,uchar const *,uchar const *,uint,uchar *,uchar *,uint,uint)

- ea: `0x180031c40`
- end: `0x180031cbc`
- name: `?IdentityWarpChroma@@YAXPEAUGmcChromaParams@@HHPEBE1IPEAE2II@Z`
- size: `124`
- prototype: `void __fastcall(struct GmcChromaParams *, int, int, const unsigned __int8 *, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031c40`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180031c91`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180031cab`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180031c91`
- `mfperfhelper!__imp_ippiCopy8x8_8u_C1R` at `0x180031cab`

## pseudocode

```c
void __fastcall IdentityWarpChroma(
        struct GmcChromaParams *a1,
        int a2,
        int a3,
        const unsigned __int8 *a4,
        const unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned __int8 *a8,
        unsigned int a9,
        unsigned int a10)
{
  __int64 v10; // r8
  __int64 v11; // rbx

  if ( a10 >= 8 * a9 && 7 * (a9 + 1) < a10 && a10 >= 8 )
  {
    v10 = (a2 >> 1) + a6 * (a3 >> 1);
    v11 = (unsigned int)v10;
    ippiCopy8x8_8u_C1R(&a4[v10], a6, a7, a9);
    ippiCopy8x8_8u_C1R(&a5[v11], a6, a8, a9);
  }
}

```

## disassembly

```asm
0x180031c40  mov     [rsp+arg_0], rbx
0x180031c45  push    rsi
0x180031c46  sub     rsp, 20h
0x180031c4a  mov     esi, [rsp+28h+arg_40]
0x180031c4e  mov     r10d, [rsp+28h+arg_48]
0x180031c53  lea     eax, ds:0[rsi*8]
0x180031c5a  cmp     r10d, eax
0x180031c5d  jb      short loc_180031CB1
0x180031c5f  lea     eax, [rsi+1]
0x180031c62  imul    ecx, eax, 7
0x180031c65  cmp     ecx, r10d
0x180031c68  jnb     short loc_180031CB1
0x180031c6a  cmp     r10d, 8
0x180031c6e  jb      short loc_180031CB1
0x180031c70  sar     r8d, 1
0x180031c73  imul    r8d, [rsp+28h+arg_28]
0x180031c79  sar     edx, 1
0x180031c7b  add     r8d, edx
0x180031c7e  mov     edx, [rsp+28h+arg_28]
0x180031c82  mov     ebx, r8d
0x180031c85  lea     rcx, [r8+r9]
0x180031c89  mov     r8, [rsp+28h+arg_30]
0x180031c8e  mov     r9d, esi
0x180031c91  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180031c97  mov     rcx, [rsp+28h+arg_20]
0x180031c9c  mov     r9d, esi
0x180031c9f  mov     r8, [rsp+28h+arg_38]
0x180031ca4  add     rcx, rbx
0x180031ca7  mov     edx, [rsp+28h+arg_28]
0x180031cab  call    cs:__imp_ippiCopy8x8_8u_C1R
0x180031cb1  mov     rbx, [rsp+28h+arg_0]
0x180031cb6  add     rsp, 20h
0x180031cba  pop     rsi
0x180031cbb  retn
```
