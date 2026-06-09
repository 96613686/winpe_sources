# UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d630`
- end: `0x18001d702`
- name: `?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `210`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x180018650`
- `0x18001d630`
- `0x180020f45`

## pseudocode

```c
void __fastcall UpdateDstPartialMBRGB16(
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

  UpdateDstMBRGB16(Src, a3, a4, a5, a6, a7, 32);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, 2 * a8);
    i += 32;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001d630  mov     [rsp+arg_0], rbx
0x18001d635  push    rbp
0x18001d636  push    rsi
0x18001d637  push    rdi
0x18001d638  push    r12
0x18001d63a  push    r15
0x18001d63c  sub     rsp, 250h
0x18001d643  mov     rax, cs:__security_cookie
0x18001d64a  xor     rax, rsp
0x18001d64d  mov     [rsp+278h+var_38], rax
0x18001d655  mov     eax, [rsp+278h+arg_30]
0x18001d65c  mov     r11, r9
0x18001d65f  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001d667  mov     r10, r8
0x18001d66a  mov     r15d, [rsp+278h+arg_38]
0x18001d672  mov     rbx, rdx
0x18001d675  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001d67d  mov     r12, rcx
0x18001d680  mov     [rsp+278h+var_250], eax; int
0x18001d684  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001d689  mov     eax, [rsp+278h+arg_28]
0x18001d690  mov     r8, r11; unsigned __int8 *
0x18001d693  mov     rdx, r10; unsigned __int8 *
0x18001d696  mov     [rsp+278h+var_258], eax; int
0x18001d69a  call    ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d69f  xor     esi, esi
0x18001d6a1  lea     rdi, [rsp+278h+Src]
0x18001d6a6  cmp     [rsp+278h+arg_40], esi
0x18001d6ad  jle     short loc_18001D6DB
0x18001d6af  lea     eax, [r15+r15]
0x18001d6b3  movsxd  rbp, eax
0x18001d6b6  mov     r8, rbp; Size
0x18001d6b9  mov     rdx, rdi; Src
0x18001d6bc  mov     rcx, rbx; void *
0x18001d6bf  call    memcpy_0
0x18001d6c4  movsxd  rax, dword ptr [r12+40h]
0x18001d6c9  add     rdi, 20h ; ' '
0x18001d6cd  add     rbx, rax
0x18001d6d0  inc     esi
0x18001d6d2  cmp     esi, [rsp+278h+arg_40]
0x18001d6d9  jl      short loc_18001D6B6
0x18001d6db  mov     rcx, [rsp+278h+var_38]
0x18001d6e3  xor     rcx, rsp; StackCookie
0x18001d6e6  call    __security_check_cookie
0x18001d6eb  mov     rbx, [rsp+278h+arg_0]
0x18001d6f3  add     rsp, 250h
0x18001d6fa  pop     r15
0x18001d6fc  pop     r12
0x18001d6fe  pop     rdi
0x18001d6ff  pop     rsi
0x18001d700  pop     rbp
0x18001d701  retn
```
