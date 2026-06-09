# UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x180043680`
- end: `0x18004378a`
- name: `?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `266`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *Src, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180043680`
- `0x180045805`

## pseudocode

```c
void __fastcall UpdateDstPartialMBYV12(
        unsigned __int8 *a1,
        unsigned __int8 *a2,
        unsigned __int8 *a3,
        const unsigned __int8 *Src,
        const unsigned __int8 *Srca,
        const unsigned __int8 *a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        int a12)
{
  int v12; // r15d
  size_t v13; // rax
  size_t v18; // [rsp+20h] [rbp-58h]
  size_t Size; // [rsp+28h] [rbp-50h]

  v12 = 0;
  LODWORD(v13) = a11 & 0xFFFFFFFE;
  if ( a12 >> 1 > 0 )
  {
    v13 = (int)v13;
    Size = (int)v13;
    v18 = (int)(a11 & 0xFFFFFFFE) >> 1;
    do
    {
      memcpy_0(a1, Src, v13);
      memcpy_0(&a1[a9], &Src[a7], Size);
      Src += 2 * a7;
      a1 += 2 * a9;
      memcpy_0(a2, Srca, v18);
      Srca += a8;
      a2 += a10;
      memcpy_0(a3, a6, v18);
      ++v12;
      a6 += a8;
      a3 += a10;
      v13 = Size;
    }
    while ( v12 < a12 >> 1 );
  }
}

```

## disassembly

```asm
0x180043680  push    rbx
0x180043682  push    rbp
0x180043683  push    rsi
0x180043684  push    rdi
0x180043685  push    r12
0x180043687  push    r13
0x180043689  push    r14
0x18004368b  push    r15
0x18004368d  sub     rsp, 38h
0x180043691  mov     eax, [rsp+78h+arg_50]
0x180043698  xor     r15d, r15d
0x18004369b  mov     ebx, [rsp+78h+arg_58]
0x1800436a2  and     eax, 0FFFFFFFEh
0x1800436a5  mov     r10d, eax
0x1800436a8  sar     ebx, 1
0x1800436aa  sar     r10d, 1
0x1800436ad  mov     rdi, r9
0x1800436b0  mov     rbp, r8
0x1800436b3  mov     r14, rdx
0x1800436b6  mov     rsi, rcx
0x1800436b9  test    ebx, ebx
0x1800436bb  jle     loc_180043779
0x1800436c1  movsxd  r12, [rsp+78h+arg_30]
0x1800436c9  movsxd  r13, [rsp+78h+arg_40]
0x1800436d1  cdqe
0x1800436d3  movsxd  rcx, r10d
0x1800436d6  mov     [rsp+78h+Size], rax
0x1800436db  mov     [rsp+78h+var_58], rcx
0x1800436e0  mov     r8, rax; Size
0x1800436e3  mov     rdx, rdi; Src
0x1800436e6  mov     rcx, rsi; void *
0x1800436e9  call    memcpy_0
0x1800436ee  mov     r8, [rsp+78h+Size]; Size
0x1800436f3  lea     rdx, [r12+rdi]; Src
0x1800436f7  lea     rcx, [rsi+r13]; void *
0x1800436fb  call    memcpy_0
0x180043700  mov     r8, [rsp+78h+var_58]; Size
0x180043705  lea     rdi, [rdi+r12*2]
0x180043709  mov     rdx, [rsp+78h+Src]; Src
0x180043711  lea     rsi, [rsi+r13*2]
0x180043715  mov     rcx, r14; void *
0x180043718  call    memcpy_0
0x18004371d  movsxd  rax, [rsp+78h+arg_38]
0x180043725  mov     rcx, rbp; void *
0x180043728  add     [rsp+78h+Src], rax
0x180043730  movsxd  rax, [rsp+78h+arg_48]
0x180043738  mov     r8, [rsp+78h+var_58]; Size
0x18004373d  add     r14, rax
0x180043740  mov     rdx, [rsp+78h+arg_28]; Src
0x180043748  call    memcpy_0
0x18004374d  movsxd  rax, [rsp+78h+arg_38]
0x180043755  inc     r15d
0x180043758  add     [rsp+78h+arg_28], rax
0x180043760  movsxd  rax, [rsp+78h+arg_48]
0x180043768  add     rbp, rax
0x18004376b  mov     rax, [rsp+78h+Size]
0x180043770  cmp     r15d, ebx
0x180043773  jl      loc_1800436E0
0x180043779  add     rsp, 38h
0x18004377d  pop     r15
0x18004377f  pop     r14
0x180043781  pop     r13
0x180043783  pop     r12
0x180043785  pop     rdi
0x180043786  pop     rsi
0x180043787  pop     rbp
0x180043788  pop     rbx
0x180043789  retn
```
