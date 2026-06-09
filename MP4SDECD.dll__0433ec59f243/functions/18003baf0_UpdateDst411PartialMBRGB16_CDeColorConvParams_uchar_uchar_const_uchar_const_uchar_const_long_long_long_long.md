# UpdateDst411PartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003baf0`
- end: `0x18003bbb3`
- name: `?UpdateDst411PartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `195`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003a350`
- `0x18003baf0`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBRGB16(
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
  unsigned __int8 Src[512]; // [rsp+40h] [rbp-248h] BYREF

  UpdateDst411MBRGB16(a1, Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 2 * a8);
    i += 32;
    a2 += *((int *)a1 + 19);
  }
}

```

## disassembly

```asm
0x18003baf0  push    rbx
0x18003baf2  push    rbp
0x18003baf3  push    rsi
0x18003baf4  push    rdi
0x18003baf5  push    r12
0x18003baf7  push    r14
0x18003baf9  sub     rsp, 258h
0x18003bb00  mov     rax, cs:__security_cookie
0x18003bb07  xor     rax, rsp
0x18003bb0a  mov     [rsp+288h+var_48], rax
0x18003bb12  mov     eax, [rsp+288h+arg_30]
0x18003bb19  mov     r14, rcx
0x18003bb1c  mov     rcx, [rsp+288h+arg_20]
0x18003bb24  mov     rbx, rdx
0x18003bb27  mov     r12d, [rsp+288h+arg_38]
0x18003bb2f  lea     rdx, [rsp+288h+Src]; unsigned __int8 *
0x18003bb34  mov     [rsp+288h+var_250], 20h ; ' '; int
0x18003bb3c  mov     [rsp+288h+var_258], eax; int
0x18003bb40  mov     eax, [rsp+288h+arg_28]
0x18003bb47  mov     [rsp+288h+var_260], eax; int
0x18003bb4b  mov     [rsp+288h+var_268], rcx; unsigned __int8 *
0x18003bb50  mov     rcx, r14; struct CDeColorConvParams *
0x18003bb53  call    ?UpdateDst411MBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003bb58  xor     esi, esi
0x18003bb5a  lea     rdi, [rsp+288h+Src]
0x18003bb5f  cmp     [rsp+288h+arg_40], esi
0x18003bb66  jle     short loc_18003BB93
0x18003bb68  lea     eax, [r12+r12]
0x18003bb6c  movsxd  rbp, eax
0x18003bb6f  mov     r8, rbp; Size
0x18003bb72  mov     rdx, rdi; Src
0x18003bb75  mov     rcx, rbx; void *
0x18003bb78  call    memcpy_0
0x18003bb7d  movsxd  rax, dword ptr [r14+4Ch]
0x18003bb81  add     rdi, 20h ; ' '
0x18003bb85  add     rbx, rax
0x18003bb88  inc     esi
0x18003bb8a  cmp     esi, [rsp+288h+arg_40]
0x18003bb91  jl      short loc_18003BB6F
0x18003bb93  mov     rcx, [rsp+288h+var_48]
0x18003bb9b  xor     rcx, rsp; StackCookie
0x18003bb9e  call    __security_check_cookie
0x18003bba3  add     rsp, 258h
0x18003bbaa  pop     r14
0x18003bbac  pop     r12
0x18003bbae  pop     rdi
0x18003bbaf  pop     rsi
0x18003bbb0  pop     rbp
0x18003bbb1  pop     rbx
0x18003bbb2  retn
```
