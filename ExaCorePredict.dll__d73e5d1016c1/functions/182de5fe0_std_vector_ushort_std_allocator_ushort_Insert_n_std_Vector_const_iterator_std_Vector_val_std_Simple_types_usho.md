# std::vector<ushort,std::allocator<ushort>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<ushort>>>,unsigned __int64,ushort const &)

- ea: `0x182de5fe0`
- end: `0x182de6286`
- name: `?_Insert_n@?$vector@GV?$allocator@G@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@G@std@@@std@@@2@_KAEBG@Z`
- size: `678`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x182de7b10`
- `0x183087180`
- `0x1832827e0`
- `0x183283650`
- `0x1832844b0`
- `0x183285380`
- `0x183286260`
- `0x183287140`
- `0x183288180`
- `0x183289010`
- `0x183289e90`

## callees

- `0x182d75f10`
- `0x182da9d20`
- `0x182de5fe0`
- `0x182fd8950`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de60de`
- `VCRUNTIME140!memmove` at `0x182de60fb`
- `VCRUNTIME140!memmove` at `0x182de6174`
- `VCRUNTIME140!memmove` at `0x182de620a`
- `VCRUNTIME140!memmove` at `0x182de6230`
- `VCRUNTIME140!memmove` at `0x182de60de`
- `VCRUNTIME140!memmove` at `0x182de60fb`
- `VCRUNTIME140!memmove` at `0x182de6174`
- `VCRUNTIME140!memmove` at `0x182de620a`
- `VCRUNTIME140!memmove` at `0x182de6230`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned short>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        __int16 *a5)
{
  _BYTE *v9; // r8
  __int64 v10; // r12
  char *v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // r15
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  char *v17; // rsi
  __int64 v18; // r14
  unsigned __int64 v19; // rdi
  __int64 v20; // r14
  char *v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  __int16 v24; // ax
  __int16 v25; // r15
  char *i; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-78h]
  char v30; // [rsp+20h] [rbp-78h]
  __int16 v31; // [rsp+30h] [rbp-68h] BYREF
  CxVector *v32; // [rsp+38h] [rbp-60h]
  unsigned __int64 v33; // [rsp+40h] [rbp-58h]
  __int64 v34; // [rsp+48h] [rbp-50h]
  __int64 v35; // [rsp+50h] [rbp-48h]

  v35 = -2;
  v32 = a1;
  v9 = *(_BYTE **)a1;
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 1;
  if ( a4 )
  {
    v11 = (char *)*((_QWORD *)a1 + 1);
    if ( (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v11) >> 1 >= a4 )
    {
      v20 = 2 * a4;
      if ( (v11 - a3) >> 1 >= a4 )
      {
        v25 = *a5;
        memmove(v11, &v11[-v20], 2 * a4);
        *((_QWORD *)a1 + 1) = &v11[v20];
        memmove(&a3[2 * a4], a3, (size_t)&v11[-2LL * a4 - (_QWORD)a3]);
        for ( i = a3; i != &a3[v20]; i += 2 )
          *(_WORD *)i = v25;
      }
      else
      {
        v31 = *a5;
        memmove(&a3[v20], a3, v11 - a3);
        try
        {
          v30 = v31;
          std::_Uninit_alloc_fill_n1<unsigned short *,unsigned __int64,std::allocator<unsigned short>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 1),
            &v31,
            a1,
            v30);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += v20;
        v21 = a3;
        v22 = 0;
        v23 = (unsigned __int64)(*((_QWORD *)a1 + 1) - v20 - (_QWORD)a3 + 1) >> 1;
        if ( (unsigned __int64)a3 > *((_QWORD *)a1 + 1) - v20 )
          v23 = 0;
        if ( v23 )
        {
          v24 = v31;
          do
          {
            *(_WORD *)v21 = v24;
            v21 += 2;
            ++v22;
          }
          while ( v22 != v23 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 1;
      if ( 0x7FFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v9) >> 1;
      v15 = 0;
      if ( 0x7FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v33 = v13;
      v16 = std::allocator<wchar_t>::allocate(a1, v13);
      v17 = (char *)v16;
      v34 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 1;
      try
      {
        v29 = v31;
        std::_Uninit_alloc_fill_n1<unsigned short *,unsigned __int64,std::allocator<unsigned short>>(
          v16 + 2 * v18,
          a4,
          a5,
          a1,
          v29);
        memmove(v17, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[2 * a4 + 2 * v18], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v32);
        std::_Wrap_alloc<std::allocator<unsigned short>>::deallocate(Pointer, v34, v33);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 1) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<wchar_t>::deallocate(a1, *(_QWORD *)a1, (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 1);
      *((_QWORD *)a1 + 2) = &v17[2 * v13];
      *((_QWORD *)a1 + 1) = &v17[2 * v19];
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 2 * v10;
  return a2;
}

```

## disassembly

```asm
0x182de5fe0  mov     [rsp+Src], r8
0x182de5fe5  push    rbx
0x182de5fe6  push    rsi
0x182de5fe7  push    rdi
0x182de5fe8  push    r12
0x182de5fea  push    r13
0x182de5fec  push    r14
0x182de5fee  push    r15
0x182de5ff0  sub     rsp, 60h
0x182de5ff4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x182de5ffd  mov     rdi, r9
0x182de6000  mov     rax, r8
0x182de6003  mov     r13, rdx
0x182de6006  mov     rbx, rcx
0x182de6009  mov     [rsp+98h+var_60], rcx
0x182de600e  mov     r8, [rcx]
0x182de6011  mov     r12, rax
0x182de6014  sub     r12, r8
0x182de6017  sar     r12, 1
0x182de601a  test    r9, r9
0x182de601d  jz      loc_182DE6268
0x182de6023  mov     rsi, [rcx+8]
0x182de6027  mov     rdx, [rcx+10h]
0x182de602b  mov     rcx, rdx
0x182de602e  sub     rcx, rsi
0x182de6031  sar     rcx, 1
0x182de6034  cmp     rcx, r9
0x182de6037  jnb     loc_182DE6141
0x182de603d  sub     rsi, r8
0x182de6040  sar     rsi, 1
0x182de6043  mov     r9, 7FFFFFFFFFFFFFFFh
0x182de604d  mov     rax, r9
0x182de6050  sub     rax, rsi
0x182de6053  cmp     rax, rdi
0x182de6056  jnb     short loc_182DE6061
0x182de6058  mov     rcx, rbx
0x182de605b  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de6061  lea     r15, [rdi+rsi]
0x182de6065  sub     rdx, r8
0x182de6068  sar     rdx, 1
0x182de606b  mov     rax, rdx
0x182de606e  shr     rax, 1
0x182de6071  sub     r9, rax
0x182de6074  add     rax, rdx
0x182de6077  xor     ecx, ecx
0x182de6079  cmp     r9, rdx
0x182de607c  cmovnb  rcx, rax
0x182de6080  cmp     rcx, r15
0x182de6083  cmovnb  r15, rcx
0x182de6087  mov     [rsp+98h+var_58], r15
0x182de608c  mov     rdx, r15
0x182de608f  mov     rcx, rbx
0x182de6092  call    ?allocate@?$allocator@_W@std@@QEAAPEA_W_K@Z; std::allocator<wchar_t>::allocate(unsigned __int64)
0x182de6097  mov     rsi, rax
0x182de609a  mov     [rsp+98h+var_50], rax
0x182de609f  mov     r14, [rsp+98h+Src]
0x182de60a7  sub     r14, [rbx]
0x182de60aa  sar     r14, 1
0x182de60ad  lea     rcx, [rax+r14*2]
0x182de60b1  movzx   eax, byte ptr [rsp+98h+var_68]
0x182de60b6  mov     [rsp+98h+var_78], al
0x182de60ba  mov     r9, rbx
0x182de60bd  mov     r8, [rsp+98h+arg_20]
0x182de60c5  mov     rdx, rdi
0x182de60c8  call    ??$_Uninit_alloc_fill_n1@PEAG_KV?$allocator@G@std@@@std@@YAXPEAG_KPEBGAEAU?$_Wrap_alloc@V?$allocator@G@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<ushort *,unsigned __int64,std::allocator<ushort>>(ushort *,unsigned __int64,ushort const *,std::_Wrap_alloc<std::allocator<ushort>> &,std::integral_constant<bool,0>)
0x182de60cd  mov     rdx, [rbx]; Src
0x182de60d0  mov     r8, [rsp+98h+Src]
0x182de60d8  sub     r8, rdx; Size
0x182de60db  mov     rcx, rsi; void *
0x182de60de  call    cs:__imp_memmove
0x182de60e4  mov     r8, [rbx+8]
0x182de60e8  lea     rax, [rdi+r14]
0x182de60ec  lea     rcx, [rsi+rax*2]; void *
0x182de60f0  mov     rdx, [rsp+98h+Src]; Src
0x182de60f8  sub     r8, rdx; Size
0x182de60fb  call    cs:__imp_memmove
0x182de6101  nop
0x182de6102  mov     rdx, [rbx]
0x182de6105  mov     rax, [rbx+8]
0x182de6109  sub     rax, rdx
0x182de610c  sar     rax, 1
0x182de610f  add     rdi, rax
0x182de6112  test    rdx, rdx
0x182de6115  jz      short loc_182DE6129
0x182de6117  mov     r8, [rbx+10h]
0x182de611b  sub     r8, rdx
0x182de611e  sar     r8, 1
0x182de6121  mov     rcx, rbx
0x182de6124  call    ?deallocate@?$allocator@_W@std@@QEAAXPEA_W_K@Z; std::allocator<wchar_t>::deallocate(wchar_t *,unsigned __int64)
0x182de6129  lea     rax, [rsi+r15*2]
0x182de612d  mov     [rbx+10h], rax
0x182de6131  lea     rax, [rsi+rdi*2]
0x182de6135  mov     [rbx+8], rax
0x182de6139  mov     [rbx], rsi
0x182de613c  jmp     loc_182DE6268
0x182de6141  mov     rcx, rsi
0x182de6144  sub     rcx, rax
0x182de6147  sar     rcx, 1
0x182de614a  lea     r14, [r9+r9]
0x182de614e  cmp     rcx, rdi
0x182de6151  jnb     loc_182DE61F2
0x182de6157  mov     rcx, [rsp+98h+arg_20]
0x182de615f  movzx   edx, word ptr [rcx]
0x182de6162  mov     [rsp+98h+var_68], dx
0x182de6167  lea     rcx, [r14+rax]; void *
0x182de616b  sub     rsi, rax
0x182de616e  mov     r8, rsi; Size
0x182de6171  mov     rdx, rax; Src
0x182de6174  call    cs:__imp_memmove
0x182de617a  nop
0x182de617b  mov     rax, [rbx+8]
0x182de617f  sub     rax, [rsp+98h+Src]
0x182de6187  sar     rax, 1
0x182de618a  sub     rdi, rax
0x182de618d  movzx   eax, byte ptr [rsp+98h+var_68]
0x182de6192  mov     [rsp+98h+var_78], al
0x182de6196  mov     r9, rbx
0x182de6199  lea     r8, [rsp+98h+var_68]
0x182de619e  mov     rdx, rdi
0x182de61a1  mov     rcx, [rbx+8]
0x182de61a5  call    ??$_Uninit_alloc_fill_n1@PEAG_KV?$allocator@G@std@@@std@@YAXPEAG_KPEBGAEAU?$_Wrap_alloc@V?$allocator@G@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<ushort *,unsigned __int64,std::allocator<ushort>>(ushort *,unsigned __int64,ushort const *,std::_Wrap_alloc<std::allocator<ushort>> &,std::integral_constant<bool,0>)
0x182de61aa  nop
0x182de61ab  add     [rbx+8], r14
0x182de61af  mov     rax, [rbx+8]
0x182de61b3  sub     rax, r14
0x182de61b6  mov     rdx, [rsp+98h+Src]
0x182de61be  xor     ecx, ecx
0x182de61c0  mov     r8, rax
0x182de61c3  sub     r8, rdx
0x182de61c6  inc     r8
0x182de61c9  shr     r8, 1
0x182de61cc  cmp     rdx, rax
0x182de61cf  cmova   r8, rcx
0x182de61d3  test    r8, r8
0x182de61d6  jz      loc_182DE6268
0x182de61dc  movzx   eax, [rsp+98h+var_68]
0x182de61e1  mov     [rdx], ax
0x182de61e4  lea     rdx, [rdx+2]
0x182de61e8  inc     rcx
0x182de61eb  cmp     rcx, r8
0x182de61ee  jnz     short loc_182DE61E1
0x182de61f0  jmp     short loc_182DE6268
0x182de61f2  mov     rax, [rsp+98h+arg_20]
0x182de61fa  movzx   r15d, word ptr [rax]
0x182de61fe  mov     rdx, rsi
0x182de6201  sub     rdx, r14; Src
0x182de6204  mov     r8, r14; Size
0x182de6207  mov     rcx, rsi; void *
0x182de620a  call    cs:__imp_memmove
0x182de6210  lea     rax, [r14+rsi]
0x182de6214  mov     [rbx+8], rax
0x182de6218  imul    r8, rdi, -2
0x182de621c  mov     rdx, [rsp+98h+Src]; Src
0x182de6224  sub     r8, rdx
0x182de6227  add     r8, rsi; Size
0x182de622a  sub     rsi, r8
0x182de622d  mov     rcx, rsi; void *
0x182de6230  call    cs:__imp_memmove
0x182de6236  mov     r8, [rsp+98h+Src]
0x182de623e  lea     rax, [r14+r8]
0x182de6242  cmp     r8, rax
0x182de6245  jz      short loc_182DE6268
0x182de6247  nop     word ptr [rax+rax+00000000h]
0x182de6250  mov     [r8], r15w
0x182de6254  add     r8, 2
0x182de6258  mov     rdx, [rsp+98h+Src]
0x182de6260  add     rdx, r14
0x182de6263  cmp     r8, rdx
0x182de6266  jnz     short loc_182DE6250
0x182de6268  mov     rcx, [rbx]
0x182de626b  lea     rdx, [rcx+r12*2]
0x182de626f  mov     [r13+0], rdx
0x182de6273  mov     rax, r13
0x182de6276  add     rsp, 60h
0x182de627a  pop     r15
0x182de627c  pop     r14
0x182de627e  pop     r13
0x182de6280  pop     r12
0x182de6282  pop     rdi
0x182de6283  pop     rsi
0x182de6284  pop     rbx
0x182de6285  retn
```
