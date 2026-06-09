# UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d710`
- end: `0x18001d7e2`
- name: `?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `210`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001a1f0`
- `0x18001d710`
- `0x180020f45`

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
  unsigned __int8 Src[768]; // [rsp+40h] [rbp-338h] BYREF

  UpdateDstMBRGB24(Src, a3, a4, a5, a6, a7, 48);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 3 * a8);
    i += 48;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001d710  mov     [rsp+arg_0], rbx
0x18001d715  push    rbp
0x18001d716  push    rsi
0x18001d717  push    rdi
0x18001d718  push    r12
0x18001d71a  push    r14
0x18001d71c  sub     rsp, 350h
0x18001d723  mov     rax, cs:__security_cookie
0x18001d72a  xor     rax, rsp
0x18001d72d  mov     [rsp+378h+var_38], rax
0x18001d735  mov     eax, [rsp+378h+arg_30]
0x18001d73c  mov     r11, r9
0x18001d73f  mov     r9, [rsp+378h+arg_20]; unsigned __int8 *
0x18001d747  mov     r10, r8
0x18001d74a  mov     r14d, [rsp+378h+arg_38]
0x18001d752  mov     rbx, rdx
0x18001d755  mov     [rsp+378h+var_348], 30h ; '0'; int
0x18001d75d  mov     r12, rcx
0x18001d760  mov     [rsp+378h+var_350], eax; int
0x18001d764  lea     rcx, [rsp+378h+Src]; unsigned __int8 *
0x18001d769  mov     eax, [rsp+378h+arg_28]
0x18001d770  mov     r8, r11; unsigned __int8 *
0x18001d773  mov     rdx, r10; unsigned __int8 *
0x18001d776  mov     [rsp+378h+var_358], eax; int
0x18001d77a  call    ?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d77f  xor     esi, esi
0x18001d781  lea     rdi, [rsp+378h+Src]
0x18001d786  cmp     [rsp+378h+arg_40], esi
0x18001d78d  jle     short loc_18001D7BB
0x18001d78f  lea     eax, [r14+r14*2]
0x18001d793  movsxd  rbp, eax
0x18001d796  mov     r8, rbp; Size
0x18001d799  mov     rdx, rdi; Src
0x18001d79c  mov     rcx, rbx; void *
0x18001d79f  call    memcpy_0
0x18001d7a4  movsxd  rax, dword ptr [r12+40h]
0x18001d7a9  add     rdi, 30h ; '0'
0x18001d7ad  add     rbx, rax
0x18001d7b0  inc     esi
0x18001d7b2  cmp     esi, [rsp+378h+arg_40]
0x18001d7b9  jl      short loc_18001D796
0x18001d7bb  mov     rcx, [rsp+378h+var_38]
0x18001d7c3  xor     rcx, rsp; StackCookie
0x18001d7c6  call    __security_check_cookie
0x18001d7cb  mov     rbx, [rsp+378h+arg_0]
0x18001d7d3  add     rsp, 350h
0x18001d7da  pop     r14
0x18001d7dc  pop     r12
0x18001d7de  pop     rdi
0x18001d7df  pop     rsi
0x18001d7e0  pop     rbp
0x18001d7e1  retn
```
