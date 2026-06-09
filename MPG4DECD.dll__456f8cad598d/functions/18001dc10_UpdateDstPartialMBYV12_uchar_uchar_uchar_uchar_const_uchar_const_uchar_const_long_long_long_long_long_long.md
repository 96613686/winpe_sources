# UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x18001dc10`
- end: `0x18001dd1a`
- name: `?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `266`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *Src, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18001dc10`
- `0x180021005`

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
0x18001dc10  push    rbx
0x18001dc12  push    rbp
0x18001dc13  push    rsi
0x18001dc14  push    rdi
0x18001dc15  push    r12
0x18001dc17  push    r13
0x18001dc19  push    r14
0x18001dc1b  push    r15
0x18001dc1d  sub     rsp, 38h
0x18001dc21  mov     eax, [rsp+78h+arg_50]
0x18001dc28  xor     r15d, r15d
0x18001dc2b  mov     ebx, [rsp+78h+arg_58]
0x18001dc32  and     eax, 0FFFFFFFEh
0x18001dc35  mov     r10d, eax
0x18001dc38  sar     ebx, 1
0x18001dc3a  sar     r10d, 1
0x18001dc3d  mov     rdi, r9
0x18001dc40  mov     rbp, r8
0x18001dc43  mov     r14, rdx
0x18001dc46  mov     rsi, rcx
0x18001dc49  test    ebx, ebx
0x18001dc4b  jle     loc_18001DD09
0x18001dc51  movsxd  r12, [rsp+78h+arg_30]
0x18001dc59  movsxd  r13, [rsp+78h+arg_40]
0x18001dc61  cdqe
0x18001dc63  movsxd  rcx, r10d
0x18001dc66  mov     [rsp+78h+Size], rax
0x18001dc6b  mov     [rsp+78h+var_58], rcx
0x18001dc70  mov     r8, rax; Size
0x18001dc73  mov     rdx, rdi; Src
0x18001dc76  mov     rcx, rsi; void *
0x18001dc79  call    memcpy_0
0x18001dc7e  mov     r8, [rsp+78h+Size]; Size
0x18001dc83  lea     rdx, [r12+rdi]; Src
0x18001dc87  lea     rcx, [rsi+r13]; void *
0x18001dc8b  call    memcpy_0
0x18001dc90  mov     r8, [rsp+78h+var_58]; Size
0x18001dc95  lea     rdi, [rdi+r12*2]
0x18001dc99  mov     rdx, [rsp+78h+Src]; Src
0x18001dca1  lea     rsi, [rsi+r13*2]
0x18001dca5  mov     rcx, r14; void *
0x18001dca8  call    memcpy_0
0x18001dcad  movsxd  rax, [rsp+78h+arg_38]
0x18001dcb5  mov     rcx, rbp; void *
0x18001dcb8  add     [rsp+78h+Src], rax
0x18001dcc0  movsxd  rax, [rsp+78h+arg_48]
0x18001dcc8  mov     r8, [rsp+78h+var_58]; Size
0x18001dccd  add     r14, rax
0x18001dcd0  mov     rdx, [rsp+78h+arg_28]; Src
0x18001dcd8  call    memcpy_0
0x18001dcdd  movsxd  rax, [rsp+78h+arg_38]
0x18001dce5  inc     r15d
0x18001dce8  add     [rsp+78h+arg_28], rax
0x18001dcf0  movsxd  rax, [rsp+78h+arg_48]
0x18001dcf8  add     rbp, rax
0x18001dcfb  mov     rax, [rsp+78h+Size]
0x18001dd00  cmp     r15d, ebx
0x18001dd03  jl      loc_18001DC70
0x18001dd09  add     rsp, 38h
0x18001dd0d  pop     r15
0x18001dd0f  pop     r14
0x18001dd11  pop     r13
0x18001dd13  pop     r12
0x18001dd15  pop     rdi
0x18001dd16  pop     rsi
0x18001dd17  pop     rbp
0x18001dd18  pop     rbx
0x18001dd19  retn
```
