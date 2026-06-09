# UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x1800431f0`
- end: `0x1800432b3`
- name: `?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `195`
- prototype: `void __fastcall(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180024160`
- `0x18002aac0`
- `0x1800431f0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBRGB24(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v11; // esi
  unsigned __int8 *i; // rdi
  unsigned __int8 Src[768]; // [rsp+40h] [rbp-348h] BYREF

  UpdateDstMBRGB24(a1, Src, a3, a4, a5, a6, a7, 48);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 3 * a8);
    i += 48;
    a2 += *((int *)a1 + 19);
  }
}

```

## disassembly

```asm
0x1800431f0  push    rbx
0x1800431f2  push    rbp
0x1800431f3  push    rsi
0x1800431f4  push    rdi
0x1800431f5  push    r14
0x1800431f7  push    r15
0x1800431f9  sub     rsp, 358h
0x180043200  mov     rax, cs:__security_cookie
0x180043207  xor     rax, rsp
0x18004320a  mov     [rsp+388h+var_48], rax
0x180043212  mov     eax, [rsp+388h+arg_30]
0x180043219  mov     r15, rcx
0x18004321c  mov     rcx, [rsp+388h+arg_20]
0x180043224  mov     rbx, rdx
0x180043227  mov     r14d, [rsp+388h+arg_38]
0x18004322f  lea     rdx, [rsp+388h+Src]; unsigned __int8 *
0x180043234  mov     [rsp+388h+var_350], 30h ; '0'; int
0x18004323c  mov     [rsp+388h+var_358], eax; int
0x180043240  mov     eax, [rsp+388h+arg_28]
0x180043247  mov     [rsp+388h+var_360], eax; int
0x18004324b  mov     [rsp+388h+var_368], rcx; unsigned __int8 *
0x180043250  mov     rcx, r15; struct CDeColorConvParams *
0x180043253  call    ?UpdateDstMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180043258  xor     esi, esi
0x18004325a  lea     rdi, [rsp+388h+Src]
0x18004325f  cmp     [rsp+388h+arg_40], esi
0x180043266  jle     short loc_180043293
0x180043268  lea     eax, [r14+r14*2]
0x18004326c  movsxd  rbp, eax
0x18004326f  mov     r8, rbp; Size
0x180043272  mov     rdx, rdi; Src
0x180043275  mov     rcx, rbx; void *
0x180043278  call    memcpy_0
0x18004327d  movsxd  rax, dword ptr [r15+4Ch]
0x180043281  add     rdi, 30h ; '0'
0x180043285  add     rbx, rax
0x180043288  inc     esi
0x18004328a  cmp     esi, [rsp+388h+arg_40]
0x180043291  jl      short loc_18004326F
0x180043293  mov     rcx, [rsp+388h+var_48]
0x18004329b  xor     rcx, rsp; StackCookie
0x18004329e  call    __security_check_cookie
0x1800432a3  add     rsp, 358h
0x1800432aa  pop     r15
0x1800432ac  pop     r14
0x1800432ae  pop     rdi
0x1800432af  pop     rsi
0x1800432b0  pop     rbp
0x1800432b1  pop     rbx
0x1800432b2  retn
```
