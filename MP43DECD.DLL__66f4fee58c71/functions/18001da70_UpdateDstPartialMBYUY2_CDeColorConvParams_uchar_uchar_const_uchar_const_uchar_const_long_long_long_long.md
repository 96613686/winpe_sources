# UpdateDstPartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001da70`
- end: `0x18001db46`
- name: `?UpdateDstPartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `214`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001d080`
- `0x18001da70`
- `0x180020f45`

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

  UpdateDstMBYUY2(Src, a3, a4, a5, a6, a7, 32);
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
0x18001da70  mov     [rsp+arg_0], rbx
0x18001da75  push    rbp
0x18001da76  push    rsi
0x18001da77  push    rdi
0x18001da78  push    r12
0x18001da7a  push    r14
0x18001da7c  sub     rsp, 250h
0x18001da83  mov     rax, cs:__security_cookie
0x18001da8a  xor     rax, rsp
0x18001da8d  mov     [rsp+278h+var_38], rax
0x18001da95  mov     eax, [rsp+278h+arg_30]
0x18001da9c  mov     r11, r9
0x18001da9f  mov     r14d, [rsp+278h+arg_38]
0x18001daa7  mov     r10, r8
0x18001daaa  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001dab2  mov     rbx, rdx
0x18001dab5  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001dabd  mov     r12, rcx
0x18001dac0  mov     [rsp+278h+var_250], eax; int
0x18001dac4  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001dac9  mov     eax, [rsp+278h+arg_28]
0x18001dad0  mov     r8, r11; unsigned __int8 *
0x18001dad3  mov     rdx, r10; unsigned __int8 *
0x18001dad6  mov     [rsp+278h+var_258], eax; int
0x18001dada  and     r14d, 0FFFFFFFEh
0x18001dade  call    ?UpdateDstMBYUY2@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBYUY2(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001dae3  xor     esi, esi
0x18001dae5  lea     rdi, [rsp+278h+Src]
0x18001daea  cmp     [rsp+278h+arg_40], esi
0x18001daf1  jle     short loc_18001DB1F
0x18001daf3  lea     eax, [r14+r14]
0x18001daf7  movsxd  rbp, eax
0x18001dafa  mov     r8, rbp; Size
0x18001dafd  mov     rdx, rdi; Src
0x18001db00  mov     rcx, rbx; void *
0x18001db03  call    memcpy_0
0x18001db08  movsxd  rax, dword ptr [r12+40h]
0x18001db0d  add     rdi, 20h ; ' '
0x18001db11  add     rbx, rax
0x18001db14  inc     esi
0x18001db16  cmp     esi, [rsp+278h+arg_40]
0x18001db1d  jl      short loc_18001DAFA
0x18001db1f  mov     rcx, [rsp+278h+var_38]
0x18001db27  xor     rcx, rsp; StackCookie
0x18001db2a  call    __security_check_cookie
0x18001db2f  mov     rbx, [rsp+278h+arg_0]
0x18001db37  add     rsp, 250h
0x18001db3e  pop     r14
0x18001db40  pop     r12
0x18001db42  pop     rdi
0x18001db43  pop     rsi
0x18001db44  pop     rbp
0x18001db45  retn
```
