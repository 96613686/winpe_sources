# std::vector<short,std::allocator<short>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<short>>>,unsigned __int64,short const &)

- ea: `0x182de5d30`
- end: `0x182de5fd6`
- name: `?_Insert_n@?$vector@FV?$allocator@F@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@F@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@F@std@@@std@@@2@_KAEBF@Z`
- size: `678`
- prototype: ``
- caller_count: `11`
- callee_count: `5`
- tags: ``

## callers

- `0x182de7a40`
- `0x183087070`
- `0x1832822f0`
- `0x183283180`
- `0x183283fe0`
- `0x183284e50`
- `0x183285d30`
- `0x183286c10`
- `0x183287bf0`
- `0x183288b40`
- `0x1832899c0`

## callees

- `0x182d75ee0`
- `0x182da9d20`
- `0x182de5d30`
- `0x182fd8950`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de5e2e`
- `VCRUNTIME140!memmove` at `0x182de5e4b`
- `VCRUNTIME140!memmove` at `0x182de5ec4`
- `VCRUNTIME140!memmove` at `0x182de5f5a`
- `VCRUNTIME140!memmove` at `0x182de5f80`
- `VCRUNTIME140!memmove` at `0x182de5e2e`
- `VCRUNTIME140!memmove` at `0x182de5e4b`
- `VCRUNTIME140!memmove` at `0x182de5ec4`
- `VCRUNTIME140!memmove` at `0x182de5f5a`
- `VCRUNTIME140!memmove` at `0x182de5f80`

## pseudocode

```c
_QWORD *__fastcall std::vector<short>::_Insert_n(CxVector *a1, _QWORD *a2, char *a3, unsigned __int64 a4, __int16 *a5)
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
          std::_Uninit_alloc_fill_n1<short *,unsigned __int64,std::allocator<short>>(
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
        std::_Uninit_alloc_fill_n1<short *,unsigned __int64,std::allocator<short>>(v16 + 2 * v18, a4, a5, a1, v29);
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
0x182de5d30  mov     [rsp+Src], r8
0x182de5d35  push    rbx
0x182de5d36  push    rsi
0x182de5d37  push    rdi
0x182de5d38  push    r12
0x182de5d3a  push    r13
0x182de5d3c  push    r14
0x182de5d3e  push    r15
0x182de5d40  sub     rsp, 60h
0x182de5d44  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x182de5d4d  mov     rdi, r9
0x182de5d50  mov     rax, r8
0x182de5d53  mov     r13, rdx
0x182de5d56  mov     rbx, rcx
0x182de5d59  mov     [rsp+98h+var_60], rcx
0x182de5d5e  mov     r8, [rcx]
0x182de5d61  mov     r12, rax
0x182de5d64  sub     r12, r8
0x182de5d67  sar     r12, 1
0x182de5d6a  test    r9, r9
0x182de5d6d  jz      loc_182DE5FB8
0x182de5d73  mov     rsi, [rcx+8]
0x182de5d77  mov     rdx, [rcx+10h]
0x182de5d7b  mov     rcx, rdx
0x182de5d7e  sub     rcx, rsi
0x182de5d81  sar     rcx, 1
0x182de5d84  cmp     rcx, r9
0x182de5d87  jnb     loc_182DE5E91
0x182de5d8d  sub     rsi, r8
0x182de5d90  sar     rsi, 1
0x182de5d93  mov     r9, 7FFFFFFFFFFFFFFFh
0x182de5d9d  mov     rax, r9
0x182de5da0  sub     rax, rsi
0x182de5da3  cmp     rax, rdi
0x182de5da6  jnb     short loc_182DE5DB1
0x182de5da8  mov     rcx, rbx
0x182de5dab  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de5db1  lea     r15, [rdi+rsi]
0x182de5db5  sub     rdx, r8
0x182de5db8  sar     rdx, 1
0x182de5dbb  mov     rax, rdx
0x182de5dbe  shr     rax, 1
0x182de5dc1  sub     r9, rax
0x182de5dc4  add     rax, rdx
0x182de5dc7  xor     ecx, ecx
0x182de5dc9  cmp     r9, rdx
0x182de5dcc  cmovnb  rcx, rax
0x182de5dd0  cmp     rcx, r15
0x182de5dd3  cmovnb  r15, rcx
0x182de5dd7  mov     [rsp+98h+var_58], r15
0x182de5ddc  mov     rdx, r15
0x182de5ddf  mov     rcx, rbx
0x182de5de2  call    ?allocate@?$allocator@_W@std@@QEAAPEA_W_K@Z; std::allocator<wchar_t>::allocate(unsigned __int64)
0x182de5de7  mov     rsi, rax
0x182de5dea  mov     [rsp+98h+var_50], rax
0x182de5def  mov     r14, [rsp+98h+Src]
0x182de5df7  sub     r14, [rbx]
0x182de5dfa  sar     r14, 1
0x182de5dfd  lea     rcx, [rax+r14*2]
0x182de5e01  movzx   eax, byte ptr [rsp+98h+var_68]
0x182de5e06  mov     [rsp+98h+var_78], al
0x182de5e0a  mov     r9, rbx
0x182de5e0d  mov     r8, [rsp+98h+arg_20]
0x182de5e15  mov     rdx, rdi
0x182de5e18  call    ??$_Uninit_alloc_fill_n1@PEAF_KV?$allocator@F@std@@@std@@YAXPEAF_KPEBFAEAU?$_Wrap_alloc@V?$allocator@F@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<short *,unsigned __int64,std::allocator<short>>(short *,unsigned __int64,short const *,std::_Wrap_alloc<std::allocator<short>> &,std::integral_constant<bool,0>)
0x182de5e1d  mov     rdx, [rbx]; Src
0x182de5e20  mov     r8, [rsp+98h+Src]
0x182de5e28  sub     r8, rdx; Size
0x182de5e2b  mov     rcx, rsi; void *
0x182de5e2e  call    cs:__imp_memmove
0x182de5e34  mov     r8, [rbx+8]
0x182de5e38  lea     rax, [rdi+r14]
0x182de5e3c  lea     rcx, [rsi+rax*2]; void *
0x182de5e40  mov     rdx, [rsp+98h+Src]; Src
0x182de5e48  sub     r8, rdx; Size
0x182de5e4b  call    cs:__imp_memmove
0x182de5e51  nop
0x182de5e52  mov     rdx, [rbx]
0x182de5e55  mov     rax, [rbx+8]
0x182de5e59  sub     rax, rdx
0x182de5e5c  sar     rax, 1
0x182de5e5f  add     rdi, rax
0x182de5e62  test    rdx, rdx
0x182de5e65  jz      short loc_182DE5E79
0x182de5e67  mov     r8, [rbx+10h]
0x182de5e6b  sub     r8, rdx
0x182de5e6e  sar     r8, 1
0x182de5e71  mov     rcx, rbx
0x182de5e74  call    ?deallocate@?$allocator@_W@std@@QEAAXPEA_W_K@Z; std::allocator<wchar_t>::deallocate(wchar_t *,unsigned __int64)
0x182de5e79  lea     rax, [rsi+r15*2]
0x182de5e7d  mov     [rbx+10h], rax
0x182de5e81  lea     rax, [rsi+rdi*2]
0x182de5e85  mov     [rbx+8], rax
0x182de5e89  mov     [rbx], rsi
0x182de5e8c  jmp     loc_182DE5FB8
0x182de5e91  mov     rcx, rsi
0x182de5e94  sub     rcx, rax
0x182de5e97  sar     rcx, 1
0x182de5e9a  lea     r14, [r9+r9]
0x182de5e9e  cmp     rcx, rdi
0x182de5ea1  jnb     loc_182DE5F42
0x182de5ea7  mov     rcx, [rsp+98h+arg_20]
0x182de5eaf  movzx   edx, word ptr [rcx]
0x182de5eb2  mov     [rsp+98h+var_68], dx
0x182de5eb7  lea     rcx, [r14+rax]; void *
0x182de5ebb  sub     rsi, rax
0x182de5ebe  mov     r8, rsi; Size
0x182de5ec1  mov     rdx, rax; Src
0x182de5ec4  call    cs:__imp_memmove
0x182de5eca  nop
0x182de5ecb  mov     rax, [rbx+8]
0x182de5ecf  sub     rax, [rsp+98h+Src]
0x182de5ed7  sar     rax, 1
0x182de5eda  sub     rdi, rax
0x182de5edd  movzx   eax, byte ptr [rsp+98h+var_68]
0x182de5ee2  mov     [rsp+98h+var_78], al
0x182de5ee6  mov     r9, rbx
0x182de5ee9  lea     r8, [rsp+98h+var_68]
0x182de5eee  mov     rdx, rdi
0x182de5ef1  mov     rcx, [rbx+8]
0x182de5ef5  call    ??$_Uninit_alloc_fill_n1@PEAF_KV?$allocator@F@std@@@std@@YAXPEAF_KPEBFAEAU?$_Wrap_alloc@V?$allocator@F@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<short *,unsigned __int64,std::allocator<short>>(short *,unsigned __int64,short const *,std::_Wrap_alloc<std::allocator<short>> &,std::integral_constant<bool,0>)
0x182de5efa  nop
0x182de5efb  add     [rbx+8], r14
0x182de5eff  mov     rax, [rbx+8]
0x182de5f03  sub     rax, r14
0x182de5f06  mov     rdx, [rsp+98h+Src]
0x182de5f0e  xor     ecx, ecx
0x182de5f10  mov     r8, rax
0x182de5f13  sub     r8, rdx
0x182de5f16  inc     r8
0x182de5f19  shr     r8, 1
0x182de5f1c  cmp     rdx, rax
0x182de5f1f  cmova   r8, rcx
0x182de5f23  test    r8, r8
0x182de5f26  jz      loc_182DE5FB8
0x182de5f2c  movzx   eax, [rsp+98h+var_68]
0x182de5f31  mov     [rdx], ax
0x182de5f34  lea     rdx, [rdx+2]
0x182de5f38  inc     rcx
0x182de5f3b  cmp     rcx, r8
0x182de5f3e  jnz     short loc_182DE5F31
0x182de5f40  jmp     short loc_182DE5FB8
0x182de5f42  mov     rax, [rsp+98h+arg_20]
0x182de5f4a  movzx   r15d, word ptr [rax]
0x182de5f4e  mov     rdx, rsi
0x182de5f51  sub     rdx, r14; Src
0x182de5f54  mov     r8, r14; Size
0x182de5f57  mov     rcx, rsi; void *
0x182de5f5a  call    cs:__imp_memmove
0x182de5f60  lea     rax, [r14+rsi]
0x182de5f64  mov     [rbx+8], rax
0x182de5f68  imul    r8, rdi, -2
0x182de5f6c  mov     rdx, [rsp+98h+Src]; Src
0x182de5f74  sub     r8, rdx
0x182de5f77  add     r8, rsi; Size
0x182de5f7a  sub     rsi, r8
0x182de5f7d  mov     rcx, rsi; void *
0x182de5f80  call    cs:__imp_memmove
0x182de5f86  mov     r8, [rsp+98h+Src]
0x182de5f8e  lea     rax, [r14+r8]
0x182de5f92  cmp     r8, rax
0x182de5f95  jz      short loc_182DE5FB8
0x182de5f97  nop     word ptr [rax+rax+00000000h]
0x182de5fa0  mov     [r8], r15w
0x182de5fa4  add     r8, 2
0x182de5fa8  mov     rdx, [rsp+98h+Src]
0x182de5fb0  add     rdx, r14
0x182de5fb3  cmp     r8, rdx
0x182de5fb6  jnz     short loc_182DE5FA0
0x182de5fb8  mov     rcx, [rbx]
0x182de5fbb  lea     rdx, [rcx+r12*2]
0x182de5fbf  mov     [r13+0], rdx
0x182de5fc3  mov     rax, r13
0x182de5fc6  add     rsp, 60h
0x182de5fca  pop     r15
0x182de5fcc  pop     r14
0x182de5fce  pop     r13
0x182de5fd0  pop     r12
0x182de5fd2  pop     rdi
0x182de5fd3  pop     rsi
0x182de5fd4  pop     rbx
0x182de5fd5  retn
```
