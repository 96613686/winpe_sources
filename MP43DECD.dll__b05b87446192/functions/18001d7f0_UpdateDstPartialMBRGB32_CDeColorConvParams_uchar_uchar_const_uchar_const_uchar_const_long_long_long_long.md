# UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d7f0`
- end: `0x18001d8b5`
- name: `?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `197`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x180001880`
- `0x18001af20`
- `0x18001d7f0`
- `0x180020f45`

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
0x18001d7f0  push    rbx
0x18001d7f2  push    rbp
0x18001d7f3  push    rsi
0x18001d7f4  push    rdi
0x18001d7f5  push    r15
0x18001d7f7  sub     rsp, 450h
0x18001d7fe  mov     rax, cs:__security_cookie
0x18001d805  xor     rax, rsp
0x18001d808  mov     [rsp+478h+var_38], rax
0x18001d810  mov     eax, [rsp+478h+arg_30]
0x18001d817  mov     r11, r9
0x18001d81a  mov     r9, [rsp+478h+arg_20]; unsigned __int8 *
0x18001d822  mov     r10, r8
0x18001d825  mov     ebp, [rsp+478h+arg_38]
0x18001d82c  mov     rbx, rdx
0x18001d82f  mov     [rsp+478h+var_448], 40h ; '@'; int
0x18001d837  mov     r15, rcx
0x18001d83a  mov     [rsp+478h+var_450], eax; int
0x18001d83e  lea     rcx, [rsp+478h+Src]; unsigned __int8 *
0x18001d843  mov     eax, [rsp+478h+arg_28]
0x18001d84a  mov     r8, r11; unsigned __int8 *
0x18001d84d  mov     rdx, r10; unsigned __int8 *
0x18001d850  mov     [rsp+478h+var_458], eax; int
0x18001d854  call    ?UpdateDstMBRGB32@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB32(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d859  xor     esi, esi
0x18001d85b  lea     rdi, [rsp+478h+Src]
0x18001d860  cmp     [rsp+478h+arg_40], esi
0x18001d867  jle     short loc_18001D897
0x18001d869  lea     eax, ds:0[rbp*4]
0x18001d870  movsxd  rbp, eax
0x18001d873  mov     r8, rbp; Size
0x18001d876  mov     rdx, rdi; Src
0x18001d879  mov     rcx, rbx; void *
0x18001d87c  call    memcpy_0
0x18001d881  movsxd  rax, dword ptr [r15+40h]
0x18001d885  add     rdi, 40h ; '@'
0x18001d889  add     rbx, rax
0x18001d88c  inc     esi
0x18001d88e  cmp     esi, [rsp+478h+arg_40]
0x18001d895  jl      short loc_18001D873
0x18001d897  mov     rcx, [rsp+478h+var_38]
0x18001d89f  xor     rcx, rsp; StackCookie
0x18001d8a2  call    __security_check_cookie
0x18001d8a7  add     rsp, 450h
0x18001d8ae  pop     r15
0x18001d8b0  pop     rdi
0x18001d8b1  pop     rsi
0x18001d8b2  pop     rbp
0x18001d8b3  pop     rbx
0x18001d8b4  retn
```
