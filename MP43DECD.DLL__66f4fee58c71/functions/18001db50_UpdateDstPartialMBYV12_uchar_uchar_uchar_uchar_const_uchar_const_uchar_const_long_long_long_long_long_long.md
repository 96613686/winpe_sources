# UpdateDstPartialMBYV12(uchar *,uchar *,uchar *,uchar const *,uchar const *,uchar const *,long,long,long,long,long,long)

- ea: `0x18001db50`
- end: `0x18001dc5a`
- name: `?UpdateDstPartialMBYV12@@YAXPEAE00PEBE11JJJJJJ@Z`
- size: `266`
- prototype: `void __fastcall(unsigned __int8 *, unsigned __int8 *, unsigned __int8 *, const unsigned __int8 *Src, const unsigned __int8 *, const unsigned __int8 *, int, int, int, int, int, int)`
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x18001db50`
- `0x180020f45`

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
0x18001db50  push    rbx
0x18001db52  push    rbp
0x18001db53  push    rsi
0x18001db54  push    rdi
0x18001db55  push    r12
0x18001db57  push    r13
0x18001db59  push    r14
0x18001db5b  push    r15
0x18001db5d  sub     rsp, 38h
0x18001db61  mov     eax, [rsp+78h+arg_50]
0x18001db68  xor     r15d, r15d
0x18001db6b  mov     ebx, [rsp+78h+arg_58]
0x18001db72  and     eax, 0FFFFFFFEh
0x18001db75  mov     r10d, eax
0x18001db78  sar     ebx, 1
0x18001db7a  sar     r10d, 1
0x18001db7d  mov     rdi, r9
0x18001db80  mov     rbp, r8
0x18001db83  mov     r14, rdx
0x18001db86  mov     rsi, rcx
0x18001db89  test    ebx, ebx
0x18001db8b  jle     loc_18001DC49
0x18001db91  movsxd  r12, [rsp+78h+arg_30]
0x18001db99  movsxd  r13, [rsp+78h+arg_40]
0x18001dba1  cdqe
0x18001dba3  movsxd  rcx, r10d
0x18001dba6  mov     [rsp+78h+Size], rax
0x18001dbab  mov     [rsp+78h+var_58], rcx
0x18001dbb0  mov     r8, rax; Size
0x18001dbb3  mov     rdx, rdi; Src
0x18001dbb6  mov     rcx, rsi; void *
0x18001dbb9  call    memcpy_0
0x18001dbbe  mov     r8, [rsp+78h+Size]; Size
0x18001dbc3  lea     rdx, [r12+rdi]; Src
0x18001dbc7  lea     rcx, [rsi+r13]; void *
0x18001dbcb  call    memcpy_0
0x18001dbd0  mov     r8, [rsp+78h+var_58]; Size
0x18001dbd5  lea     rdi, [rdi+r12*2]
0x18001dbd9  mov     rdx, [rsp+78h+Src]; Src
0x18001dbe1  lea     rsi, [rsi+r13*2]
0x18001dbe5  mov     rcx, r14; void *
0x18001dbe8  call    memcpy_0
0x18001dbed  movsxd  rax, [rsp+78h+arg_38]
0x18001dbf5  mov     rcx, rbp; void *
0x18001dbf8  add     [rsp+78h+Src], rax
0x18001dc00  movsxd  rax, [rsp+78h+arg_48]
0x18001dc08  mov     r8, [rsp+78h+var_58]; Size
0x18001dc0d  add     r14, rax
0x18001dc10  mov     rdx, [rsp+78h+arg_28]; Src
0x18001dc18  call    memcpy_0
0x18001dc1d  movsxd  rax, [rsp+78h+arg_38]
0x18001dc25  inc     r15d
0x18001dc28  add     [rsp+78h+arg_28], rax
0x18001dc30  movsxd  rax, [rsp+78h+arg_48]
0x18001dc38  add     rbp, rax
0x18001dc3b  mov     rax, [rsp+78h+Size]
0x18001dc40  cmp     r15d, ebx
0x18001dc43  jl      loc_18001DBB0
0x18001dc49  add     rsp, 38h
0x18001dc4d  pop     r15
0x18001dc4f  pop     r14
0x18001dc51  pop     r13
0x18001dc53  pop     r12
0x18001dc55  pop     rdi
0x18001dc56  pop     rsi
0x18001dc57  pop     rbp
0x18001dc58  pop     rbx
0x18001dc59  retn
```
