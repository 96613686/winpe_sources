# std::vector<CxDateTime,std::allocator<CxDateTime>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CxDateTime>>>,unsigned __int64,CxDateTime const &)

- ea: `0x182de6b30`
- end: `0x182de6e26`
- name: `?_Insert_n@?$vector@VCxDateTime@@V?$allocator@VCxDateTime@@@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@VCxDateTime@@@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCxDateTime@@@std@@@std@@@2@_KAEBVCxDateTime@@@Z`
- size: `758`
- prototype: ``
- caller_count: `11`
- callee_count: `6`
- tags: ``

## callers

- `0x182de7860`
- `0x183088720`
- `0x183281bc0`
- `0x183282a60`
- `0x1832838c0`
- `0x183284720`
- `0x183285600`
- `0x1832864e0`
- `0x1832873d0`
- `0x183288420`
- `0x183289280`

## callees

- `0x182d76150`
- `0x182da9570`
- `0x182da9e10`
- `0x182dd1700`
- `0x182de6b30`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x182de6dcd`
- `VCRUNTIME140!memmove` at `0x182de6dcd`

## pseudocode

```c
_QWORD *__fastcall std::vector<CxDateTime>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        __int128 *a5)
{
  __int64 v9; // r8
  unsigned __int64 v10; // r14
  __int64 v11; // rsi
  __int64 v12; // rsi
  unsigned __int64 v13; // rsi
  unsigned __int64 v14; // rdx
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // r15
  __int64 v18; // r12
  unsigned __int64 v19; // rdi
  __int64 v20; // r15
  char *v21; // rcx
  char *v22; // rax
  __int128 v23; // xmm1
  char *v24; // r8
  __int128 v25; // xmm1
  struct CxVector *Pointer; // rax
  char v28; // [rsp+20h] [rbp-78h]
  int v29; // [rsp+20h] [rbp-78h]
  int v30; // [rsp+20h] [rbp-78h]
  char v31; // [rsp+20h] [rbp-78h]
  int v32; // [rsp+20h] [rbp-78h]
  char v33; // [rsp+20h] [rbp-78h]
  char v34; // [rsp+28h] [rbp-70h]
  int v35; // [rsp+28h] [rbp-70h]
  char v36; // [rsp+28h] [rbp-70h]
  char v37; // [rsp+28h] [rbp-70h]
  char v38; // [rsp+30h] [rbp-68h]
  __int128 v39; // [rsp+38h] [rbp-60h] BYREF
  CxVector *v40; // [rsp+48h] [rbp-50h]
  unsigned __int64 v41; // [rsp+50h] [rbp-48h]
  __int64 v42; // [rsp+58h] [rbp-40h]

  v42 = -2;
  v40 = a1;
  v9 = *(_QWORD *)a1;
  v10 = (unsigned __int64)&a3[-*(_QWORD *)a1];
  if ( a4 )
  {
    v11 = *((_QWORD *)a1 + 1);
    if ( (*((_QWORD *)a1 + 2) - v11) >> 4 >= a4 )
    {
      v20 = 16 * a4;
      if ( (v11 - (__int64)a3) >> 4 >= a4 )
      {
        v39 = *a5;
        v37 = v38;
        v33 = v38;
        *((_QWORD *)a1 + 1) = std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(
                                v11 - v20,
                                v11,
                                v11,
                                a1,
                                v33,
                                v37);
        memmove(&a3[16 * a4], a3, v11 + -16LL * a4 - (_QWORD)a3);
        v24 = a3;
        if ( a3 != &a3[v20] )
        {
          v25 = v39;
          do
          {
            *(_OWORD *)v24 = v25;
            v24 += 16;
          }
          while ( v24 != &a3[v20] );
        }
      }
      else
      {
        v39 = *a5;
        v36 = v38;
        v31 = v38;
        std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(
          a3,
          v11,
          &a3[v20],
          a1,
          v31,
          v36);
        try
        {
          LOBYTE(v32) = v38;
          std::_Uninit_alloc_fill_n1<CxDateTime *,unsigned __int64,std::allocator<CxDateTime>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 4),
            &v39,
            a1,
            v32);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += v20;
        v21 = (char *)(*((_QWORD *)a1 + 1) - v20);
        v22 = a3;
        if ( a3 != v21 )
        {
          v23 = v39;
          do
          {
            *(_OWORD *)v22 = v23;
            v22 += 16;
          }
          while ( v22 != v21 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 4;
      if ( 0xFFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (*((_QWORD *)a1 + 2) - v9) >> 4;
      v15 = 0;
      if ( 0xFFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v41 = v13;
      v16 = std::allocator<_SQLSatellite_TypeInfo>::allocate(a1, v13);
      v17 = v16;
      *(_QWORD *)&v39 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 4;
      try
      {
        v28 = v38;
        std::_Uninit_alloc_fill_n1<CxDateTime *,unsigned __int64,std::allocator<CxDateTime>>(
          v16 + 16 * v18,
          a4,
          a5,
          a1,
          v28);
        v34 = v38;
        LOBYTE(v29) = v38;
        std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(
          *(_QWORD *)a1,
          a3,
          v17,
          a1,
          v29,
          v34);
        LOBYTE(v35) = v38;
        LOBYTE(v30) = v38;
        std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(
          a3,
          *((_QWORD *)a1 + 1),
          v17 + 16 * (a4 + v18),
          a1,
          v30,
          v35);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v40);
        std::_Wrap_alloc<std::allocator<_SQLSatellite_TypeInfo>>::deallocate(Pointer, v39, v41);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 4) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<CxDateTime>::deallocate(a1, *(_QWORD *)a1, (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 4);
      *((_QWORD *)a1 + 2) = v17 + 16 * v13;
      *((_QWORD *)a1 + 1) = v17 + 16 * v19;
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + (v10 & 0xFFFFFFFFFFFFFFF0uLL);
  return a2;
}

```

## disassembly

```asm
0x182de6b30  mov     [rsp+Src], r8
0x182de6b35  push    rbx
0x182de6b36  push    rsi
0x182de6b37  push    rdi
0x182de6b38  push    r12
0x182de6b3a  push    r13
0x182de6b3c  push    r14
0x182de6b3e  push    r15
0x182de6b40  sub     rsp, 60h
0x182de6b44  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFEh
0x182de6b4d  mov     rdi, r9
0x182de6b50  mov     rax, r8
0x182de6b53  mov     r13, rdx
0x182de6b56  mov     rbx, rcx
0x182de6b59  mov     [rsp+98h+var_50], rcx
0x182de6b5e  mov     r8, [rcx]
0x182de6b61  mov     r14, rax
0x182de6b64  sub     r14, r8
0x182de6b67  test    r9, r9
0x182de6b6a  jz      loc_182DE6E08
0x182de6b70  mov     rdx, [rcx+10h]
0x182de6b74  mov     rsi, [rcx+8]
0x182de6b78  mov     rcx, rdx
0x182de6b7b  sub     rcx, rsi
0x182de6b7e  sar     rcx, 4
0x182de6b82  cmp     rcx, r9
0x182de6b85  jnb     loc_182DE6CC4
0x182de6b8b  sub     rsi, r8
0x182de6b8e  sar     rsi, 4
0x182de6b92  mov     r9, 0FFFFFFFFFFFFFFFh
0x182de6b9c  mov     rax, r9
0x182de6b9f  sub     rax, rsi
0x182de6ba2  cmp     rax, rdi
0x182de6ba5  jnb     short loc_182DE6BB0
0x182de6ba7  mov     rcx, rbx
0x182de6baa  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x182de6bb0  add     rsi, rdi
0x182de6bb3  sub     rdx, r8
0x182de6bb6  sar     rdx, 4
0x182de6bba  mov     rax, rdx
0x182de6bbd  shr     rax, 1
0x182de6bc0  sub     r9, rax
0x182de6bc3  add     rax, rdx
0x182de6bc6  xor     ecx, ecx
0x182de6bc8  cmp     r9, rdx
0x182de6bcb  cmovnb  rcx, rax
0x182de6bcf  cmp     rcx, rsi
0x182de6bd2  cmovnb  rsi, rcx
0x182de6bd6  mov     [rsp+98h+var_48], rsi
0x182de6bdb  mov     rdx, rsi
0x182de6bde  mov     rcx, rbx
0x182de6be1  call    ?allocate@?$allocator@U_SQLSatellite_TypeInfo@@@std@@QEAAPEAU_SQLSatellite_TypeInfo@@_K@Z; std::allocator<_SQLSatellite_TypeInfo>::allocate(unsigned __int64)
0x182de6be6  mov     r15, rax
0x182de6be9  mov     qword ptr [rsp+98h+var_60], rax
0x182de6bee  mov     r12, [rsp+98h+Src]
0x182de6bf6  sub     r12, [rbx]
0x182de6bf9  sar     r12, 4
0x182de6bfd  mov     rcx, r12
0x182de6c00  shl     rcx, 4
0x182de6c04  add     rcx, rax
0x182de6c07  movzx   eax, [rsp+98h+var_68]
0x182de6c0c  mov     [rsp+98h+var_78], al
0x182de6c10  mov     r9, rbx
0x182de6c13  mov     r8, [rsp+98h+arg_20]
0x182de6c1b  mov     rdx, rdi
0x182de6c1e  call    ??$_Uninit_alloc_fill_n1@PEAVCxDateTime@@_KV?$allocator@VCxDateTime@@@std@@@std@@YAXPEAVCxDateTime@@_KPEBV1@AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<CxDateTime *,unsigned __int64,std::allocator<CxDateTime>>(CxDateTime *,unsigned __int64,CxDateTime const *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::integral_constant<bool,0>)
0x182de6c23  movzx   eax, [rsp+98h+var_68]
0x182de6c28  mov     [rsp+98h+var_70], al
0x182de6c2c  movzx   eax, [rsp+98h+var_68]
0x182de6c31  mov     [rsp+98h+var_78], al
0x182de6c35  mov     r9, rbx
0x182de6c38  mov     r8, r15
0x182de6c3b  mov     rdx, [rsp+98h+Src]
0x182de6c43  mov     rcx, [rbx]
0x182de6c46  call    ??$_Uninitialized_move_al_unchecked1@PEAVCxDateTime@@PEAV1@V?$allocator@VCxDateTime@@@std@@@std@@YAPEAVCxDateTime@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(CxDateTime *,CxDateTime *,CxDateTime *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x182de6c4b  lea     r8, [rdi+r12]
0x182de6c4f  shl     r8, 4
0x182de6c53  add     r8, r15
0x182de6c56  movzx   eax, [rsp+98h+var_68]
0x182de6c5b  mov     [rsp+98h+var_70], al
0x182de6c5f  movzx   eax, [rsp+98h+var_68]
0x182de6c64  mov     [rsp+98h+var_78], al
0x182de6c68  mov     r9, rbx
0x182de6c6b  mov     rdx, [rbx+8]
0x182de6c6f  mov     rcx, [rsp+98h+Src]
0x182de6c77  call    ??$_Uninitialized_move_al_unchecked1@PEAVCxDateTime@@PEAV1@V?$allocator@VCxDateTime@@@std@@@std@@YAPEAVCxDateTime@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(CxDateTime *,CxDateTime *,CxDateTime *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x182de6c7c  nop
0x182de6c7d  mov     rdx, [rbx]
0x182de6c80  mov     rax, [rbx+8]
0x182de6c84  sub     rax, rdx
0x182de6c87  sar     rax, 4
0x182de6c8b  add     rdi, rax
0x182de6c8e  test    rdx, rdx
0x182de6c91  jz      short loc_182DE6CA6
0x182de6c93  mov     r8, [rbx+10h]
0x182de6c97  sub     r8, rdx
0x182de6c9a  sar     r8, 4
0x182de6c9e  mov     rcx, rbx
0x182de6ca1  call    ?deallocate@?$allocator@VCxDateTime@@@std@@QEAAXPEAVCxDateTime@@_K@Z; std::allocator<CxDateTime>::deallocate(CxDateTime *,unsigned __int64)
0x182de6ca6  shl     rsi, 4
0x182de6caa  add     rsi, r15
0x182de6cad  mov     [rbx+10h], rsi
0x182de6cb1  shl     rdi, 4
0x182de6cb5  add     rdi, r15
0x182de6cb8  mov     [rbx+8], rdi
0x182de6cbc  mov     [rbx], r15
0x182de6cbf  jmp     loc_182DE6E08
0x182de6cc4  mov     rcx, rsi
0x182de6cc7  sub     rcx, rax
0x182de6cca  sar     rcx, 4
0x182de6cce  mov     r15, rdi
0x182de6cd1  mov     r9, rbx
0x182de6cd4  mov     rdx, rsi
0x182de6cd7  shl     r15, 4
0x182de6cdb  cmp     rcx, rdi
0x182de6cde  jnb     loc_182DE6D81
0x182de6ce4  mov     rcx, [rsp+98h+arg_20]
0x182de6cec  movups  xmm0, xmmword ptr [rcx]
0x182de6cef  movups  [rsp+98h+var_60], xmm0
0x182de6cf4  lea     r8, [r15+rax]
0x182de6cf8  movzx   ecx, [rsp+98h+var_68]
0x182de6cfd  mov     [rsp+98h+var_70], cl
0x182de6d01  movzx   ecx, [rsp+98h+var_68]
0x182de6d06  mov     [rsp+98h+var_78], cl
0x182de6d0a  mov     rcx, rax
0x182de6d0d  call    ??$_Uninitialized_move_al_unchecked1@PEAVCxDateTime@@PEAV1@V?$allocator@VCxDateTime@@@std@@@std@@YAPEAVCxDateTime@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(CxDateTime *,CxDateTime *,CxDateTime *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x182de6d12  nop
0x182de6d13  mov     rax, [rbx+8]
0x182de6d17  sub     rax, [rsp+98h+Src]
0x182de6d1f  sar     rax, 4
0x182de6d23  sub     rdi, rax
0x182de6d26  movzx   eax, [rsp+98h+var_68]
0x182de6d2b  mov     [rsp+98h+var_78], al
0x182de6d2f  mov     r9, rbx
0x182de6d32  lea     r8, [rsp+98h+var_60]
0x182de6d37  mov     rdx, rdi
0x182de6d3a  mov     rcx, [rbx+8]
0x182de6d3e  call    ??$_Uninit_alloc_fill_n1@PEAVCxDateTime@@_KV?$allocator@VCxDateTime@@@std@@@std@@YAXPEAVCxDateTime@@_KPEBV1@AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<CxDateTime *,unsigned __int64,std::allocator<CxDateTime>>(CxDateTime *,unsigned __int64,CxDateTime const *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::integral_constant<bool,0>)
0x182de6d43  nop
0x182de6d44  add     [rbx+8], r15
0x182de6d48  mov     rcx, [rbx+8]
0x182de6d4c  sub     rcx, r15
0x182de6d4f  mov     rax, [rsp+98h+Src]
0x182de6d57  cmp     rax, rcx
0x182de6d5a  jz      loc_182DE6E08
0x182de6d60  movups  xmm1, [rsp+98h+var_60]
0x182de6d65  nop     word ptr [rax+rax+00000000h]
0x182de6d70  movups  xmmword ptr [rax], xmm1
0x182de6d73  add     rax, 10h
0x182de6d77  cmp     rax, rcx
0x182de6d7a  jnz     short loc_182DE6D70
0x182de6d7c  jmp     loc_182DE6E08
0x182de6d81  mov     rax, [rsp+98h+arg_20]
0x182de6d89  movups  xmm0, xmmword ptr [rax]
0x182de6d8c  movups  [rsp+98h+var_60], xmm0
0x182de6d91  mov     rcx, rsi
0x182de6d94  sub     rcx, r15
0x182de6d97  movzx   eax, [rsp+98h+var_68]
0x182de6d9c  mov     [rsp+98h+var_70], al
0x182de6da0  movzx   eax, [rsp+98h+var_68]
0x182de6da5  mov     [rsp+98h+var_78], al
0x182de6da9  mov     r8, rsi
0x182de6dac  call    ??$_Uninitialized_move_al_unchecked1@PEAVCxDateTime@@PEAV1@V?$allocator@VCxDateTime@@@std@@@std@@YAPEAVCxDateTime@@PEAV1@00AEAU?$_Wrap_alloc@V?$allocator@VCxDateTime@@@std@@@0@U_General_ptr_iterator_tag@0@U_Any_tag@0@@Z; std::_Uninitialized_move_al_unchecked1<CxDateTime *,CxDateTime *,std::allocator<CxDateTime>>(CxDateTime *,CxDateTime *,CxDateTime *,std::_Wrap_alloc<std::allocator<CxDateTime>> &,std::_General_ptr_iterator_tag,std::_Any_tag)
0x182de6db1  mov     [rbx+8], rax
0x182de6db5  imul    r8, rdi, -10h
0x182de6db9  mov     rdx, [rsp+98h+Src]; Src
0x182de6dc1  sub     r8, rdx
0x182de6dc4  add     r8, rsi; Size
0x182de6dc7  sub     rsi, r8
0x182de6dca  mov     rcx, rsi; void *
0x182de6dcd  call    cs:__imp_memmove
0x182de6dd3  mov     r8, [rsp+98h+Src]
0x182de6ddb  lea     rax, [r15+r8]
0x182de6ddf  cmp     r8, rax
0x182de6de2  jz      short loc_182DE6E08
0x182de6de4  movups  xmm1, [rsp+98h+var_60]
0x182de6de9  nop     dword ptr [rax+00000000h]
0x182de6df0  movups  xmmword ptr [r8], xmm1
0x182de6df4  add     r8, 10h
0x182de6df8  mov     rdx, [rsp+98h+Src]
0x182de6e00  add     rdx, r15
0x182de6e03  cmp     r8, rdx
0x182de6e06  jnz     short loc_182DE6DF0
0x182de6e08  and     r14, 0FFFFFFFFFFFFFFF0h
0x182de6e0c  add     r14, [rbx]
0x182de6e0f  mov     [r13+0], r14
0x182de6e13  mov     rax, r13
0x182de6e16  add     rsp, 60h
0x182de6e1a  pop     r15
0x182de6e1c  pop     r14
0x182de6e1e  pop     r13
0x182de6e20  pop     r12
0x182de6e22  pop     rdi
0x182de6e23  pop     rsi
0x182de6e24  pop     rbx
0x182de6e25  retn
```
