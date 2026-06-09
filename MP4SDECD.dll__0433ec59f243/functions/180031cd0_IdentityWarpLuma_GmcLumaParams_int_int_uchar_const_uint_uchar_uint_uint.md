# IdentityWarpLuma(GmcLumaParams *,int,int,uchar const *,uint,uchar *,uint,uint)

- ea: `0x180031cd0`
- end: `0x180031d25`
- name: `?IdentityWarpLuma@@YAXPEAUGmcLumaParams@@HHPEBEIPEAEII@Z`
- size: `85`
- prototype: `void __fastcall(struct GmcLumaParams *, int, int, const unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180031cd0`

## import_xrefs

- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180031d19`
- `mfperfhelper!__imp_ippiCopy16x16_8u_C1R` at `0x180031d19`

## pseudocode

```c
void __fastcall IdentityWarpLuma(
        struct GmcLumaParams *a1,
        int a2,
        int a3,
        const unsigned __int8 *a4,
        unsigned int a5,
        unsigned __int8 *a6,
        unsigned int a7,
        unsigned int a8)
{
  if ( a8 >= 16 * a7 && 15 * (a7 + 1) < a8 && a8 >= 0x10 )
    ippiCopy16x16_8u_C1R(&a4[a5 * a3 + a2], a5, a6, a7);
}

```

## disassembly

```asm
0x180031cd0  push    rbx
0x180031cd2  sub     rsp, 20h
0x180031cd6  mov     r10d, [rsp+28h+arg_38]
0x180031cdb  mov     r11, r9
0x180031cde  mov     r9d, [rsp+28h+arg_30]
0x180031ce3  mov     eax, r9d
0x180031ce6  shl     eax, 4
0x180031ce9  movsxd  rbx, edx
0x180031cec  cmp     r10d, eax
0x180031cef  jb      short loc_180031D1F
0x180031cf1  lea     eax, [r9+1]
0x180031cf5  imul    ecx, eax, 0Fh
0x180031cf8  cmp     ecx, r10d
0x180031cfb  jnb     short loc_180031D1F
0x180031cfd  cmp     r10d, 10h
0x180031d01  jb      short loc_180031D1F
0x180031d03  mov     edx, [rsp+28h+arg_20]
0x180031d07  imul    r8d, edx
0x180031d0b  mov     ecx, r8d
0x180031d0e  mov     r8, [rsp+28h+arg_28]
0x180031d13  add     rcx, r11
0x180031d16  add     rcx, rbx
0x180031d19  call    cs:__imp_ippiCopy16x16_8u_C1R
0x180031d1f  add     rsp, 20h
0x180031d23  pop     rbx
0x180031d24  retn
```
