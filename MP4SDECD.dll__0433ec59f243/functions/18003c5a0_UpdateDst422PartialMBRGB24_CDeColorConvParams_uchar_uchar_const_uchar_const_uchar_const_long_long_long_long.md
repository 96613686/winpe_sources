# UpdateDst422PartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003c5a0`
- end: `0x18003c663`
- name: `?UpdateDst422PartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `195`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003c000`
- `0x18003c5a0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst422PartialMBRGB24(
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

  UpdateDst422MBRGB24(a1, Src, a3, a4, a5, a6, a7, 48);
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
0x18003c5a0  push    rbx
0x18003c5a2  push    rbp
0x18003c5a3  push    rsi
0x18003c5a4  push    rdi
0x18003c5a5  push    r14
0x18003c5a7  push    r15
0x18003c5a9  sub     rsp, 358h
0x18003c5b0  mov     rax, cs:__security_cookie
0x18003c5b7  xor     rax, rsp
0x18003c5ba  mov     [rsp+388h+var_48], rax
0x18003c5c2  mov     eax, [rsp+388h+arg_30]
0x18003c5c9  mov     r15, rcx
0x18003c5cc  mov     rcx, [rsp+388h+arg_20]
0x18003c5d4  mov     rbx, rdx
0x18003c5d7  mov     r14d, [rsp+388h+arg_38]
0x18003c5df  lea     rdx, [rsp+388h+Src]; unsigned __int8 *
0x18003c5e4  mov     [rsp+388h+var_350], 30h ; '0'; int
0x18003c5ec  mov     [rsp+388h+var_358], eax; int
0x18003c5f0  mov     eax, [rsp+388h+arg_28]
0x18003c5f7  mov     [rsp+388h+var_360], eax; int
0x18003c5fb  mov     [rsp+388h+var_368], rcx; unsigned __int8 *
0x18003c600  mov     rcx, r15; struct CDeColorConvParams *
0x18003c603  call    ?UpdateDst422MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst422MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003c608  xor     esi, esi
0x18003c60a  lea     rdi, [rsp+388h+Src]
0x18003c60f  cmp     [rsp+388h+arg_40], esi
0x18003c616  jle     short loc_18003C643
0x18003c618  lea     eax, [r14+r14*2]
0x18003c61c  movsxd  rbp, eax
0x18003c61f  mov     r8, rbp; Size
0x18003c622  mov     rdx, rdi; Src
0x18003c625  mov     rcx, rbx; void *
0x18003c628  call    memcpy_0
0x18003c62d  movsxd  rax, dword ptr [r15+4Ch]
0x18003c631  add     rdi, 30h ; '0'
0x18003c635  add     rbx, rax
0x18003c638  inc     esi
0x18003c63a  cmp     esi, [rsp+388h+arg_40]
0x18003c641  jl      short loc_18003C61F
0x18003c643  mov     rcx, [rsp+388h+var_48]
0x18003c64b  xor     rcx, rsp; StackCookie
0x18003c64e  call    __security_check_cookie
0x18003c653  add     rsp, 358h
0x18003c65a  pop     r15
0x18003c65c  pop     r14
0x18003c65e  pop     rdi
0x18003c65f  pop     rsi
0x18003c660  pop     rbp
0x18003c661  pop     rbx
0x18003c662  retn
```
