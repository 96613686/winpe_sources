# std::vector<Windows::AutoNewPtr<FeatureDescriptor>,std::allocator<Windows::AutoNewPtr<FeatureDescriptor>>>::_Emplace_reallocate<Windows::AutoNewPtr<FeatureDescriptor>>(Windows::AutoNewPtr<FeatureDescriptor> * const,Windows::AutoNewPtr<FeatureDescriptor> &&)

- ea: `0x1800263b4`
- end: `0x1800265fa`
- name: `??$_Emplace_reallocate@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@AEAAPEAV?$AutoNewPtr@UFeatureDescriptor@@@Windows@@QEAV23@$$QEAV23@@Z`
- size: `582`
- prototype: `void **__fastcall(void ***, void **, __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x1800268d4`

## callees

- `0x180003544`
- `0x180003a34`
- `0x18000a81c`
- `0x18000a85c`
- `0x1800263b4`
- `0x180026834`

## pseudocode

```c
void **__fastcall std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Emplace_reallocate<Windows::AutoNewPtr<FeatureDescriptor>>(
        void ***a1,
        void **a2,
        __int64 *a3)
{
  void **v3; // r12
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // r15
  void **v12; // rbx
  void *v13; // rax
  void *v14; // rax
  __int64 v15; // r14
  void **v16; // rdx
  void **v17; // r8
  void **v18; // rcx
  void **v19; // rdx
  void *v20; // rax
  __int64 v21; // r14
  void *v22; // rax
  void **v23; // rcx
  void *v24; // rax
  void **v25; // rsi
  void **v26; // rbp
  void *v27; // rcx
  void **v28; // rcx
  void **v29; // rax
  __int64 v31; // [rsp+20h] [rbp-68h]
  _QWORD v32[3]; // [rsp+28h] [rbp-60h] BYREF
  void **v33; // [rsp+40h] [rbp-48h]
  _QWORD *v34; // [rsp+48h] [rbp-40h]

  v3 = *a1;
  v6 = a1[1] - *a1;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Xlength();
  v8 = a1[2] - v3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_36;
  v31 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v10 = v8 + v9;
  if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_36;
  v11 = 8 * v10;
  if ( !(8 * v10) )
  {
    v12 = 0;
    goto LABEL_13;
  }
  if ( v11 < 0x1000 )
  {
    v12 = (void **)operator new(8 * v10);
    goto LABEL_13;
  }
  if ( v11 + 39 < v11 )
LABEL_36:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    goto LABEL_31;
  v12 = (void **)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_13:
  v14 = (void *)*a3;
  *a3 = 0;
  v15 = a2 - v3;
  v32[0] = a1;
  v32[2] = v10;
  v16 = &v12[v15];
  *v16 = v14;
  v17 = a1[1];
  v34 = v16 + 1;
  v18 = *a1;
  v33 = v16;
  v19 = v12;
  if ( a2 == v17 )
  {
    while ( v18 != v17 )
    {
      v20 = *v18;
      *v18++ = 0;
      *v19++ = v20;
    }
    v21 = v15;
  }
  else
  {
    while ( v18 != a2 )
    {
      v22 = *v18;
      *v18++ = 0;
      *v19++ = v22;
    }
    v19 = a1[1];
    v21 = v15;
    v33 = v12;
    v23 = &v12[v21 + 1];
    while ( a2 != v19 )
    {
      v24 = *a2;
      *a2++ = 0;
      *v23++ = v24;
    }
  }
  v25 = *a1;
  v32[1] = 0;
  if ( v25 )
  {
    v26 = a1[1];
    while ( v25 != v26 )
    {
      v27 = *v25;
      if ( *v25 )
      {
        *v25 = 0;
        operator delete(v27);
      }
      ++v25;
    }
    v28 = *a1;
    if ( (unsigned __int64)(8 * (a1[2] - *a1)) < 0x1000 )
    {
      v29 = *a1;
    }
    else
    {
      v29 = (void **)*(v28 - 1);
      if ( (unsigned __int64)((char *)v28 - (char *)v29 - 8) > 0x1F )
LABEL_31:
        __fastfail(5u);
    }
    operator delete(v29);
  }
  *a1 = v12;
  a1[1] = &v12[v31];
  a1[2] = &v12[v11 / 8];
  std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Reallocation_guard::~_Reallocation_guard(v32, v19);
  return &v12[v21];
}

```

