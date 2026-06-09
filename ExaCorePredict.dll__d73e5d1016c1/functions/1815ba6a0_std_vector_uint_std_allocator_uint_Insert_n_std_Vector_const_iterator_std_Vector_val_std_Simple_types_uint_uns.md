# std::vector<uint,std::allocator<uint>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<uint>>>,unsigned __int64,uint const &)

- ea: `0x1815ba6a0`
- end: `0x1815ba955`
- name: `?_Insert_n@?$vector@IV?$allocator@I@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@I@std@@@std@@@2@_KAEBI@Z`
- size: `693`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: ``

## callers

- `0x1815bbc60`
- `0x1830873a0`
- `0x183282600`
- `0x183283480`
- `0x1832842e0`
- `0x183285170`
- `0x183286050`
- `0x183286f30`
- `0x183287f60`
- `0x183288e40`
- `0x183289cc0`
- `0x1832a0570`
- `0x1832a0930`
- `0x1832a0cf0`
- `0x1832a10a0`
- `0x1832a1490`
- `0x1832a1880`
- `0x1832a1cb0`
- `0x1832a2110`
- `0x1832a24d0`

## callees

- `0x1815adec0`
- `0x1815ba6a0`
- `0x182da94f0`
- `0x182da9d90`
- `0x183066770`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815ba7a3`
- `VCRUNTIME140!memmove` at `0x1815ba7c0`
- `VCRUNTIME140!memmove` at `0x1815ba83e`
- `VCRUNTIME140!memmove` at `0x1815ba8d7`
- `VCRUNTIME140!memmove` at `0x1815ba8fd`
- `VCRUNTIME140!memmove` at `0x1815ba7a3`
- `VCRUNTIME140!memmove` at `0x1815ba7c0`
- `VCRUNTIME140!memmove` at `0x1815ba83e`
- `VCRUNTIME140!memmove` at `0x1815ba8d7`
- `VCRUNTIME140!memmove` at `0x1815ba8fd`

## pseudocode

```c
_QWORD *__fastcall std::vector<unsigned int>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        int *a5)
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
  int v24; // eax
  int v25; // r15d
  char *i; // r8
  struct CxVector *Pointer; // rax
  char v29; // [rsp+20h] [rbp-78h]
  char v30; // [rsp+20h] [rbp-78h]
  char v31; // [rsp+30h] [rbp-68h]
  CxVector *v32; // [rsp+38h] [rbp-60h] BYREF
  unsigned __int64 v33; // [rsp+40h] [rbp-58h]
  __int64 v34; // [rsp+48h] [rbp-50h]
  __int64 v35; // [rsp+50h] [rbp-48h]

  v35 = -2;
  v32 = a1;
  v9 = *(_BYTE **)a1;
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 2;
  if ( a4 )
  {
    v11 = (char *)*((_QWORD *)a1 + 1);
    if ( (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v11) >> 2 >= a4 )
    {
      v20 = 4 * a4;
      if ( (v11 - a3) >> 2 >= a4 )
      {
        v25 = *a5;
        memmove(v11, &v11[-v20], 4 * a4);
        *((_QWORD *)a1 + 1) = &v11[v20];
        memmove(&a3[4 * a4], a3, (size_t)&v11[-4LL * a4 - (_QWORD)a3]);
        for ( i = a3; i != &a3[v20]; i += 4 )
          *(_DWORD *)i = v25;
      }
      else
      {
        LODWORD(v32) = *a5;
        memmove(&a3[v20], a3, v11 - a3);
        try
        {
          v30 = v31;
          std::_Uninit_alloc_fill_n1<unsigned int *,unsigned __int64,std::allocator<unsigned int>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 2),
            &v32,
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
        v23 = (unsigned __int64)(*((_QWORD *)a1 + 1) - v20 - (_QWORD)a3 + 3) >> 2;
        if ( (unsigned __int64)a3 > *((_QWORD *)a1 + 1) - v20 )
          v23 = 0;
        if ( v23 )
        {
          v24 = (int)v32;
          do
          {
            *(_DWORD *)v21 = v24;
            v21 += 4;
            ++v22;
          }
          while ( v22 != v23 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 2;
      if ( 0x3FFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v9) >> 2;
      v15 = 0;
      if ( 0x3FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v33 = v13;
      v16 = std::allocator<int>::allocate(a1, v13);
      v17 = (char *)v16;
      v34 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 2;
      try
      {
        v29 = v31;
        std::_Uninit_alloc_fill_n1<unsigned int *,unsigned __int64,std::allocator<unsigned int>>(
          v16 + 4 * v18,
          a4,
          a5,
          a1,
          v29);
        memmove(v17, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[4 * a4 + 4 * v18], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v32);
        std::_Wrap_alloc<std::allocator<float>>::deallocate(Pointer, v34, v33);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 2) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<float>::deallocate(a1, *(_QWORD *)a1, (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 2);
      *((_QWORD *)a1 + 2) = &v17[4 * v13];
      *((_QWORD *)a1 + 1) = &v17[4 * v19];
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 4 * v10;
  return a2;
}

```

## disassembly

```asm
0x1815ba6a0  mov     [rsp+Src], r8
0x1815ba6a5  push    rbx
0x1815ba6a6  push    rsi
0x1815ba6a7  push    rdi
0x1815ba6a8  push    r12
0x1815ba6aa  push    r13
0x1815ba6ac  push    r14
0x1815ba6ae  push    r15
0x1815ba6b0  sub     rsp, 60h
0x1815ba6b4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1815ba6bd  mov     rdi, r9
0x1815ba6c0  mov     rax, r8
0x1815ba6c3  mov     r13, rdx
0x1815ba6c6  mov     rbx, rcx
0x1815ba6c9  mov     [rsp+98h+var_60], rcx
0x1815ba6ce  mov     r8, [rcx]
0x1815ba6d1  mov     r12, rax
0x1815ba6d4  sub     r12, r8
0x1815ba6d7  sar     r12, 2
0x1815ba6db  test    r9, r9
0x1815ba6de  jz      loc_1815BA937
0x1815ba6e4  mov     rsi, [rcx+8]
0x1815ba6e8  mov     rdx, [rcx+10h]
0x1815ba6ec  mov     rcx, rdx
0x1815ba6ef  sub     rcx, rsi
0x1815ba6f2  sar     rcx, 2
0x1815ba6f6  cmp     rcx, r9
0x1815ba6f9  jnb     loc_1815BA808
0x1815ba6ff  sub     rsi, r8
0x1815ba702  sar     rsi, 2
0x1815ba706  mov     r9, 3FFFFFFFFFFFFFFFh
0x1815ba710  mov     rax, r9
0x1815ba713  sub     rax, rsi
0x1815ba716  cmp     rax, rdi
0x1815ba719  jnb     short loc_1815BA724
0x1815ba71b  mov     rcx, rbx
0x1815ba71e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1815ba724  lea     r15, [rdi+rsi]
0x1815ba728  sub     rdx, r8
0x1815ba72b  sar     rdx, 2
0x1815ba72f  mov     rax, rdx
0x1815ba732  shr     rax, 1
0x1815ba735  sub     r9, rax
0x1815ba738  add     rax, rdx
0x1815ba73b  xor     ecx, ecx
0x1815ba73d  cmp     r9, rdx
0x1815ba740  cmovnb  rcx, rax
0x1815ba744  cmp     rcx, r15
0x1815ba747  cmovnb  r15, rcx
0x1815ba74b  mov     [rsp+98h+var_58], r15
0x1815ba750  mov     rdx, r15
0x1815ba753  mov     rcx, rbx
0x1815ba756  call    ?allocate@?$allocator@H@std@@QEAAPEAH_K@Z; std::allocator<int>::allocate(unsigned __int64)
0x1815ba75b  mov     rsi, rax
0x1815ba75e  mov     [rsp+98h+var_50], rax
0x1815ba763  mov     r14, [rsp+98h+Src]
0x1815ba76b  sub     r14, [rbx]
0x1815ba76e  sar     r14, 2
0x1815ba772  lea     rcx, [rax+r14*4]
0x1815ba776  movzx   eax, [rsp+98h+var_68]
0x1815ba77b  mov     [rsp+98h+var_78], al
0x1815ba77f  mov     r9, rbx
0x1815ba782  mov     r8, [rsp+98h+arg_20]
0x1815ba78a  mov     rdx, rdi
0x1815ba78d  call    ??$_Uninit_alloc_fill_n1@PEAI_KV?$allocator@I@std@@@std@@YAXPEAI_KPEBIAEAU?$_Wrap_alloc@V?$allocator@I@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<uint *,unsigned __int64,std::allocator<uint>>(uint *,unsigned __int64,uint const *,std::_Wrap_alloc<std::allocator<uint>> &,std::integral_constant<bool,0>)
0x1815ba792  mov     rdx, [rbx]; Src
0x1815ba795  mov     r8, [rsp+98h+Src]
0x1815ba79d  sub     r8, rdx; Size
0x1815ba7a0  mov     rcx, rsi; void *
0x1815ba7a3  call    cs:__imp_memmove
0x1815ba7a9  mov     r8, [rbx+8]
0x1815ba7ad  lea     rax, [rdi+r14]
0x1815ba7b1  lea     rcx, [rsi+rax*4]; void *
0x1815ba7b5  mov     rdx, [rsp+98h+Src]; Src
0x1815ba7bd  sub     r8, rdx; Size
0x1815ba7c0  call    cs:__imp_memmove
0x1815ba7c6  nop
0x1815ba7c7  mov     rdx, [rbx]
0x1815ba7ca  mov     rax, [rbx+8]
0x1815ba7ce  sub     rax, rdx
0x1815ba7d1  sar     rax, 2
0x1815ba7d5  add     rdi, rax
0x1815ba7d8  test    rdx, rdx
0x1815ba7db  jz      short loc_1815BA7F0
0x1815ba7dd  mov     r8, [rbx+10h]
0x1815ba7e1  sub     r8, rdx
0x1815ba7e4  sar     r8, 2
0x1815ba7e8  mov     rcx, rbx
0x1815ba7eb  call    ?deallocate@?$allocator@M@std@@QEAAXPEAM_K@Z; std::allocator<float>::deallocate(float *,unsigned __int64)
0x1815ba7f0  lea     rax, [rsi+r15*4]
0x1815ba7f4  mov     [rbx+10h], rax
0x1815ba7f8  lea     rax, [rsi+rdi*4]
0x1815ba7fc  mov     [rbx+8], rax
0x1815ba800  mov     [rbx], rsi
0x1815ba803  jmp     loc_1815BA937
0x1815ba808  mov     rcx, rsi
0x1815ba80b  sub     rcx, rax
0x1815ba80e  sar     rcx, 2
0x1815ba812  lea     r14, ds:0[r9*4]
0x1815ba81a  cmp     rcx, rdi
0x1815ba81d  jnb     loc_1815BA8C0
0x1815ba823  mov     rcx, [rsp+98h+arg_20]
0x1815ba82b  mov     edx, [rcx]
0x1815ba82d  mov     dword ptr [rsp+98h+var_60], edx
0x1815ba831  lea     rcx, [r14+rax]; void *
0x1815ba835  sub     rsi, rax
0x1815ba838  mov     r8, rsi; Size
0x1815ba83b  mov     rdx, rax; Src
0x1815ba83e  call    cs:__imp_memmove
0x1815ba844  nop
0x1815ba845  mov     rax, [rbx+8]
0x1815ba849  sub     rax, [rsp+98h+Src]
0x1815ba851  sar     rax, 2
0x1815ba855  sub     rdi, rax
0x1815ba858  movzx   eax, [rsp+98h+var_68]
0x1815ba85d  mov     [rsp+98h+var_78], al
0x1815ba861  mov     r9, rbx
0x1815ba864  lea     r8, [rsp+98h+var_60]
0x1815ba869  mov     rdx, rdi
0x1815ba86c  mov     rcx, [rbx+8]
0x1815ba870  call    ??$_Uninit_alloc_fill_n1@PEAI_KV?$allocator@I@std@@@std@@YAXPEAI_KPEBIAEAU?$_Wrap_alloc@V?$allocator@I@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<uint *,unsigned __int64,std::allocator<uint>>(uint *,unsigned __int64,uint const *,std::_Wrap_alloc<std::allocator<uint>> &,std::integral_constant<bool,0>)
0x1815ba875  nop
0x1815ba876  add     [rbx+8], r14
0x1815ba87a  mov     rax, [rbx+8]
0x1815ba87e  sub     rax, r14
0x1815ba881  mov     rdx, [rsp+98h+Src]
0x1815ba889  xor     ecx, ecx
0x1815ba88b  mov     r8, rax
0x1815ba88e  sub     r8, rdx
0x1815ba891  add     r8, 3
0x1815ba895  shr     r8, 2
0x1815ba899  cmp     rdx, rax
0x1815ba89c  cmova   r8, rcx
0x1815ba8a0  test    r8, r8
0x1815ba8a3  jz      loc_1815BA937
0x1815ba8a9  mov     eax, dword ptr [rsp+98h+var_60]
0x1815ba8ad  nop     dword ptr [rax]
0x1815ba8b0  mov     [rdx], eax
0x1815ba8b2  lea     rdx, [rdx+4]
0x1815ba8b6  inc     rcx
0x1815ba8b9  cmp     rcx, r8
0x1815ba8bc  jnz     short loc_1815BA8B0
0x1815ba8be  jmp     short loc_1815BA937
0x1815ba8c0  mov     rax, [rsp+98h+arg_20]
0x1815ba8c8  mov     r15d, [rax]
0x1815ba8cb  mov     rdx, rsi
0x1815ba8ce  sub     rdx, r14; Src
0x1815ba8d1  mov     r8, r14; Size
0x1815ba8d4  mov     rcx, rsi; void *
0x1815ba8d7  call    cs:__imp_memmove
0x1815ba8dd  lea     rax, [r14+rsi]
0x1815ba8e1  mov     [rbx+8], rax
0x1815ba8e5  imul    r8, rdi, -4
0x1815ba8e9  mov     rdx, [rsp+98h+Src]; Src
0x1815ba8f1  sub     r8, rdx
0x1815ba8f4  add     r8, rsi; Size
0x1815ba8f7  sub     rsi, r8
0x1815ba8fa  mov     rcx, rsi; void *
0x1815ba8fd  call    cs:__imp_memmove
0x1815ba903  mov     r8, [rsp+98h+Src]
0x1815ba90b  lea     rax, [r14+r8]
0x1815ba90f  cmp     r8, rax
0x1815ba912  jz      short loc_1815BA937
0x1815ba914  nop     dword ptr [rax+00h]
0x1815ba918  nop     dword ptr [rax+rax+00000000h]
0x1815ba920  mov     [r8], r15d
0x1815ba923  add     r8, 4
0x1815ba927  mov     rdx, [rsp+98h+Src]
0x1815ba92f  add     rdx, r14
0x1815ba932  cmp     r8, rdx
0x1815ba935  jnz     short loc_1815BA920
0x1815ba937  mov     rcx, [rbx]
0x1815ba93a  lea     rdx, [rcx+r12*4]
0x1815ba93e  mov     [r13+0], rdx
0x1815ba942  mov     rax, r13
0x1815ba945  add     rsp, 60h
0x1815ba949  pop     r15
0x1815ba94b  pop     r14
0x1815ba94d  pop     r13
0x1815ba94f  pop     r12
0x1815ba951  pop     rdi
0x1815ba952  pop     rsi
0x1815ba953  pop     rbx
0x1815ba954  retn
```
