# UpdateDst411PartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18003bc90`
- end: `0x18003bd51`
- name: `?UpdateDst411PartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `193`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003b3d0`
- `0x18003bc90`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDst411PartialMBRGB32(
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
  unsigned __int8 Src[1024]; // [rsp+40h] [rbp-438h] BYREF

  UpdateDst411MBRGB32(a1, Src, a3, a4, a5, a6, a7, 64);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 4 * a8);
    i += 64;
    a2 += *((int *)a1 + 19);
  }
}

```

## disassembly

```asm
0x18003bc90  push    rbx
0x18003bc92  push    rbp
0x18003bc93  push    rsi
0x18003bc94  push    rdi
0x18003bc95  push    r14
0x18003bc97  sub     rsp, 450h
0x18003bc9e  mov     rax, cs:__security_cookie
0x18003bca5  xor     rax, rsp
0x18003bca8  mov     [rsp+478h+var_38], rax
0x18003bcb0  mov     eax, [rsp+478h+arg_30]
0x18003bcb7  mov     r14, rcx
0x18003bcba  mov     rcx, [rsp+478h+arg_20]
0x18003bcc2  mov     rbx, rdx
0x18003bcc5  mov     ebp, [rsp+478h+arg_38]
0x18003bccc  lea     rdx, [rsp+478h+Src]; unsigned __int8 *
0x18003bcd1  mov     [rsp+478h+var_440], 40h ; '@'; int
0x18003bcd9  mov     [rsp+478h+var_448], eax; int
0x18003bcdd  mov     eax, [rsp+478h+arg_28]
0x18003bce4  mov     [rsp+478h+var_450], eax; int
0x18003bce8  mov     [rsp+478h+var_458], rcx; unsigned __int8 *
0x18003bced  mov     rcx, r14; struct CDeColorConvParams *
0x18003bcf0  call    ?UpdateDst411MBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDst411MBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18003bcf5  xor     esi, esi
0x18003bcf7  lea     rdi, [rsp+478h+Src]
0x18003bcfc  cmp     [rsp+478h+arg_40], esi
0x18003bd03  jle     short loc_18003BD33
0x18003bd05  lea     eax, ds:0[rbp*4]
0x18003bd0c  movsxd  rbp, eax
0x18003bd0f  mov     r8, rbp; Size
0x18003bd12  mov     rdx, rdi; Src
0x18003bd15  mov     rcx, rbx; void *
0x18003bd18  call    memcpy_0
0x18003bd1d  movsxd  rax, dword ptr [r14+4Ch]
0x18003bd21  add     rdi, 40h ; '@'
0x18003bd25  add     rbx, rax
0x18003bd28  inc     esi
0x18003bd2a  cmp     esi, [rsp+478h+arg_40]
0x18003bd31  jl      short loc_18003BD0F
0x18003bd33  mov     rcx, [rsp+478h+var_38]
0x18003bd3b  xor     rcx, rsp; StackCookie
0x18003bd3e  call    __security_check_cookie
0x18003bd43  add     rsp, 450h
0x18003bd4a  pop     r14
0x18003bd4c  pop     rdi
0x18003bd4d  pop     rsi
0x18003bd4e  pop     rbp
0x18003bd4f  pop     rbx
0x18003bd50  retn
```