## disassembly

```asm
0x1800263b4  mov     [rsp+arg_18], rbx
0x1800263b9  push    rbp
0x1800263ba  push    rsi
0x1800263bb  push    rdi
0x1800263bc  push    r12
0x1800263be  push    r13
0x1800263c0  push    r14
0x1800263c2  push    r15
0x1800263c4  sub     rsp, 50h
0x1800263c8  mov     r12, [rcx]
0x1800263cb  mov     rsi, rdx
0x1800263ce  mov     rdx, [rcx+8]
0x1800263d2  mov     r9, 1FFFFFFFFFFFFFFFh
0x1800263dc  sub     rdx, r12
0x1800263df  mov     r13, r8
0x1800263e2  sar     rdx, 3
0x1800263e6  mov     rdi, rcx
0x1800263e9  cmp     rdx, r9
0x1800263ec  jz      loc_1800265EE
0x1800263f2  mov     rcx, [rcx+10h]
0x1800263f6  mov     rax, r9
0x1800263f9  sub     rcx, r12
0x1800263fc  sar     rcx, 3
0x180026400  mov     r8, rcx
0x180026403  shr     r8, 1
0x180026406  sub     rax, r8
0x180026409  cmp     rcx, rax
0x18002640c  ja      loc_1800265F4
0x180026412  inc     rdx
0x180026415  lea     rax, [rcx+r8]
0x180026419  cmp     rax, rdx
0x18002641c  mov     [rsp+88h+var_68], rdx
0x180026421  mov     rbp, rdx
0x180026424  cmovnb  rbp, rax
0x180026428  cmp     rbp, r9
0x18002642b  ja      loc_1800265F4
0x180026431  lea     r15, ds:0[rbp*8]
0x180026439  test    r15, r15
0x18002643c  jnz     short loc_180026442
0x18002643e  xor     ebx, ebx
0x180026440  jmp     short loc_18002647F
0x180026442  cmp     r15, 1000h
0x180026449  jb      short loc_180026474
0x18002644b  lea     rcx, [r15+27h]; Size
0x18002644f  cmp     rcx, r15
0x180026452  jbe     loc_1800265F4
0x180026458  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002645d  test    rax, rax
0x180026460  jz      loc_18002659E
0x180026466  lea     rbx, [rax+27h]
0x18002646a  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18002646e  mov     [rbx-8], rax
0x180026472  jmp     short loc_18002647F
0x180026474  mov     rcx, r15; Size
0x180026477  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002647c  mov     rbx, rax
0x18002647f  mov     rax, [r13+0]
0x180026483  mov     r14, rsi
0x180026486  mov     qword ptr [r13+0], 0
0x18002648e  sub     r14, r12
0x180026491  sar     r14, 3
0x180026495  mov     [rsp+88h+var_60], rdi
0x18002649a  mov     [rsp+88h+var_50], rbp
0x18002649f  lea     rdx, [rbx+r14*8]
0x1800264a3  mov     [rdx], rax
0x1800264a6  lea     rcx, [rdx+8]
0x1800264aa  mov     r8, [rdi+8]
0x1800264ae  mov     [rsp+88h+var_40], rcx
0x1800264b3  mov     rcx, [rdi]
0x1800264b6  mov     [rsp+88h+var_48], rdx
0x1800264bb  mov     rdx, rbx
0x1800264be  cmp     rsi, r8
0x1800264c1  jnz     short loc_1800264FA
0x1800264c3  jmp     short loc_1800264DA
0x1800264c5  mov     rax, [rcx]
0x1800264c8  mov     qword ptr [rcx], 0
0x1800264cf  add     rcx, 8
0x1800264d3  mov     [rdx], rax
0x1800264d6  lea     rdx, [rdx+8]
0x1800264da  cmp     rcx, r8
0x1800264dd  jnz     short loc_1800264C5
0x1800264df  shl     r14, 3
0x1800264e3  jmp     short loc_18002652F
0x1800264e5  mov     rax, [rcx]
0x1800264e8  mov     qword ptr [rcx], 0
0x1800264ef  add     rcx, 8
0x1800264f3  mov     [rdx], rax
0x1800264f6  lea     rdx, [rdx+8]
0x1800264fa  cmp     rcx, rsi
0x1800264fd  jnz     short loc_1800264E5
0x1800264ff  mov     rdx, [rdi+8]
0x180026503  shl     r14, 3
0x180026507  mov     [rsp+88h+var_48], rbx
0x18002650c  lea     rcx, [r14+8]
0x180026510  add     rcx, rbx
0x180026513  jmp     short loc_18002652A
0x180026515  mov     rax, [rsi]
0x180026518  mov     qword ptr [rsi], 0
0x18002651f  add     rsi, 8
0x180026523  mov     [rcx], rax
0x180026526  lea     rcx, [rcx+8]
0x18002652a  cmp     rsi, rdx
0x18002652d  jnz     short loc_180026515
0x18002652f  mov     rsi, [rdi]
0x180026532  mov     [rsp+88h+var_58], 0
0x18002653b  test    rsi, rsi
0x18002653e  jz      short loc_1800265B0
0x180026540  mov     rbp, [rdi+8]
0x180026544  jmp     short loc_180026563
0x180026546  mov     rcx, [rsi]; Block
0x180026549  test    rcx, rcx
0x18002654c  jz      short loc_18002655F
0x18002654e  mov     edx, 18h
0x180026553  mov     qword ptr [rsi], 0
0x18002655a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002655f  add     rsi, 8
0x180026563  cmp     rsi, rbp
0x180026566  jnz     short loc_180026546
0x180026568  mov     rcx, [rdi]
0x18002656b  mov     rax, [rdi+10h]
0x18002656f  sub     rax, rcx
0x180026572  sar     rax, 3
0x180026576  lea     rdx, ds:0[rax*8]
0x18002657e  cmp     rdx, 1000h
0x180026585  jb      short loc_1800265A5
0x180026587  mov     rax, [rcx-8]
0x18002658b  sub     rcx, rax
0x18002658e  sub     rcx, 8
0x180026592  cmp     rcx, 1Fh
0x180026596  ja      short loc_18002659E
0x180026598  add     rdx, 27h ; '''
0x18002659c  jmp     short loc_1800265A8
0x18002659e  mov     ecx, 5
0x1800265a3  int     29h; Win8: RtlFailFast(ecx)
0x1800265a5  mov     rax, rcx
0x1800265a8  mov     rcx, rax; Block
0x1800265ab  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800265b0  mov     rax, [rsp+88h+var_68]
0x1800265b5  lea     rcx, [rsp+88h+var_60]
0x1800265ba  mov     [rdi], rbx
0x1800265bd  lea     rax, [rbx+rax*8]
0x1800265c1  mov     [rdi+8], rax
0x1800265c5  lea     rax, [r15+rbx]
0x1800265c9  mov     [rdi+10h], rax
0x1800265cd  call    ??1_Reallocation_guard@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@QEAA@XZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Reallocation_guard::~_Reallocation_guard(void)
0x1800265d2  lea     rax, [r14+rbx]
0x1800265d6  mov     rbx, [rsp+88h+arg_18]
0x1800265de  add     rsp, 50h
0x1800265e2  pop     r15
0x1800265e4  pop     r14
0x1800265e6  pop     r13
0x1800265e8  pop     r12
0x1800265ea  pop     rdi
0x1800265eb  pop     rsi
0x1800265ec  pop     rbp
0x1800265ed  retn
0x1800265ee  call    ?_Xlength@?$vector@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@V?$allocator@V?$AutoNewPtr@UFeatureDescriptor@@@Windows@@@std@@@std@@CAXXZ; std::vector<Windows::AutoNewPtr<FeatureDescriptor>>::_Xlength(void)
0x1800265f4  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
