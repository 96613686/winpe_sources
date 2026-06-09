# UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d6f0`
- end: `0x18001d7c2`
- name: `?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `210`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x180018710`
- `0x18001d6f0`
- `0x180021005`

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
0x18001d6f0  mov     [rsp+arg_0], rbx
0x18001d6f5  push    rbp
0x18001d6f6  push    rsi
0x18001d6f7  push    rdi
0x18001d6f8  push    r12
0x18001d6fa  push    r15
0x18001d6fc  sub     rsp, 250h
0x18001d703  mov     rax, cs:__security_cookie
0x18001d70a  xor     rax, rsp
0x18001d70d  mov     [rsp+278h+var_38], rax
0x18001d715  mov     eax, [rsp+278h+arg_30]
0x18001d71c  mov     r11, r9
0x18001d71f  mov     r9, [rsp+278h+arg_20]; unsigned __int8 *
0x18001d727  mov     r10, r8
0x18001d72a  mov     r15d, [rsp+278h+arg_38]
0x18001d732  mov     rbx, rdx
0x18001d735  mov     [rsp+278h+var_248], 20h ; ' '; int
0x18001d73d  mov     r12, rcx
0x18001d740  mov     [rsp+278h+var_250], eax; int
0x18001d744  lea     rcx, [rsp+278h+Src]; unsigned __int8 *
0x18001d749  mov     eax, [rsp+278h+arg_28]
0x18001d750  mov     r8, r11; unsigned __int8 *
0x18001d753  mov     rdx, r10; unsigned __int8 *
0x18001d756  mov     [rsp+278h+var_258], eax; int
0x18001d75a  call    ?UpdateDstMBRGB16@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB16(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d75f  xor     esi, esi
0x18001d761  lea     rdi, [rsp+278h+Src]
0x18001d766  cmp     [rsp+278h+arg_40], esi
0x18001d76d  jle     short loc_18001D79B
0x18001d76f  lea     eax, [r15+r15]
0x18001d773  movsxd  rbp, eax
0x18001d776  mov     r8, rbp; Size
0x18001d779  mov     rdx, rdi; Src
0x18001d77c  mov     rcx, rbx; void *
0x18001d77f  call    memcpy_0
0x18001d784  movsxd  rax, dword ptr [r12+40h]
0x18001d789  add     rdi, 20h ; ' '
0x18001d78d  add     rbx, rax
0x18001d790  inc     esi
0x18001d792  cmp     esi, [rsp+278h+arg_40]
0x18001d799  jl      short loc_18001D776
0x18001d79b  mov     rcx, [rsp+278h+var_38]
0x18001d7a3  xor     rcx, rsp; StackCookie
0x18001d7a6  call    __security_check_cookie
0x18001d7ab  mov     rbx, [rsp+278h+arg_0]
0x18001d7b3  add     rsp, 250h
0x18001d7ba  pop     r15
0x18001d7bc  pop     r12
0x18001d7be  pop     rdi
0x18001d7bf  pop     rsi
0x18001d7c0  pop     rbp
0x18001d7c1  retn
```
