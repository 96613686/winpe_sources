# UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d8b0`
- end: `0x18001d975`
- name: `?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `197`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001afe0`
- `0x18001d8b0`
- `0x180021005`

## pseudocode

```c
void __fastcall UpdateDstPartialMBRGB32(
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

  UpdateDstMBRGB32(Src, a3, a4, a5, a6, a7, 64);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 4 * a8);
    i += 64;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001d8b0  push    rbx
0x18001d8b2  push    rbp
0x18001d8b3  push    rsi
0x18001d8b4  push    rdi
0x18001d8b5  push    r15
0x18001d8b7  sub     rsp, 450h
0x18001d8be  mov     rax, cs:__security_cookie
0x18001d8c5  xor     rax, rsp
0x18001d8c8  mov     [rsp+478h+var_38], rax
0x18001d8d0  mov     eax, [rsp+478h+arg_30]
0x18001d8d7  mov     r11, r9
0x18001d8da  mov     r9, [rsp+478h+arg_20]; unsigned __int8 *
0x18001d8e2  mov     r10, r8
0x18001d8e5  mov     ebp, [rsp+478h+arg_38]
0x18001d8ec  mov     rbx, rdx
0x18001d8ef  mov     [rsp+478h+var_448], 40h ; '@'; int
0x18001d8f7  mov     r15, rcx
0x18001d8fa  mov     [rsp+478h+var_450], eax; int
0x18001d8fe  lea     rcx, [rsp+478h+Src]; unsigned __int8 *
0x18001d903  mov     eax, [rsp+478h+arg_28]
0x18001d90a  mov     r8, r11; unsigned __int8 *
0x18001d90d  mov     rdx, r10; unsigned __int8 *
0x18001d910  mov     [rsp+478h+var_458], eax; int
0x18001d914  call    ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d919  xor     esi, esi
0x18001d91b  lea     rdi, [rsp+478h+Src]
0x18001d920  cmp     [rsp+478h+arg_40], esi
0x18001d927  jle     short loc_18001D957
0x18001d929  lea     eax, ds:0[rbp*4]
0x18001d930  movsxd  rbp, eax
0x18001d933  mov     r8, rbp; Size
0x18001d936  mov     rdx, rdi; Src
0x18001d939  mov     rcx, rbx; void *
0x18001d93c  call    memcpy_0
0x18001d941  movsxd  rax, dword ptr [r15+40h]
0x18001d945  add     rdi, 40h ; '@'
0x18001d949  add     rbx, rax
0x18001d94c  inc     esi
0x18001d94e  cmp     esi, [rsp+478h+arg_40]
0x18001d955  jl      short loc_18001D933
0x18001d957  mov     rcx, [rsp+478h+var_38]
0x18001d95f  xor     rcx, rsp; StackCookie
0x18001d962  call    __security_check_cookie
0x18001d967  add     rsp, 450h
0x18001d96e  pop     r15
0x18001d970  pop     rdi
0x18001d971  pop     rsi
0x18001d972  pop     rbp
0x18001d973  pop     rbx
0x18001d974  retn
```
