# UpdateDst411PartialMBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003be40`
- end: `0x18003bf0e`
- name: `?UpdateDst411PartialMBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `206`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003b9b0`
- `0x18003be40`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBYUY2(
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

  UpdateDst411MBYUY2(a1, Src, a3, a4, a5, a6, a7, 32);
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
0x18003be40  mov     [rsp+arg_0], rbx
0x18003be45  push    rbp
0x18003be46  push    rsi
0x18003be47  push    rdi
0x18003be48  push    r14
0x18003be4a  push    r15
0x18003be4c  sub     rsp, 250h
0x18003be53  mov     rax, cs:__security_cookie
0x18003be5a  xor     rax, rsp
0x18003be5d  mov     [rsp+278h+var_38], rax
0x18003be65  mov     eax, [rsp+278h+arg_30]
0x18003be6c  mov     rbx, rdx
0x18003be6f  mov     r10, [rsp+278h+arg_20]
0x18003be77  lea     rdx, [rsp+278h+Src]; unsigned __int8 *
0x18003be7c  mov     r14d, [rsp+278h+arg_38]
0x18003be84  mov     r15, rcx
0x18003be87  mov     [rsp+278h+var_240], 20h ; ' '; int
0x18003be8f  and     r14d, 0FFFFFFFEh
0x18003be93  mov     [rsp+278h+var_248], eax; int
0x18003be97  mov     eax, [rsp+278h+arg_28]
0x18003be9e  mov     [rsp+278h+var_250], eax; int
0x18003bea2  mov     [rsp+278h+var_258], r10; unsigned __int8 *
0x18003bea7  call    ?UpdateDst411MBYUY2@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBYUY2(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003beac  xor     esi, esi
0x18003beae  lea     rdi, [rsp+278h+Src]
0x18003beb3  cmp     [rsp+278h+arg_40], esi
0x18003beba  jle     short loc_18003BEE7
0x18003bebc  lea     eax, [r14+r14]
0x18003bec0  movsxd  rbp, eax
0x18003bec3  mov     r8, rbp; Size
0x18003bec6  mov     rdx, rdi; Src
0x18003bec9  mov     rcx, rbx; void *
0x18003becc  call    memcpy_0
0x18003bed1  movsxd  rax, dword ptr [r15+4Ch]
0x18003bed5  add     rdi, 20h ; ' '
0x18003bed9  add     rbx, rax
0x18003bedc  inc     esi
0x18003bede  cmp     esi, [rsp+278h+arg_40]
0x18003bee5  jl      short loc_18003BEC3
0x18003bee7  mov     rcx, [rsp+278h+var_38]
0x18003beef  xor     rcx, rsp; StackCookie
0x18003bef2  call    __security_check_cookie
0x18003bef7  mov     rbx, [rsp+278h+arg_0]
0x18003beff  add     rsp, 250h
0x18003bf06  pop     r15
0x18003bf08  pop     r14
0x18003bf0a  pop     rdi
0x18003bf0b  pop     rsi
0x18003bf0c  pop     rbp
0x18003bf0d  retn
```
