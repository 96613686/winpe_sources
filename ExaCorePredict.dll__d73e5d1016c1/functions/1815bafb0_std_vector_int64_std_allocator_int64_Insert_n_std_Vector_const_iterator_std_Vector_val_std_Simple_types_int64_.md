# std::vector<__int64,std::allocator<__int64>>::_Insert_n(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<__int64>>>,unsigned __int64,__int64 const &)

- ea: `0x1815bafb0`
- end: `0x1815bb265`
- name: `?_Insert_n@?$vector@_JV?$allocator@_J@std@@@std@@IEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@_J@std@@@std@@@2@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_J@std@@@std@@@2@_KAEB_J@Z`
- size: `693`
- prototype: ``
- caller_count: `20`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x182de79f0`
- `0x183088b60`
- `0x183282200`
- `0x183283090`
- `0x183283ef0`
- `0x183284d60`
- `0x183285c40`
- `0x183286b20`
- `0x183287ae0`
- `0x183288a50`
- `0x1832898d0`
- `0x1832a0660`
- `0x1832a0a10`
- `0x1832a0dd0`
- `0x1832a1190`
- `0x1832a1580`
- `0x1832a1970`
- `0x1832a1dc0`
- `0x1832a21f0`
- `0x1832a25b0`

## callees

- `0x1815adf80`
- `0x1815bafb0`
- `0x1815bbf10`
- `0x183066770`
- `0x183103b60`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x1815bb0b3`
- `VCRUNTIME140!memmove` at `0x1815bb0d0`
- `VCRUNTIME140!memmove` at `0x1815bb150`
- `VCRUNTIME140!memmove` at `0x1815bb1e8`
- `VCRUNTIME140!memmove` at `0x1815bb20e`
- `VCRUNTIME140!memmove` at `0x1815bb0b3`
- `VCRUNTIME140!memmove` at `0x1815bb0d0`
- `VCRUNTIME140!memmove` at `0x1815bb150`
- `VCRUNTIME140!memmove` at `0x1815bb1e8`
- `VCRUNTIME140!memmove` at `0x1815bb20e`

## pseudocode

```c
_QWORD *__fastcall std::vector<__int64>::_Insert_n(
        CxVector *a1,
        _QWORD *a2,
        char *a3,
        unsigned __int64 a4,
        CxVector **a5)
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
  CxVector **v21; // rdx
  __int64 v22; // rcx
  unsigned __int64 v23; // r8
  CxVector *v24; // rax
  CxVector *v25; // r15
  CxVector **v26; // r8
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
  v10 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
  if ( a4 )
  {
    v11 = (char *)*((_QWORD *)a1 + 1);
    if ( (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v11) >> 3 >= a4 )
    {
      v20 = 8 * a4;
      if ( (v11 - a3) >> 3 >= a4 )
      {
        v25 = *a5;
        memmove(v11, &v11[-v20], 8 * a4);
        *((_QWORD *)a1 + 1) = &v11[v20];
        memmove(&a3[8 * a4], a3, (size_t)&v11[-8LL * a4 - (_QWORD)a3]);
        v26 = (CxVector **)a3;
        if ( a3 != &a3[v20] )
        {
          do
            *v26++ = v25;
          while ( v26 != (CxVector **)&a3[v20] );
        }
      }
      else
      {
        v32 = *a5;
        memmove(&a3[v20], a3, v11 - a3);
        try
        {
          v30 = v31;
          std::_Uninit_alloc_fill_n1<__int64 *,unsigned __int64,std::allocator<__int64>>(
            *((_QWORD *)a1 + 1),
            a4 - ((__int64)(*((_QWORD *)a1 + 1) - (_QWORD)a3) >> 3),
            &v32,
            a1,
            v30);
        }
        catch ( ... )
        {
          throw;
        }
        *((_QWORD *)a1 + 1) += v20;
        v21 = (CxVector **)a3;
        v22 = 0;
        v23 = (unsigned __int64)(*((_QWORD *)a1 + 1) - v20 - (_QWORD)a3 + 7) >> 3;
        if ( (unsigned __int64)a3 > *((_QWORD *)a1 + 1) - v20 )
          v23 = 0;
        if ( v23 )
        {
          v24 = v32;
          do
          {
            *v21++ = v24;
            ++v22;
          }
          while ( v22 != v23 );
        }
      }
    }
    else
    {
      v12 = (v11 - v9) >> 3;
      if ( 0x1FFFFFFFFFFFFFFFLL - v12 < a4 )
        std::vector<VarBase>::_Xlen(a1);
      v13 = a4 + v12;
      v14 = (__int64)(*((_QWORD *)a1 + 2) - (_QWORD)v9) >> 3;
      v15 = 0;
      if ( 0x1FFFFFFFFFFFFFFFLL - (v14 >> 1) >= v14 )
        v15 = v14 + (v14 >> 1);
      if ( v15 >= v13 )
        v13 = v15;
      v33 = v13;
      v16 = std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(
              a1,
              v13);
      v17 = (char *)v16;
      v34 = v16;
      v18 = (__int64)&a3[-*(_QWORD *)a1] >> 3;
      try
      {
        v29 = v31;
        std::_Uninit_alloc_fill_n1<__int64 *,unsigned __int64,std::allocator<__int64>>(v16 + 8 * v18, a4, a5, a1, v29);
        memmove(v17, *(const void **)a1, (size_t)&a3[-*(_QWORD *)a1]);
        memmove(&v17[8 * a4 + 8 * v18], a3, *((_QWORD *)a1 + 1) - (_QWORD)a3);
      }
      catch ( ... )
      {
        Pointer = CxVector::GetPointer(v32);
        std::_Wrap_alloc<std::allocator<CxWrapper<CxVarDescriptor>>>::deallocate(Pointer, v34, v33);
        throw;
      }
      v19 = ((__int64)(*((_QWORD *)a1 + 1) - *(_QWORD *)a1) >> 3) + a4;
      if ( *(_QWORD *)a1 )
        std::allocator<CxWrapper<CxComputation>>::deallocate(
          a1,
          *(_QWORD *)a1,
          (__int64)(*((_QWORD *)a1 + 2) - *(_QWORD *)a1) >> 3);
      *((_QWORD *)a1 + 2) = &v17[8 * v13];
      *((_QWORD *)a1 + 1) = &v17[8 * v19];
      *(_QWORD *)a1 = v17;
    }
  }
  *a2 = *(_QWORD *)a1 + 8 * v10;
  return a2;
}

```

