# UpdateDstPartialMBRGB24(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d7d0`
- end: `0x18001d8a2`
- name: `?UpdateDstPartialMBRGB24@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `210`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001a2b0`
- `0x18001d7d0`
- `0x180021005`

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
0x18001d7d0  mov     [rsp+arg_0], rbx
0x18001d7d5  push    rbp
0x18001d7d6  push    rsi
0x18001d7d7  push    rdi
0x18001d7d8  push    r12
0x18001d7da  push    r14
0x18001d7dc  sub     rsp, 350h
0x18001d7e3  mov     rax, cs:__security_cookie
0x18001d7ea  xor     rax, rsp
0x18001d7ed  mov     [rsp+378h+var_38], rax
0x18001d7f5  mov     eax, [rsp+378h+arg_30]
0x18001d7fc  mov     r11, r9
0x18001d7ff  mov     r9, [rsp+378h+arg_20]; unsigned __int8 *
0x18001d807  mov     r10, r8
0x18001d80a  mov     r14d, [rsp+378h+arg_38]
0x18001d812  mov     rbx, rdx
0x18001d815  mov     [rsp+378h+var_348], 30h ; '0'; int
0x18001d81d  mov     r12, rcx
0x18001d820  mov     [rsp+378h+var_350], eax; int
0x18001d824  lea     rcx, [rsp+378h+Src]; unsigned __int8 *
0x18001d829  mov     eax, [rsp+378h+arg_28]
0x18001d830  mov     r8, r11; unsigned __int8 *
0x18001d833  mov     rdx, r10; unsigned __int8 *
0x18001d836  mov     [rsp+378h+var_358], eax; int
0x18001d83a  call    ?UpdateDstMBRGB24@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB24(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d83f  xor     esi, esi
0x18001d841  lea     rdi, [rsp+378h+Src]
0x18001d846  cmp     [rsp+378h+arg_40], esi
0x18001d84d  jle     short loc_18001D87B
0x18001d84f  lea     eax, [r14+r14*2]
0x18001d853  movsxd  rbp, eax
0x18001d856  mov     r8, rbp; Size
0x18001d859  mov     rdx, rdi; Src
0x18001d85c  mov     rcx, rbx; void *
0x18001d85f  call    memcpy_0
0x18001d864  movsxd  rax, dword ptr [r12+40h]
0x18001d869  add     rdi, 30h ; '0'
0x18001d86d  add     rbx, rax
0x18001d870  inc     esi
0x18001d872  cmp     esi, [rsp+378h+arg_40]
0x18001d879  jl      short loc_18001D856
0x18001d87b  mov     rcx, [rsp+378h+var_38]
0x18001d883  xor     rcx, rsp; StackCookie
0x18001d886  call    __security_check_cookie
0x18001d88b  mov     rbx, [rsp+378h+arg_0]
0x18001d893  add     rsp, 350h
0x18001d89a  pop     r14
0x18001d89c  pop     r12
0x18001d89e  pop     rdi
0x18001d89f  pop     rsi
0x18001d8a0  pop     rbp
0x18001d8a1  retn
```
