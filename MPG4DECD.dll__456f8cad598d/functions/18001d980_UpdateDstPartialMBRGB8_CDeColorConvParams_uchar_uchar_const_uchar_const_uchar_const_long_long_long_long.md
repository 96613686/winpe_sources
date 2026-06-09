# UpdateDstPartialMBRGB8(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x18001d980`
- end: `0x18001da3c`
- name: `?UpdateDstPartialMBRGB8@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `188`
- prototype: `void(struct CDeColorConvParams *, unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x1800018b0`
- `0x18001bd10`
- `0x18001d980`
- `0x180021005`

## pseudocode

```c
void __fastcall UpdateDstPartialMBRGB8(
        struct CDeColorConvParams *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *a4,
        unsigned __int8 *a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int v11; // esi
  unsigned __int8 *i; // rdi
  unsigned __int8 Src[256]; // [rsp+40h] [rbp-138h] BYREF

  UpdateDstMBRGB8(Src, a3, a4, a5, a6, a7, 16);
  v11 = 0;
  for ( i = Src; v11 < a9; ++v11 )
  {
    memcpy_0(a2, i, a8);
    i += 16;
    a2 += *((int *)a1 + 16);
  }
}

```

## disassembly

```asm
0x18001d980  push    rbx
0x18001d982  push    rbp
0x18001d983  push    rsi
0x18001d984  push    rdi
0x18001d985  push    r15
0x18001d987  sub     rsp, 150h
0x18001d98e  mov     rax, cs:__security_cookie
0x18001d995  xor     rax, rsp
0x18001d998  mov     [rsp+178h+var_38], rax
0x18001d9a0  mov     eax, [rsp+178h+arg_30]
0x18001d9a7  mov     r11, r9
0x18001d9aa  mov     r9, [rsp+178h+arg_20]; unsigned __int8 *
0x18001d9b2  mov     r10, r8
0x18001d9b5  mov     [rsp+178h+var_148], 10h; int
0x18001d9bd  mov     rbx, rdx
0x18001d9c0  mov     [rsp+178h+var_150], eax; int
0x18001d9c4  mov     r15, rcx
0x18001d9c7  mov     eax, [rsp+178h+arg_28]
0x18001d9ce  lea     rcx, [rsp+178h+Src]; unsigned __int8 *
0x18001d9d3  mov     r8, r11; unsigned __int8 *
0x18001d9d6  mov     [rsp+178h+var_158], eax; int
0x18001d9da  mov     rdx, r10; unsigned __int8 *
0x18001d9dd  call    ?UpdateDstMBRGB8@@YAXPEAEPEBE11JJJ@Z; UpdateDstMBRGB8(uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x18001d9e2  xor     esi, esi
0x18001d9e4  lea     rdi, [rsp+178h+Src]
0x18001d9e9  cmp     [rsp+178h+arg_40], esi
0x18001d9f0  jle     short loc_18001DA1E
0x18001d9f2  movsxd  rbp, [rsp+178h+arg_38]
0x18001d9fa  mov     r8, rbp; Size
0x18001d9fd  mov     rdx, rdi; Src
0x18001da00  mov     rcx, rbx; void *
0x18001da03  call    memcpy_0
0x18001da08  movsxd  rax, dword ptr [r15+40h]
0x18001da0c  add     rdi, 10h
0x18001da10  add     rbx, rax
0x18001da13  inc     esi
0x18001da15  cmp     esi, [rsp+178h+arg_40]
0x18001da1c  jl      short loc_18001D9FA
0x18001da1e  mov     rcx, [rsp+178h+var_38]
0x18001da26  xor     rcx, rsp; StackCookie
0x18001da29  call    __security_check_cookie
0x18001da2e  add     rsp, 150h
0x18001da35  pop     r15
0x18001da37  pop     rdi
0x18001da38  pop     rsi
0x18001da39  pop     rbp
0x18001da3a  pop     rbx
0x18001da3b  retn
```
