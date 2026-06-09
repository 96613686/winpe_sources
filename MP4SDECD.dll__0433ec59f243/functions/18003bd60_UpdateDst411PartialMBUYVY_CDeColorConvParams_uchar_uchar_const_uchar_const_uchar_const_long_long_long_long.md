# UpdateDst411PartialMBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003bd60`
- end: `0x18003be2e`
- name: `?UpdateDst411PartialMBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003b910`
- `0x18003bd60`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBUYVY(
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

  UpdateDst411MBUYVY(a1, Src, a3, a4, a5, a6, a7, 32);
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
0x18003bd60  mov     [rsp+arg_0], rbx
0x18003bd65  push    rbp
0x18003bd66  push    rsi
0x18003bd67  push    rdi
0x18003bd68  push    r14
0x18003bd6a  push    r15
0x18003bd6c  sub     rsp, 250h
0x18003bd73  mov     rax, cs:__security_cookie
0x18003bd7a  xor     rax, rsp
0x18003bd7d  mov     [rsp+278h+var_38], rax
0x18003bd85  mov     eax, [rsp+278h+arg_30]
0x18003bd8c  mov     rbx, rdx
0x18003bd8f  mov     r10, [rsp+278h+arg_20]
0x18003bd97  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x18003bd9c  mov     r14d, [rsp+278h+arg_38]
0x18003bda4  mov     r15, rcx
0x18003bda7  mov     [rsp+278h+var_240], 20h ; ' '; int
0x18003bdaf  and     r14d, 0FFFFFFFEh
0x18003bdb3  mov     [rsp+278h+var_248], eax; int
0x18003bdb7  mov     eax, [rsp+278h+arg_28]
0x18003bdbe  mov     [rsp+278h+var_250], eax; int
0x18003bdc2  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x18003bdc7  call    ?UpdateDst411MBUYVY@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBUYVY(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003bdcc  xor     esi, esi
0x18003bdce  lea     rdi, [rsp+278h+Src]
0x18003bdd3  cmp     [rsp+278h+arg_40], esi
0x18003bdda  jle     short loc_18003BE07
0x18003bddc  lea     eax, [r14+r14]
0x18003bde0  movsxd  rbp, eax
0x18003bde3  mov     r8, rbp; Size
0x18003bde6  mov     rdx, rdi; Src
0x18003bde9  mov     rcx, rbx; void *
0x18003bdec  call    memcpy_0
0x18003bdf1  movsxd  rax, dword ptr [r15+4Ch]
0x18003bdf5  add     rdi, 20h ; ' '
0x18003bdf9  add     rbx, rax
0x18003bdfc  inc     esi
0x18003bdfe  cmp     esi, [rsp+278h+arg_40]
0x18003be05  jl      short loc_18003BDE3
0x18003be07  mov     rcx, [rsp+278h+var_38]
0x18003be0f  xor     rcx, rsp; StackCookie
0x18003be12  call    __security_check_cookie
0x18003be17  mov     rbx, [rsp+278h+arg_0]
0x18003be1f  add     rsp, 250h
0x18003be26  pop     r15
0x18003be28  pop     r14
0x18003be2a  pop     rdi
0x18003be2b  pop     rsi
0x18003be2c  pop     rbp
0x18003be2d  retn
```
