# UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d990`
- end: `0x18001da66`
- name: `?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001ce30`
- `0x18001d990`
- `0x180020f45`

## pseudocode

```c
void __fastcall UpdateDstPartialMBUYVY(
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

  UpdateDstMBUYVY(Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, (int)(2 * (a8 & 0xFFFFFFFE)));
    i += 32;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001d990  mov     [rsp+arg_0], rbx
0x18001d995  push    rbp
0x18001d996  push    rsi
0x18001d997  push    rdi
0x18001d998  push    r12
0x18001d99a  push    r14
0x18001d99c  sub     rsp, 250h
0x18001d9a3  mov     rax, cs:__security_cookie
0x18001d9aa  xor     rax, rsp
0x18001d9ad  mov     [rsp+278h+var_38], rax
0x18001d9b5  mov     eax, [rsp+278h+arg_30]
0x18001d9bc  mov     r11, r9
0x18001d9bf  mov     r14d, [rsp+278h+arg_38]
0x18001d9c7  mov     r10, r8
0x18001d9ca  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001d9d2  mov     rbx, rdx
0x18001d9d5  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001d9dd  mov     r12, rcx
0x18001d9e0  mov     [rsp+278h+var_250], eax; int
0x18001d9e4  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001d9e9  mov     eax, [rsp+278h+arg_28]
0x18001d9f0  mov     r8, r11; unsigned __int8 *
0x18001d9f3  mov     rdx, r10; unsigned __int8 *
0x18001d9f6  mov     [rsp+278h+var_258], eax; int
0x18001d9fa  and     r14d, 0FFFFFFFEh
0x18001d9fe  call    ?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001da03  xor     esi, esi
0x18001da05  lea     rdi, [rsp+278h+Src]
0x18001da0a  cmp     [rsp+278h+arg_40], esi
0x18001da11  jle     short loc_18001DA3F
0x18001da13  lea     eax, [r14+r14]
0x18001da17  movsxd  rbp, eax
0x18001da1a  mov     r8, rbp; Size
0x18001da1d  mov     rdx, rdi; Src
0x18001da20  mov     rcx, rbx; void *
0x18001da23  call    memcpy_0
0x18001da28  movsxd  rax, dword ptr [r12+40h]
0x18001da2d  add     rdi, 20h ; ' '
0x18001da31  add     rbx, rax
0x18001da34  inc     esi
0x18001da36  cmp     esi, [rsp+278h+arg_40]
0x18001da3d  jl      short loc_18001DA1A
0x18001da3f  mov     rcx, [rsp+278h+var_38]
0x18001da47  xor     rcx, rsp; StackCookie
0x18001da4a  call    __security_check_cookie
0x18001da4f  mov     rbx, [rsp+278h+arg_0]
0x18001da57  add     rsp, 250h
0x18001da5e  pop     r14
0x18001da60  pop     r12
0x18001da62  pop     rdi
0x18001da63  pop     rsi
0x18001da64  pop     rbp
0x18001da65  retn
```
