# asg::SemanticPipelines::SingleTextEmbeddingPipeline::CreateFromModel(asg::Guid,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::VectorSpaceRegistry const &)

- ea: `0x1800a23e0`
- end: `0x1800a289e`
- name: `?CreateFromModel@SingleTextEmbeddingPipeline@SemanticPipelines@asg@@SA?AV?$shared_ptr@VSingleTextEmbeddingPipeline@SemanticPipelines@asg@@@std@@UGuid@3@W4EmbeddingElementType@SemanticRegistry@3@AEBVVectorSpaceRegistry@83@@Z`
- size: `1214`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a29a0`

## callees

- `0x180004140`
- `0x180004700`
- `0x180004a80`
- `0x180004bf0`
- `0x18000e5a0`
- `0x180087df0`
- `0x18009deb0`
- `0x1800a1900`
- `0x1800a23e0`
- `0x1801f7110`
- `0x1801f7190`
- `0x1801f97e0`

## string_xrefs

- `0x1800a282a`: `A compatible text model accessor factory could not be found`
- `0x1800a284d`: `Failed to create a text model accessor`
- `0x1800a2870`: `Failed to create a text tokenizer`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 *__fastcall asg::SemanticPipelines::SingleTextEmbeddingPipeline::CreateFromModel(
        __int64 *a1,
        _OWORD *a2,
        unsigned int a3,
        __int64 a4)
{
  struct asg::SemanticPipelines::ModelAccessorFactoryRegistry *v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 *v12; // rax
  __int64 v13; // r14
  volatile signed __int32 *v14; // rsi
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  __int64 v16; // rcx
  void (__fastcall ***v17)(_QWORD, __int64); // r8
  __int64 *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r14
  __int64 *v21; // rax
  __int64 v22; // r12
  volatile signed __int32 *v23; // rdi
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  _DWORD *v25; // rcx
  void (__fastcall ***v26)(_QWORD, _DWORD *); // r8
  __int64 *v27; // rax
  __int64 v28; // r14
  _DWORD *v29; // rax
  volatile signed __int32 *v30; // rdi
  volatile signed __int32 *v31; // rdi
  _OWORD pExceptionObject[2]; // [rsp+30h] [rbp-A9h] BYREF
  _DWORD *v34; // [rsp+50h] [rbp-89h] BYREF
  __int128 v35; // [rsp+60h] [rbp-79h] BYREF
  __int64 *v36; // [rsp+78h] [rbp-61h]
  __int128 v37; // [rsp+80h] [rbp-59h]
  __int128 v38; // [rsp+90h] [rbp-49h]
  __int128 v39; // [rsp+A0h] [rbp-39h] BYREF
  __int128 v40; // [rsp+B0h] [rbp-29h] BYREF
  __int128 v41; // [rsp+C0h] [rbp-19h] BYREF
  _BYTE v42[16]; // [rsp+D0h] [rbp-9h] BYREF

  v36 = a1;
  v41 = 0;
  v8 = asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance();
  pExceptionObject[0] = *a2;
  asg::SemanticPipelines::ModelAccessorFactoryRegistry::TryGetTextModelAccessorFactory(v8, &v41, pExceptionObject, a4);
  if ( !(_QWORD)v41 || !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v41 + 16LL))(v41, a3) )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "A compatible text model accessor factory could not be found");
    throw (std::invalid_argument *)pExceptionObject;
  }
  v40 = 0;
  pExceptionObject[0] = *a2;
  asg::SemanticRegistry::VectorSpaceRegistry::GetModel(a4, &v40, pExceptionObject);
  asg::SemanticRegistry::ModelDescriptor::QuantizationParameters(v40, v42);
  v38 = 0;
  v9 = (__int64 *)(**(__int64 (__fastcall ***)(_QWORD, __int128 *, _BYTE *))v41)(v41, &v35, v42);
  pExceptionObject[0] = 0;
  v11 = *v9;
  *v9 = 0;
  *(_QWORD *)&pExceptionObject[0] = v11;
  BYTE8(pExceptionObject[0]) = 1;
  if ( !v11 || *(_BYTE *)(v11 + 200) )
    std::_Throw_future_error2(4);
  LOBYTE(v10) = 1;
  v12 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 16LL))(v11, v10);
  v13 = *v12;
  *(_QWORD *)&v38 = *v12;
  v14 = (volatile signed __int32 *)v12[1];
  *((_QWORD *)&v38 + 1) = v14;
  *v12 = 0;
  v12[1] = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 0xFFFFFFFF) == 1 )
  {
    v15 = *(void (__fastcall ****)(_QWORD, __int64))(v11 + 216);
    if ( v15 )
      (**v15)(v15, v11);
    else
      (**(void (__fastcall ***)(__int64, __int64))v11)(v11, 1);
  }
  v16 = v35;
  if ( (_QWORD)v35 && _InterlockedExchangeAdd((volatile signed __int32 *)(v35 + 8), 0xFFFFFFFF) == 1 )
  {
    v17 = *(void (__fastcall ****)(_QWORD, __int64))(v16 + 216);
    if ( v17 )
      (**v17)(*(_QWORD *)(v16 + 216), v16);
    else
      (**(void (__fastcall ***)(__int64, __int64))v16)(v16, 1);
  }
  if ( !v13 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Failed to create a text model accessor");
    throw (std::runtime_error *)pExceptionObject;
  }
  v37 = 0;
  v18 = (__int64 *)(*(__int64 (__fastcall **)(_QWORD, _DWORD **))(*(_QWORD *)v41 + 8LL))(v41, &v34);
  pExceptionObject[0] = 0;
  v20 = *v18;
  *v18 = 0;
  *(_QWORD *)&pExceptionObject[0] = v20;
  BYTE8(pExceptionObject[0]) = 1;
  if ( !v20 || *(_BYTE *)(v20 + 200) )
    std::_Throw_future_error2(4);
  LOBYTE(v19) = 1;
  v21 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 16LL))(v20, v19);
  v22 = *v21;
  *(_QWORD *)&v37 = *v21;
  v23 = (volatile signed __int32 *)v21[1];
  *((_QWORD *)&v37 + 1) = v23;
  *v21 = 0;
  v21[1] = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v20 + 8), 0xFFFFFFFF) == 1 )
  {
    v24 = *(void (__fastcall ****)(_QWORD, __int64))(v20 + 216);
    if ( v24 )
      (**v24)(v24, v20);
    else
      (**(void (__fastcall ***)(__int64, __int64))v20)(v20, 1);
  }
  v25 = v34;
  if ( v34 && _InterlockedExchangeAdd(v34 + 2, 0xFFFFFFFF) == 1 )
  {
    v26 = (void (__fastcall ***)(_QWORD, _DWORD *))*((_QWORD *)v25 + 27);
    if ( v26 )
      (**v26)(*((_QWORD *)v25 + 27), v25);
    else
      (**(void (__fastcall ***)(_DWORD *, __int64))v25)(v25, 1);
  }
  if ( !v22 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)pExceptionObject, "Failed to create a text tokenizer");
    throw (std::runtime_error *)pExceptionObject;
  }
  v27 = (__int64 *)operator new(0x38u);
  v36 = v27;
  if ( v27 )
  {
    *(_OWORD *)v27 = 0;
    *((_OWORD *)v27 + 1) = 0;
    *((_OWORD *)v27 + 2) = 0;
    v27[6] = 0;
    v39 = 0;
    if ( v23 )
      _InterlockedIncrement(v23 + 2);
    v39 = v37;
    v35 = 0;
    if ( v14 )
      _InterlockedIncrement(v14 + 2);
    v35 = v38;
    pExceptionObject[0] = 0;
    if ( *((_QWORD *)&v40 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL));
    pExceptionObject[0] = v40;
    v28 = asg::SemanticPipelines::SingleTextEmbeddingPipeline::SingleTextEmbeddingPipeline(
            v27,
            pExceptionObject,
            a3,
            &v35,
            &v39);
  }
  else
  {
    v28 = 0;
  }
  *a1 = 0;
  a1[1] = 0;
  v34 = (_DWORD *)v28;
  v29 = operator new(0x18u);
  v34 = v29;
  if ( v29 )
  {
    *(_OWORD *)v29 = 0;
    v29[2] = 1;
    v29[3] = 1;
    *(_QWORD *)v29 = &std::_Ref_count<asg::SemanticPipelines::SingleTextEmbeddingPipeline>::`vftable';
    *((_QWORD *)v29 + 2) = v28;
  }
  *a1 = v28;
  a1[1] = (__int64)v29;
  if ( v23 )
  {
    if ( _InterlockedExchangeAdd(v23 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v30 = (volatile signed __int32 *)*((_QWORD *)&v40 + 1);
  if ( *((_QWORD *)&v40 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v40 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v30)(v30);
      if ( _InterlockedExchangeAdd(v30 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v30 + 8LL))(v30);
    }
  }
  v31 = (volatile signed __int32 *)*((_QWORD *)&v41 + 1);
  if ( *((_QWORD *)&v41 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v41 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      if ( _InterlockedExchangeAdd(v31 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800a23e0  push    rbp
0x1800a23e2  push    rbx
0x1800a23e3  push    rsi
0x1800a23e4  push    rdi
0x1800a23e5  push    r12
0x1800a23e7  push    r13
0x1800a23e9  push    r14
0x1800a23eb  push    r15
0x1800a23ed  lea     rbp, [rsp-1Fh]
0x1800a23f2  sub     rsp, 0F8h
0x1800a23f9  mov     rax, cs:__security_cookie
0x1800a2400  xor     rax, rsp
0x1800a2403  mov     [rbp+57h+var_50], rax
0x1800a2407  mov     rdi, r9
0x1800a240a  mov     r13d, r8d
0x1800a240d  mov     rbx, rdx
0x1800a2410  mov     r15, rcx
0x1800a2413  mov     [rbp+57h+var_B8], rcx
0x1800a2417  xor     r12d, r12d
0x1800a241a  xorps   xmm0, xmm0
0x1800a241d  movups  [rbp+57h+var_70], xmm0
0x1800a2421  call    ?Instance@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@SAAEAU123@XZ; asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance(void)
0x1800a2426  movups  xmm0, xmmword ptr [rbx]
0x1800a2429  movaps  [rsp+130h+pExceptionObject], xmm0
0x1800a242e  mov     r9, rdi
0x1800a2431  lea     r8, [rsp+130h+pExceptionObject]
0x1800a2436  lea     rdx, [rbp+57h+var_70]
0x1800a243a  mov     rcx, rax
0x1800a243d  call    ?TryGetTextModelAccessorFactory@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@QEBA?AV?$shared_ptr@UITextModelAccessorFactory@SemanticPipelines@asg@@@std@@UGuid@3@PEBVVectorSpaceRegistry@SemanticRegistry@3@@Z; asg::SemanticPipelines::ModelAccessorFactoryRegistry::TryGetTextModelAccessorFactory(asg::Guid,asg::SemanticRegistry::VectorSpaceRegistry const *)
0x1800a2442  nop
0x1800a2443  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800a2447  test    rcx, rcx
0x1800a244a  jz      loc_1800A282A
0x1800a2450  mov     rax, [rcx]
0x1800a2453  mov     edx, r13d
0x1800a2456  call    qword ptr [rax+10h]
0x1800a2459  test    al, al
0x1800a245b  jz      loc_1800A282A
0x1800a2461  xorps   xmm0, xmm0
0x1800a2464  movups  [rbp+57h+var_80], xmm0
0x1800a2468  movups  xmm1, xmmword ptr [rbx]
0x1800a246b  movaps  [rsp+130h+pExceptionObject], xmm1
0x1800a2470  lea     r8, [rsp+130h+pExceptionObject]
0x1800a2475  lea     rdx, [rbp+57h+var_80]
0x1800a2479  mov     rcx, rdi
0x1800a247c  call    ?GetModel@VectorSpaceRegistry@SemanticRegistry@asg@@QEBA?AV?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@std@@UGuid@3@@Z; asg::SemanticRegistry::VectorSpaceRegistry::GetModel(asg::Guid)
0x1800a2481  nop
0x1800a2482  lea     rdx, [rbp+57h+var_60]
0x1800a2486  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800a248a  call    ?QuantizationParameters@ModelDescriptor@SemanticRegistry@asg@@QEBA?AV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@XZ; asg::SemanticRegistry::ModelDescriptor::QuantizationParameters(void)
0x1800a248f  xorps   xmm0, xmm0
0x1800a2492  movups  [rbp+57h+var_A0], xmm0
0x1800a2496  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800a249a  mov     rax, [rcx]
0x1800a249d  lea     r8, [rbp+57h+var_60]
0x1800a24a1  lea     rdx, [rbp+57h+var_D0]
0x1800a24a5  call    qword ptr [rax]
0x1800a24a7  nop
0x1800a24a8  xorps   xmm0, xmm0
0x1800a24ab  movups  [rsp+130h+pExceptionObject], xmm0
0x1800a24b0  mov     rdi, [rax]
0x1800a24b3  mov     [rax], r12
0x1800a24b6  mov     qword ptr [rsp+130h+pExceptionObject], rdi
0x1800a24bb  mov     byte ptr [rsp+130h+pExceptionObject+8], 1
0x1800a24c0  test    rdi, rdi
0x1800a24c3  jz      loc_1800A281F
0x1800a24c9  cmp     [rdi+0C8h], r12b
0x1800a24d0  jnz     loc_1800A281F
0x1800a24d6  mov     rax, [rdi]
0x1800a24d9  mov     dl, 1
0x1800a24db  mov     rcx, rdi
0x1800a24de  call    qword ptr [rax+10h]
0x1800a24e1  mov     r14, [rax]
0x1800a24e4  mov     qword ptr [rbp+57h+var_A0], r14
0x1800a24e8  mov     rsi, [rax+8]
0x1800a24ec  mov     qword ptr [rbp+57h+var_A0+8], rsi
0x1800a24f0  mov     [rax], r12
0x1800a24f3  mov     [rax+8], r12
0x1800a24f7  mov     ebx, 0FFFFFFFFh
0x1800a24fc  mov     eax, ebx
0x1800a24fe  lock xadd [rdi+8], eax
0x1800a2503  cmp     eax, 1
0x1800a2506  jnz     short loc_1800A252C
0x1800a2508  mov     rcx, [rdi+0D8h]
0x1800a250f  test    rcx, rcx
0x1800a2512  jz      short loc_1800A251E
0x1800a2514  mov     rax, [rcx]
0x1800a2517  mov     rdx, rdi
0x1800a251a  call    qword ptr [rax]
0x1800a251c  jmp     short loc_1800A252C
0x1800a251e  mov     rax, [rdi]
0x1800a2521  mov     edx, 1
0x1800a2526  mov     rcx, rdi
0x1800a2529  call    qword ptr [rax]
0x1800a252b  nop
0x1800a252c  mov     rcx, qword ptr [rbp+57h+var_D0]
0x1800a2530  test    rcx, rcx
0x1800a2533  jz      short loc_1800A2564
0x1800a2535  mov     eax, ebx
0x1800a2537  lock xadd [rcx+8], eax
0x1800a253c  cmp     eax, 1
0x1800a253f  jnz     short loc_1800A2564
0x1800a2541  mov     r8, [rcx+0D8h]
0x1800a2548  test    r8, r8
0x1800a254b  jz      short loc_1800A255A
0x1800a254d  mov     rax, [r8]
0x1800a2550  mov     rdx, rcx
0x1800a2553  mov     rcx, r8
0x1800a2556  call    qword ptr [rax]
0x1800a2558  jmp     short loc_1800A2564
0x1800a255a  mov     rax, [rcx]
0x1800a255d  mov     edx, 1
0x1800a2562  call    qword ptr [rax]
0x1800a2564  test    r14, r14
0x1800a2567  jz      loc_1800A284D
0x1800a256d  xorps   xmm0, xmm0
0x1800a2570  movups  [rbp+57h+var_B0], xmm0
0x1800a2574  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800a2578  mov     rax, [rcx]
0x1800a257b  lea     rdx, [rsp+130h+var_E0]
0x1800a2580  call    qword ptr [rax+8]
0x1800a2583  nop
0x1800a2584  xorps   xmm0, xmm0
0x1800a2587  movups  [rsp+130h+pExceptionObject], xmm0
0x1800a258c  mov     r14, [rax]
0x1800a258f  mov     [rax], r12
0x1800a2592  mov     qword ptr [rsp+130h+pExceptionObject], r14
0x1800a2597  mov     byte ptr [rsp+130h+pExceptionObject+8], 1
0x1800a259c  test    r14, r14
0x1800a259f  jz      loc_1800A2893
0x1800a25a5  cmp     byte ptr [r14+0C8h], 0
0x1800a25ad  jnz     loc_1800A2893
0x1800a25b3  mov     rax, [r14]
0x1800a25b6  mov     dl, 1
0x1800a25b8  mov     rcx, r14
0x1800a25bb  call    qword ptr [rax+10h]
0x1800a25be  mov     r12, [rax]
0x1800a25c1  mov     qword ptr [rbp+57h+var_B0], r12
0x1800a25c5  mov     rdi, [rax+8]
0x1800a25c9  mov     qword ptr [rbp+57h+var_B0+8], rdi
0x1800a25cd  xor     ecx, ecx
0x1800a25cf  mov     [rax], rcx
0x1800a25d2  mov     [rax+8], rcx
0x1800a25d6  mov     eax, ebx
0x1800a25d8  lock xadd [r14+8], eax
0x1800a25de  cmp     eax, 1
0x1800a25e1  jnz     short loc_1800A2607
0x1800a25e3  mov     rcx, [r14+0D8h]
0x1800a25ea  test    rcx, rcx
0x1800a25ed  jz      short loc_1800A25F9
0x1800a25ef  mov     rax, [rcx]
0x1800a25f2  mov     rdx, r14
0x1800a25f5  call    qword ptr [rax]
0x1800a25f7  jmp     short loc_1800A2607
0x1800a25f9  mov     rax, [r14]
0x1800a25fc  mov     edx, 1
0x1800a2601  mov     rcx, r14
0x1800a2604  call    qword ptr [rax]
0x1800a2606  nop
0x1800a2607  mov     rcx, [rsp+130h+var_E0]
0x1800a260c  test    rcx, rcx
0x1800a260f  jz      short loc_1800A2640
0x1800a2611  mov     eax, ebx
0x1800a2613  lock xadd [rcx+8], eax
0x1800a2618  cmp     eax, 1
0x1800a261b  jnz     short loc_1800A2640
0x1800a261d  mov     r8, [rcx+0D8h]
0x1800a2624  test    r8, r8
0x1800a2627  jz      short loc_1800A2636
0x1800a2629  mov     rax, [r8]
0x1800a262c  mov     rdx, rcx
0x1800a262f  mov     rcx, r8
0x1800a2632  call    qword ptr [rax]
0x1800a2634  jmp     short loc_1800A2640
0x1800a2636  mov     rax, [rcx]
0x1800a2639  mov     edx, 1
0x1800a263e  call    qword ptr [rax]
0x1800a2640  test    r12, r12
0x1800a2643  jz      loc_1800A2870
0x1800a2649  mov     ecx, 38h ; '8'; Size
0x1800a264e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a2653  mov     [rbp+57h+var_B8], rax
0x1800a2657  test    rax, rax
0x1800a265a  jz      loc_1800A26E7
0x1800a2660  xorps   xmm0, xmm0
0x1800a2663  xor     ecx, ecx
0x1800a2665  movups  xmmword ptr [rax], xmm0
0x1800a2668  movups  xmmword ptr [rax+10h], xmm0
0x1800a266c  movups  xmmword ptr [rax+20h], xmm0
0x1800a2670  mov     [rax+30h], rcx
0x1800a2674  movdqa  [rbp+57h+var_90], xmm0
0x1800a2679  test    rdi, rdi
0x1800a267c  jz      short loc_1800A2682
0x1800a267e  lock inc dword ptr [rdi+8]
0x1800a2682  movaps  xmm0, [rbp+57h+var_B0]
0x1800a2686  movdqa  [rbp+57h+var_90], xmm0
0x1800a268b  xorps   xmm0, xmm0
0x1800a268e  movdqa  [rbp+57h+var_D0], xmm0
0x1800a2693  test    rsi, rsi
0x1800a2696  jz      short loc_1800A269C
0x1800a2698  lock inc dword ptr [rsi+8]
0x1800a269c  movaps  xmm0, [rbp+57h+var_A0]
0x1800a26a0  movdqa  [rbp+57h+var_D0], xmm0
0x1800a26a5  xorps   xmm0, xmm0
0x1800a26a8  movdqa  [rsp+130h+pExceptionObject], xmm0
0x1800a26ae  mov     rcx, qword ptr [rbp+57h+var_80+8]
0x1800a26b2  test    rcx, rcx
0x1800a26b5  jz      short loc_1800A26BB
0x1800a26b7  lock inc dword ptr [rcx+8]
0x1800a26bb  movaps  xmm0, [rbp+57h+var_80]
0x1800a26bf  movdqa  [rsp+130h+pExceptionObject], xmm0
0x1800a26c5  lea     rcx, [rbp+57h+var_90]
0x1800a26c9  mov     [rsp+130h+var_110], rcx
0x1800a26ce  lea     r9, [rbp+57h+var_D0]
0x1800a26d2  mov     r8d, r13d
0x1800a26d5  lea     rdx, [rsp+130h+pExceptionObject]
0x1800a26da  mov     rcx, rax
0x1800a26dd  call    ??0SingleTextEmbeddingPipeline@SemanticPipelines@asg@@AEAA@V?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@std@@W4EmbeddingElementType@SemanticRegistry@2@V?$shared_ptr@UITextModelAccessor@SemanticPipelines@asg@@@4@V?$shared_ptr@VITokenizer@SemanticRegistry@asg@@@4@@Z; asg::SemanticPipelines::SingleTextEmbeddingPipeline::SingleTextEmbeddingPipeline(std::shared_ptr<asg::SemanticRegistry::ModelDescriptor const>,asg::SemanticRegistry::EmbeddingElementType,std::shared_ptr<asg::SemanticPipelines::ITextModelAccessor>,std::shared_ptr<asg::SemanticRegistry::ITokenizer>)
0x1800a26e2  mov     r14, rax
0x1800a26e5  jmp     short loc_1800A26EA
0x1800a26e7  xor     r14d, r14d
0x1800a26ea  mov     qword ptr [r15], 0
0x1800a26f1  mov     qword ptr [r15+8], 0
0x1800a26f9  mov     [rsp+130h+var_E0], r14
0x1800a26fe  mov     ecx, 18h; Size
0x1800a2703  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a2708  mov     [rsp+130h+var_E0], rax
0x1800a270d  test    rax, rax
0x1800a2710  jz      short loc_1800A2734
0x1800a2712  xorps   xmm0, xmm0
0x1800a2715  movups  xmmword ptr [rax], xmm0
0x1800a2718  mov     dword ptr [rax+8], 1
0x1800a271f  mov     dword ptr [rax+0Ch], 1
0x1800a2726  lea     rcx, ??_7?$_Ref_count@VSingleTextEmbeddingPipeline@SemanticPipelines@asg@@@std@@6B@; const std::_Ref_count<asg::SemanticPipelines::SingleTextEmbeddingPipeline>::`vftable'
0x1800a272d  mov     [rax], rcx
0x1800a2730  mov     [rax+10h], r14
0x1800a2734  mov     [r15], r14
0x1800a2737  mov     [r15+8], rax
0x1800a273b  test    rdi, rdi
0x1800a273e  jz      short loc_1800A276A
0x1800a2740  mov     eax, ebx
0x1800a2742  lock xadd [rdi+8], eax
0x1800a2747  cmp     eax, 1
0x1800a274a  jnz     short loc_1800A276A
0x1800a274c  mov     rax, [rdi]
0x1800a274f  mov     rcx, rdi
0x1800a2752  call    qword ptr [rax]
0x1800a2754  mov     eax, ebx
0x1800a2756  lock xadd [rdi+0Ch], eax
0x1800a275b  cmp     eax, 1
0x1800a275e  jnz     short loc_1800A276A
0x1800a2760  mov     rax, [rdi]
0x1800a2763  mov     rcx, rdi
0x1800a2766  call    qword ptr [rax+8]
0x1800a2769  nop
0x1800a276a  test    rsi, rsi
0x1800a276d  jz      short loc_1800A2799
0x1800a276f  mov     eax, ebx
0x1800a2771  lock xadd [rsi+8], eax
0x1800a2776  cmp     eax, 1
0x1800a2779  jnz     short loc_1800A2799
0x1800a277b  mov     rax, [rsi]
0x1800a277e  mov     rcx, rsi
0x1800a2781  call    qword ptr [rax]
0x1800a2783  mov     eax, ebx
0x1800a2785  lock xadd [rsi+0Ch], eax
0x1800a278a  cmp     eax, 1
0x1800a278d  jnz     short loc_1800A2799
0x1800a278f  mov     rax, [rsi]
0x1800a2792  mov     rcx, rsi
0x1800a2795  call    qword ptr [rax+8]
0x1800a2798  nop
0x1800a2799  mov     rdi, qword ptr [rbp+57h+var_80+8]
0x1800a279d  test    rdi, rdi
0x1800a27a0  jz      short loc_1800A27CC
0x1800a27a2  mov     eax, ebx
0x1800a27a4  lock xadd [rdi+8], eax
0x1800a27a9  cmp     eax, 1
0x1800a27ac  jnz     short loc_1800A27CC
0x1800a27ae  mov     rax, [rdi]
0x1800a27b1  mov     rcx, rdi
0x1800a27b4  call    qword ptr [rax]
0x1800a27b6  mov     eax, ebx
0x1800a27b8  lock xadd [rdi+0Ch], eax
0x1800a27bd  cmp     eax, 1
0x1800a27c0  jnz     short loc_1800A27CC
0x1800a27c2  mov     rax, [rdi]
0x1800a27c5  mov     rcx, rdi
0x1800a27c8  call    qword ptr [rax+8]
0x1800a27cb  nop
0x1800a27cc  mov     rdi, qword ptr [rbp+57h+var_70+8]
0x1800a27d0  test    rdi, rdi
0x1800a27d3  jz      short loc_1800A27FC
0x1800a27d5  mov     eax, ebx
0x1800a27d7  lock xadd [rdi+8], eax
0x1800a27dc  cmp     eax, 1
0x1800a27df  jnz     short loc_1800A27FC
0x1800a27e1  mov     rax, [rdi]
0x1800a27e4  mov     rcx, rdi
0x1800a27e7  call    qword ptr [rax]
  ... truncated ...
```
