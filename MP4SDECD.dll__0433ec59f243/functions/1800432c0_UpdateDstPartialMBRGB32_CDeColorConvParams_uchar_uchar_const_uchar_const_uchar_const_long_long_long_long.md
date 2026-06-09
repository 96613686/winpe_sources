# UpdateDstPartialMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x1800432c0`
- end: `0x180043381`
- name: `?UpdateDstPartialMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `193`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x1800408b0`
- `0x1800432c0`
- `0x180045805`

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

  UpdateDstMBRGB32(a1, Src, a3, a4, a5, a6, a7, 64);
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
0x1800432c0  push    rbx
0x1800432c2  push    rbp
0x1800432c3  push    rsi
0x1800432c4  push    rdi
0x1800432c5  push    r14
0x1800432c7  sub     rsp, 450h
0x1800432ce  mov     rax, cs:__security_cookie
0x1800432d5  xor     rax, rsp
0x1800432d8  mov     [rsp+478h+var_38], rax
0x1800432e0  mov     eax, [rsp+478h+arg_30]
0x1800432e7  mov     r14, rcx
0x1800432ea  mov     rcx, [rsp+478h+arg_20]
0x1800432f2  mov     rbx, rdx
0x1800432f5  mov     ebp, [rsp+478h+arg_38]
0x1800432fc  lea     rdx, [rsp+478h+Src]; unsigned __int8 *
0x180043301  mov     [rsp+478h+var_440], 40h ; '@'; int
0x180043309  mov     [rsp+478h+var_448], eax; int
0x18004330d  mov     eax, [rsp+478h+arg_28]
0x180043314  mov     [rsp+478h+var_450], eax; int
0x180043318  mov     [rsp+478h+var_458], rcx; unsigned __int8 *
0x18004331d  mov     rcx, r14; struct CDeColorConvParams *
0x180043320  call    ?UpdateDstMBRGB32@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB32(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180043325  xor     esi, esi
0x180043327  lea     rdi, [rsp+478h+Src]
0x18004332c  cmp     [rsp+478h+arg_40], esi
0x180043333  jle     short loc_180043363
0x180043335  lea     eax, ds:0[rbp*4]
0x18004333c  movsxd  rbp, eax
0x18004333f  mov     r8, rbp; Size
0x180043342  mov     rdx, rdi; Src
0x180043345  mov     rcx, rbx; void *
0x180043348  call    memcpy_0
0x18004334d  movsxd  rax, dword ptr [r14+4Ch]
0x180043351  add     rdi, 40h ; '@'
0x180043355  add     rbx, rax
0x180043358  inc     esi
0x18004335a  cmp     esi, [rsp+478h+arg_40]
0x180043361  jl      short loc_18004333F
0x180043363  mov     rcx, [rsp+478h+var_38]
0x18004336b  xor     rcx, rsp; StackCookie
0x18004336e  call    __security_check_cookie
0x180043373  add     rsp, 450h
0x18004337a  pop     r14
0x18004337c  pop     rdi
0x18004337d  pop     rsi
0x18004337e  pop     rbp
0x18004337f  pop     rbx
0x180043380  retn
```
