# UpdateDst411PartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003bbc0`
- end: `0x18003bc8a`
- name: `?UpdateDst411PartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `202`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003aee0`
- `0x18003bbc0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBRGB24(
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
  unsigned __int8 Src[768]; // [rsp+40h] [rbp-338h] BYREF

  UpdateDst411MBRGB24(a1, Src, a3, a4, a5, a6, a7, 48);
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
0x18003bbc0  mov     [rsp+arg_0], rbx
0x18003bbc5  push    rbp
0x18003bbc6  push    rsi
0x18003bbc7  push    rdi
0x18003bbc8  push    r14
0x18003bbca  push    r15
0x18003bbcc  sub     rsp, 350h
0x18003bbd3  mov     rax, cs:__security_cookie
0x18003bbda  xor     rax, rsp
0x18003bbdd  mov     [rsp+378h+var_38], rax
0x18003bbe5  mov     eax, [rsp+378h+arg_30]
0x18003bbec  mov     rbx, rdx
0x18003bbef  mov     r10, [rsp+378h+arg_20]
0x18003bbf7  lea     rdx, [rsp+378h+Src]; unsigned __int8 *
0x18003bbfc  mov     r14d, [rsp+378h+arg_38]
0x18003bc04  mov     r15, rcx
0x18003bc07  mov     [rsp+378h+var_340], 30h ; '0'; int
0x18003bc0f  mov     [rsp+378h+var_348], eax; int
0x18003bc13  mov     eax, [rsp+378h+arg_28]
0x18003bc1a  mov     [rsp+378h+var_350], eax; int
0x18003bc1e  mov     [rsp+378h+var_358], r10; unsigned __int8 *
0x18003bc23  call    ?UpdateDst411MBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003bc28  xor     esi, esi
0x18003bc2a  lea     rdi, [rsp+378h+Src]
0x18003bc2f  cmp     [rsp+378h+arg_40], esi
0x18003bc36  jle     short loc_18003BC63
0x18003bc38  lea     eax, [r14+r14*2]
0x18003bc3c  movsxd  rbp, eax
0x18003bc3f  mov     r8, rbp; Size
0x18003bc42  mov     rdx, rdi; Src
0x18003bc45  mov     rcx, rbx; void *
0x18003bc48  call    memcpy_0
0x18003bc4d  movsxd  rax, dword ptr [r15+4Ch]
0x18003bc51  add     rdi, 30h ; '0'
0x18003bc55  add     rbx, rax
0x18003bc58  inc     esi
0x18003bc5a  cmp     esi, [rsp+378h+arg_40]
0x18003bc61  jl      short loc_18003BC3F
0x18003bc63  mov     rcx, [rsp+378h+var_38]
0x18003bc6b  xor     rcx, rsp; StackCookie
0x18003bc6e  call    __security_check_cookie
0x18003bc73  mov     rbx, [rsp+378h+arg_0]
0x18003bc7b  add     rsp, 350h
0x18003bc82  pop     r15
0x18003bc84  pop     r14
0x18003bc86  pop     rdi
0x18003bc87  pop     rsi
0x18003bc88  pop     rbp
0x18003bc89  retn
```
