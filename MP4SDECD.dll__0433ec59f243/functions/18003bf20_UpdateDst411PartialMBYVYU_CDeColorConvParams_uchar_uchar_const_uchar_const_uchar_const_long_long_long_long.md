# UpdateDst411PartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003bf20`
- end: `0x18003bfee`
- name: `?UpdateDst411PartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003ba50`
- `0x18003bf20`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBYVYU(
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
  unsigned __int8 Src[512]; // [rsp+40h] [rbp-238h] BYREF

  UpdateDst411MBYVYU(a1, Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, (int)(2 * (a8 & 0xFFFFFFFE)));
    i += 32;
    a2 += *((int *)a1 + 19);
  }
}

```

## disassembly

```asm
0x18003bf20  mov     [rsp+arg_0], rbx
0x18003bf25  push    rbp
0x18003bf26  push    rsi
0x18003bf27  push    rdi
0x18003bf28  push    r14
0x18003bf2a  push    r15
0x18003bf2c  sub     rsp, 250h
0x18003bf33  mov     rax, cs:__security_cookie
0x18003bf3a  xor     rax, rsp
0x18003bf3d  mov     [rsp+278h+var_38], rax
0x18003bf45  mov     eax, [rsp+278h+arg_30]
0x18003bf4c  mov     rbx, rdx
0x18003bf4f  mov     r10, [rsp+278h+arg_20]
0x18003bf57  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x18003bf5c  mov     r14d, [rsp+278h+arg_38]
0x18003bf64  mov     r15, rcx
0x18003bf67  mov     [rsp+278h+var_240], 20h ; ' '; int
0x18003bf6f  and     r14d, 0FFFFFFFEh
0x18003bf73  mov     [rsp+278h+var_248], eax; int
0x18003bf77  mov     eax, [rsp+278h+arg_28]
0x18003bf7e  mov     [rsp+278h+var_250], eax; int
0x18003bf82  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x18003bf87  call    ?UpdateDst411MBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003bf8c  xor     esi, esi
0x18003bf8e  lea     rdi, [rsp+278h+Src]
0x18003bf93  cmp     [rsp+278h+arg_40], esi
0x18003bf9a  jle     short loc_18003BFC7
0x18003bf9c  lea     eax, [r14+r14]
0x18003bfa0  movsxd  rbp, eax
0x18003bfa3  mov     r8, rbp; Size
0x18003bfa6  mov     rdx, rdi; Src
0x18003bfa9  mov     rcx, rbx; void *
0x18003bfac  call    memcpy_0
0x18003bfb1  movsxd  rax, dword ptr [r15+4Ch]
0x18003bfb5  add     rdi, 20h ; ' '
0x18003bfb9  add     rbx, rax
0x18003bfbc  inc     esi
0x18003bfbe  cmp     esi, [rsp+278h+arg_40]
0x18003bfc5  jl      short loc_18003BFA3
0x18003bfc7  mov     rcx, [rsp+278h+var_38]
0x18003bfcf  xor     rcx, rsp; StackCookie
0x18003bfd2  call    __security_check_cookie
0x18003bfd7  mov     rbx, [rsp+278h+arg_0]
0x18003bfdf  add     rsp, 250h
0x18003bfe6  pop     r15
0x18003bfe8  pop     r14
0x18003bfea  pop     rdi
0x18003bfeb  pop     rsi
0x18003bfec  pop     rbp
0x18003bfed  retn
```