## disassembly

```asm
0x1815bafb0  mov     [rsp+Src], r8
0x1815bafb5  push    rbx
0x1815bafb6  push    rsi
0x1815bafb7  push    rdi
0x1815bafb8  push    r12
0x1815bafba  push    r13
0x1815bafbc  push    r14
0x1815bafbe  push    r15
0x1815bafc0  sub     rsp, 60h
0x1815bafc4  mov     [rsp+98h+var_48], 0FFFFFFFFFFFFFFFEh
0x1815bafcd  mov     rdi, r9
0x1815bafd0  mov     rax, r8
0x1815bafd3  mov     r13, rdx
0x1815bafd6  mov     rbx, rcx
0x1815bafd9  mov     [rsp+98h+var_60], rcx
0x1815bafde  mov     r8, [rcx]
0x1815bafe1  mov     r12, rax
0x1815bafe4  sub     r12, r8
0x1815bafe7  sar     r12, 3
0x1815bafeb  test    r9, r9
0x1815bafee  jz      loc_1815BB247
0x1815baff4  mov     rsi, [rcx+8]
0x1815baff8  mov     rdx, [rcx+10h]
0x1815baffc  mov     rcx, rdx
0x1815bafff  sub     rcx, rsi
0x1815bb002  sar     rcx, 3
0x1815bb006  cmp     rcx, r9
0x1815bb009  jnb     loc_1815BB118
0x1815bb00f  sub     rsi, r8
0x1815bb012  sar     rsi, 3
0x1815bb016  mov     r9, 1FFFFFFFFFFFFFFFh
0x1815bb020  mov     rax, r9
0x1815bb023  sub     rax, rsi
0x1815bb026  cmp     rax, rdi
0x1815bb029  jnb     short loc_1815BB034
0x1815bb02b  mov     rcx, rbx
0x1815bb02e  call    ?_Xlen@?$vector@VVarBase@@V?$allocator@VVarBase@@@std@@@std@@IEBAXXZ; std::vector<VarBase>::_Xlen(void)
0x1815bb034  lea     r15, [rdi+rsi]
0x1815bb038  sub     rdx, r8
0x1815bb03b  sar     rdx, 3
0x1815bb03f  mov     rax, rdx
0x1815bb042  shr     rax, 1
0x1815bb045  sub     r9, rax
0x1815bb048  add     rax, rdx
0x1815bb04b  xor     ecx, ecx
0x1815bb04d  cmp     r9, rdx
0x1815bb050  cmovnb  rcx, rax
0x1815bb054  cmp     rcx, r15
0x1815bb057  cmovnb  r15, rcx
0x1815bb05b  mov     [rsp+98h+var_58], r15
0x1815bb060  mov     rdx, r15
0x1815bb063  mov     rcx, rbx
0x1815bb066  call    ?allocate@?$allocator@V?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@std@@@std@@QEAAPEAV?$_List_unchecked_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBVCacheKey@@V?$shared_ptr@VContext@MRSPredict@@@std@@@std@@@std@@@std@@@2@_K@Z; std::allocator<std::_List_unchecked_iterator<std::_List_val<std::_List_simple_types<std::pair<CacheKey const,std::shared_ptr<MRSPredict::Context>>>>>>::allocate(unsigned __int64)
0x1815bb06b  mov     rsi, rax
0x1815bb06e  mov     [rsp+98h+var_50], rax
0x1815bb073  mov     r14, [rsp+98h+Src]
0x1815bb07b  sub     r14, [rbx]
0x1815bb07e  sar     r14, 3
0x1815bb082  lea     rcx, [rax+r14*8]
0x1815bb086  movzx   eax, [rsp+98h+var_68]
0x1815bb08b  mov     [rsp+98h+var_78], al
0x1815bb08f  mov     r9, rbx
0x1815bb092  mov     r8, [rsp+98h+arg_20]
0x1815bb09a  mov     rdx, rdi
0x1815bb09d  call    ??$_Uninit_alloc_fill_n1@PEA_J_KV?$allocator@_J@std@@@std@@YAXPEA_J_KPEB_JAEAU?$_Wrap_alloc@V?$allocator@_J@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<__int64 *,unsigned __int64,std::allocator<__int64>>(__int64 *,unsigned __int64,__int64 const *,std::_Wrap_alloc<std::allocator<__int64>> &,std::integral_constant<bool,0>)
0x1815bb0a2  mov     rdx, [rbx]; Src
0x1815bb0a5  mov     r8, [rsp+98h+Src]
0x1815bb0ad  sub     r8, rdx; Size
0x1815bb0b0  mov     rcx, rsi; void *
0x1815bb0b3  call    cs:__imp_memmove
0x1815bb0b9  mov     r8, [rbx+8]
0x1815bb0bd  lea     rax, [rdi+r14]
0x1815bb0c1  lea     rcx, [rsi+rax*8]; void *
0x1815bb0c5  mov     rdx, [rsp+98h+Src]; Src
0x1815bb0cd  sub     r8, rdx; Size
0x1815bb0d0  call    cs:__imp_memmove
0x1815bb0d6  nop
0x1815bb0d7  mov     rdx, [rbx]
0x1815bb0da  mov     rax, [rbx+8]
0x1815bb0de  sub     rax, rdx
0x1815bb0e1  sar     rax, 3
0x1815bb0e5  add     rdi, rax
0x1815bb0e8  test    rdx, rdx
0x1815bb0eb  jz      short loc_1815BB100
0x1815bb0ed  mov     r8, [rbx+10h]
0x1815bb0f1  sub     r8, rdx
0x1815bb0f4  sar     r8, 3
0x1815bb0f8  mov     rcx, rbx
0x1815bb0fb  call    ?deallocate@?$allocator@V?$CxWrapper@VCxComputation@@@@@std@@QEAAXPEAV?$CxWrapper@VCxComputation@@@@_K@Z; std::allocator<CxWrapper<CxComputation>>::deallocate(CxWrapper<CxComputation> *,unsigned __int64)
0x1815bb100  lea     rax, [rsi+r15*8]
0x1815bb104  mov     [rbx+10h], rax
0x1815bb108  lea     rax, [rsi+rdi*8]
0x1815bb10c  mov     [rbx+8], rax
0x1815bb110  mov     [rbx], rsi
0x1815bb113  jmp     loc_1815BB247
0x1815bb118  mov     rcx, rsi
0x1815bb11b  sub     rcx, rax
0x1815bb11e  sar     rcx, 3
0x1815bb122  lea     r14, ds:0[r9*8]
0x1815bb12a  cmp     rcx, rdi
0x1815bb12d  jnb     loc_1815BB1D1
0x1815bb133  mov     rcx, [rsp+98h+arg_20]
0x1815bb13b  mov     rdx, [rcx]
0x1815bb13e  mov     [rsp+98h+var_60], rdx
0x1815bb143  lea     rcx, [r14+rax]; void *
0x1815bb147  sub     rsi, rax
0x1815bb14a  mov     r8, rsi; Size
0x1815bb14d  mov     rdx, rax; Src
0x1815bb150  call    cs:__imp_memmove
0x1815bb156  nop
0x1815bb157  mov     rax, [rbx+8]
0x1815bb15b  sub     rax, [rsp+98h+Src]
0x1815bb163  sar     rax, 3
0x1815bb167  sub     rdi, rax
0x1815bb16a  movzx   eax, [rsp+98h+var_68]
0x1815bb16f  mov     [rsp+98h+var_78], al
0x1815bb173  mov     r9, rbx
0x1815bb176  lea     r8, [rsp+98h+var_60]
0x1815bb17b  mov     rdx, rdi
0x1815bb17e  mov     rcx, [rbx+8]
0x1815bb182  call    ??$_Uninit_alloc_fill_n1@PEA_J_KV?$allocator@_J@std@@@std@@YAXPEA_J_KPEB_JAEAU?$_Wrap_alloc@V?$allocator@_J@std@@@0@U?$integral_constant@_N$0A@@0@@Z; std::_Uninit_alloc_fill_n1<__int64 *,unsigned __int64,std::allocator<__int64>>(__int64 *,unsigned __int64,__int64 const *,std::_Wrap_alloc<std::allocator<__int64>> &,std::integral_constant<bool,0>)
0x1815bb187  nop
0x1815bb188  add     [rbx+8], r14
0x1815bb18c  mov     rax, [rbx+8]
0x1815bb190  sub     rax, r14
0x1815bb193  mov     rdx, [rsp+98h+Src]
0x1815bb19b  xor     ecx, ecx
0x1815bb19d  mov     r8, rax
0x1815bb1a0  sub     r8, rdx
0x1815bb1a3  add     r8, 7
0x1815bb1a7  shr     r8, 3
0x1815bb1ab  cmp     rdx, rax
0x1815bb1ae  cmova   r8, rcx
0x1815bb1b2  test    r8, r8
0x1815bb1b5  jz      loc_1815BB247
0x1815bb1bb  mov     rax, [rsp+98h+var_60]
0x1815bb1c0  mov     [rdx], rax
0x1815bb1c3  lea     rdx, [rdx+8]
0x1815bb1c7  inc     rcx
0x1815bb1ca  cmp     rcx, r8
0x1815bb1cd  jnz     short loc_1815BB1C0
0x1815bb1cf  jmp     short loc_1815BB247
0x1815bb1d1  mov     rax, [rsp+98h+arg_20]
0x1815bb1d9  mov     r15, [rax]
0x1815bb1dc  mov     rdx, rsi
0x1815bb1df  sub     rdx, r14; Src
0x1815bb1e2  mov     r8, r14; Size
0x1815bb1e5  mov     rcx, rsi; void *
0x1815bb1e8  call    cs:__imp_memmove
0x1815bb1ee  lea     rax, [r14+rsi]
0x1815bb1f2  mov     [rbx+8], rax
0x1815bb1f6  imul    r8, rdi, -8
0x1815bb1fa  mov     rdx, [rsp+98h+Src]; Src
0x1815bb202  sub     r8, rdx
0x1815bb205  add     r8, rsi; Size
0x1815bb208  sub     rsi, r8
0x1815bb20b  mov     rcx, rsi; void *
0x1815bb20e  call    cs:__imp_memmove
0x1815bb214  mov     r8, [rsp+98h+Src]
0x1815bb21c  lea     rax, [r14+r8]
0x1815bb220  cmp     r8, rax
0x1815bb223  jz      short loc_1815BB247
0x1815bb225  nop     word ptr [rax+rax+00000000h]
0x1815bb230  mov     [r8], r15
0x1815bb233  add     r8, 8
0x1815bb237  mov     rdx, [rsp+98h+Src]
0x1815bb23f  add     rdx, r14
0x1815bb242  cmp     r8, rdx
0x1815bb245  jnz     short loc_1815BB230
0x1815bb247  mov     rcx, [rbx]
0x1815bb24a  lea     rdx, [rcx+r12*8]
0x1815bb24e  mov     [r13+0], rdx
0x1815bb252  mov     rax, r13
0x1815bb255  add     rsp, 60h
0x1815bb259  pop     r15
0x1815bb25b  pop     r14
0x1815bb25d  pop     r13
0x1815bb25f  pop     r12
0x1815bb261  pop     rdi
0x1815bb262  pop     rsi
0x1815bb263  pop     rbx
0x1815bb264  retn
```
