# UpdateDstPartialMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x1800438e0`
- end: `0x1800439ae`
- name: `?UpdateDstPartialMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x180042d90`
- `0x1800438e0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYVYU(
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

  UpdateDstMBYVYU(a1, Src, a3, a4, a5, a6, a7, 32);
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
0x1800438e0  mov     [rsp+arg_0], rbx
0x1800438e5  push    rbp
0x1800438e6  push    rsi
0x1800438e7  push    rdi
0x1800438e8  push    r14
0x1800438ea  push    r15
0x1800438ec  sub     rsp, 250h
0x1800438f3  mov     rax, cs:__security_cookie
0x1800438fa  xor     rax, rsp
0x1800438fd  mov     [rsp+278h+var_38], rax
0x180043905  mov     eax, [rsp+278h+arg_30]
0x18004390c  mov     rbx, rdx
0x18004390f  mov     r10, [rsp+278h+arg_20]
0x180043917  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x18004391c  mov     r14d, [rsp+278h+arg_38]
0x180043924  mov     r15, rcx
0x180043927  mov     [rsp+278h+var_240], 20h ; ' '; int
0x18004392f  and     r14d, 0FFFFFFFEh
0x180043933  mov     [rsp+278h+var_248], eax; int
0x180043937  mov     eax, [rsp+278h+arg_28]
0x18004393e  mov     [rsp+278h+var_250], eax; int
0x180043942  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x180043947  call    ?UpdateDstMBYVYU@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBYVYU(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004394c  xor     esi, esi
0x18004394e  lea     rdi, [rsp+278h+Src]
0x180043953  cmp     [rsp+278h+arg_40], esi
0x18004395a  jle     short loc_180043987
0x18004395c  lea     eax, [r14+r14]
0x180043960  movsxd  rbp, eax
0x180043963  mov     r8, rbp; Size
0x180043966  mov     rdx, rdi; Src
0x180043969  mov     rcx, rbx; void *
0x18004396c  call    memcpy_0
0x180043971  movsxd  rax, dword ptr [r15+4Ch]
0x180043975  add     rdi, 20h ; ' '
0x180043979  add     rbx, rax
0x18004397c  inc     esi
0x18004397e  cmp     esi, [rsp+278h+arg_40]
0x180043985  jl      short loc_180043963
0x180043987  mov     rcx, [rsp+278h+var_38]
0x18004398f  xor     rcx, rsp; StackCookie
0x180043992  call    __security_check_cookie
0x180043997  mov     rbx, [rsp+278h+arg_0]
0x18004399f  add     rsp, 250h
0x1800439a6  pop     r15
0x1800439a8  pop     r14
0x1800439aa  pop     rdi
0x1800439ab  pop     rsi
0x1800439ac  pop     rbp
0x1800439ad  retn
```
