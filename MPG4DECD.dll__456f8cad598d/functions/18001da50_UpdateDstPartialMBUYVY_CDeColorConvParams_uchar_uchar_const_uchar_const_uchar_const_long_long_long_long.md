# UpdateDstPartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001da50`
- end: `0x18001db26`
- name: `?UpdateDstPartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001cef0`
- `0x18001da50`
- `0x180021005`

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
0x18001da50  mov     [rsp+arg_0], rbx
0x18001da55  push    rbp
0x18001da56  push    rsi
0x18001da57  push    rdi
0x18001da58  push    r12
0x18001da5a  push    r14
0x18001da5c  sub     rsp, 250h
0x18001da63  mov     rax, cs:__security_cookie
0x18001da6a  xor     rax, rsp
0x18001da6d  mov     [rsp+278h+var_38], rax
0x18001da75  mov     eax, [rsp+278h+arg_30]
0x18001da7c  mov     r11, r9
0x18001da7f  mov     r14d, [rsp+278h+arg_38]
0x18001da87  mov     r10, r8
0x18001da8a  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001da92  mov     rbx, rdx
0x18001da95  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001da9d  mov     r12, rcx
0x18001daa0  mov     [rsp+278h+var_250], eax; int
0x18001daa4  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001daa9  mov     eax, [rsp+278h+arg_28]
0x18001dab0  mov     r8, r11; unsigned __int8 *
0x18001dab3  mov     rdx, r10; unsigned __int8 *
0x18001dab6  mov     [rsp+278h+var_258], eax; int
0x18001daba  and     r14d, 0FFFFFFFEh
0x18001dabe  call    ?UpdateDstMBUYVY@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBUYVY(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001dac3  xor     esi, esi
0x18001dac5  lea     rdi, [rsp+278h+Src]
0x18001daca  cmp     [rsp+278h+arg_40], esi
0x18001dad1  jle     short loc_18001DAFF
0x18001dad3  lea     eax, [r14+r14]
0x18001dad7  movsxd  rbp, eax
0x18001dada  mov     r8, rbp; Size
0x18001dadd  mov     rdx, rdi; Src
0x18001dae0  mov     rcx, rbx; void *
0x18001dae3  call    memcpy_0
0x18001dae8  movsxd  rax, dword ptr [r12+40h]
0x18001daed  add     rdi, 20h ; ' '
0x18001daf1  add     rbx, rax
0x18001daf4  inc     esi
0x18001daf6  cmp     esi, [rsp+278h+arg_40]
0x18001dafd  jl      short loc_18001DADA
0x18001daff  mov     rcx, [rsp+278h+var_38]
0x18001db07  xor     rcx, rsp; StackCookie
0x18001db0a  call    __security_check_cookie
0x18001db0f  mov     rbx, [rsp+278h+arg_0]
0x18001db17  add     rsp, 250h
0x18001db1e  pop     r14
0x18001db20  pop     r12
0x18001db22  pop     rdi
0x18001db23  pop     rsi
0x18001db24  pop     rbp
0x18001db25  retn
```
