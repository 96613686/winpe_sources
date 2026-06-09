# UpdateDstPartialMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long)

- ea: `0x180043120`
- end: `0x1800431e3`
- name: `?UpdateDstPartialMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJJ@Z`
- size: `195`
- prototype: `void __usercall(struct CDeColorConvParams *@<rcx>, unsigned __int8 *@<rdx>, const unsigned __int8 *@<r8>, const unsigned __int8 *@<r9>, const unsigned __int8 *, int, int, int, int)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update`

## callees

- `0x18002aac0`
- `0x18003ed40`
- `0x180043120`
- `0x180045805`

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
  unsigned __int8 Src[512]; // [rsp+40h] [rbp-248h] BYREF

  UpdateDstMBRGB16(a1, Src, a3, a4, a5, a6, a7, 32);
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
0x180043120  push    rbx
0x180043122  push    rbp
0x180043123  push    rsi
0x180043124  push    rdi
0x180043125  push    r12
0x180043127  push    r14
0x180043129  sub     rsp, 258h
0x180043130  mov     rax, cs:__security_cookie
0x180043137  xor     rax, rsp
0x18004313a  mov     [rsp+288h+var_48], rax
0x180043142  mov     eax, [rsp+288h+arg_30]
0x180043149  mov     r14, rcx
0x18004314c  mov     rcx, [rsp+288h+arg_20]
0x180043154  mov     rbx, rdx
0x180043157  mov     r12d, [rsp+288h+arg_38]
0x18004315f  lea     rdx, [rsp+288h+Src]; unsigned __int8 *
0x180043164  mov     [rsp+288h+var_250], 20h ; ' '; int
0x18004316c  mov     [rsp+288h+var_258], eax; int
0x180043170  mov     eax, [rsp+288h+arg_28]
0x180043177  mov     [rsp+288h+var_260], eax; int
0x18004317b  mov     [rsp+288h+var_268], rcx; unsigned __int8 *
0x180043180  mov     rcx, r14; struct CDeColorConvParams *
0x180043183  call    ?UpdateDstMBRGB16@@YAXPEAVCDeColorConvParams@@PEAEPEBE22JJJ@Z; UpdateDstMBRGB16(CDeColorConvParams *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long)
0x180043188  xor     esi, esi
0x18004318a  lea     rdi, [rsp+288h+Src]
0x18004318f  cmp     [rsp+288h+arg_40], esi
0x180043196  jle     short loc_1800431C3
0x180043198  lea     eax, [r12+r12]
0x18004319c  movsxd  rbp, eax
0x18004319f  mov     r8, rbp; Size
0x1800431a2  mov     rdx, rdi; Src
0x1800431a5  mov     rcx, rbx; void *
0x1800431a8  call    memcpy_0
0x1800431ad  movsxd  rax, dword ptr [r14+4Ch]
0x1800431b1  add     rdi, 20h ; ' '
0x1800431b5  add     rbx, rax
0x1800431b8  inc     esi
0x1800431ba  cmp     esi, [rsp+288h+arg_40]
0x1800431c1  jl      short loc_18004319F
0x1800431c3  mov     rcx, [rsp+288h+var_48]
0x1800431cb  xor     rcx, rsp; StackCookie
0x1800431ce  call    __security_check_cookie
0x1800431d3  add     rsp, 258h
0x1800431da  pop     r14
0x1800431dc  pop     r12
0x1800431de  pop     rdi
0x1800431df  pop     rsi
0x1800431e0  pop     rbp
0x1800431e1  pop     rbx
0x1800431e2  retn
```
