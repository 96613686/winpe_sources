# UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x1800435a0`
- end: `0x18004366e`
- name: `?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x180042a20`
- `0x1800435a0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYUY2(
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

  UpdateDstMBYUY2(a1, Src, a3, a4, a5, a6, a7, 32);
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
0x1800435a0  mov     [rsp+arg_0], rbx
0x1800435a5  push    rbp
0x1800435a6  push    rsi
0x1800435a7  push    rdi
0x1800435a8  push    r14
0x1800435aa  push    r15
0x1800435ac  sub     rsp, 250h
0x1800435b3  mov     rax, cs:__security_cookie
0x1800435ba  xor     rax, rsp
0x1800435bd  mov     [rsp+278h+var_38], rax
0x1800435c5  mov     eax, [rsp+278h+arg_30]
0x1800435cc  mov     rbx, rdx
0x1800435cf  mov     r10, [rsp+278h+arg_20]
0x1800435d7  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x1800435dc  mov     r14d, [rsp+278h+arg_38]
0x1800435e4  mov     r15, rcx
0x1800435e7  mov     [rsp+278h+var_240], 20h ; ' '; int
0x1800435ef  and     r14d, 0FFFFFFFEh
0x1800435f3  mov     [rsp+278h+var_248], eax; int
0x1800435f7  mov     eax, [rsp+278h+arg_28]
0x1800435fe  mov     [rsp+278h+var_250], eax; int
0x180043602  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x180043607  call    ?UpdateDstMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18004360c  xor     esi, esi
0x18004360e  lea     rdi, [rsp+278h+Src]
0x180043613  cmp     [rsp+278h+arg_40], esi
0x18004361a  jle     short loc_180043647
0x18004361c  lea     eax, [r14+r14]
0x180043620  movsxd  rbp, eax
0x180043623  mov     r8, rbp; Size
0x180043626  mov     rdx, rdi; Src
0x180043629  mov     rcx, rbx; void *
0x18004362c  call    memcpy_0
0x180043631  movsxd  rax, dword ptr [r15+4Ch]
0x180043635  add     rdi, 20h ; ' '
0x180043639  add     rbx, rax
0x18004363c  inc     esi
0x18004363e  cmp     esi, [rsp+278h+arg_40]
0x180043645  jl      short loc_180043623
0x180043647  mov     rcx, [rsp+278h+var_38]
0x18004364f  xor     rcx, rsp; StackCookie
0x180043652  call    __security_check_cookie
0x180043657  mov     rbx, [rsp+278h+arg_0]
0x18004365f  add     rsp, 250h
0x180043666  pop     r15
0x180043668  pop     r14
0x18004366a  pop     rdi
0x18004366b  pop     rsi
0x18004366c  pop     rbp
0x18004366d  retn
```
