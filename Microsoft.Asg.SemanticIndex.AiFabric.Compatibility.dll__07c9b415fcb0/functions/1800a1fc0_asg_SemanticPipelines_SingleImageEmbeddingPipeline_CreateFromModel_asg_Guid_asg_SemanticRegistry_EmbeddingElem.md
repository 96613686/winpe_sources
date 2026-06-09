# asg::SemanticPipelines::SingleImageEmbeddingPipeline::CreateFromModel(asg::Guid,asg::SemanticRegistry::EmbeddingElementType,asg::SemanticRegistry::VectorSpaceRegistry const &)

- ea: `0x1800a1fc0`
- end: `0x1800a23db`
- name: `?CreateFromModel@SingleImageEmbeddingPipeline@SemanticPipelines@asg@@SA?AV?$shared_ptr@VSingleImageEmbeddingPipeline@SemanticPipelines@asg@@@std@@UGuid@3@W4EmbeddingElementType@SemanticRegistry@3@AEBVVectorSpaceRegistry@83@@Z`
- size: `1051`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800a28a0`

## callees

- `0x180004140`
- `0x180004700`
- `0x180004a80`
- `0x180004bf0`
- `0x180006410`
- `0x18000e5a0`
- `0x180087df0`
- `0x18009ddf0`
- `0x1800a1fc0`
- `0x1801f7110`
- `0x1801f7190`
- `0x1801f97e0`

## string_xrefs

- `0x1800a23ba`: `Pipeline's Embedding element type is not supported by the image model accessor. `
- `0x1800a2376`: `A compatible image model accessor factory could not be found`
- `0x1800a2397`: `Failed to create an image model accessor`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
_QWORD *__fastcall asg::SemanticPipelines::SingleImageEmbeddingPipeline::CreateFromModel(
        _QWORD *a1,
        __int128 *a2,
        unsigned int a3,
        __int64 a4)
{
  struct asg::SemanticPipelines::ModelAccessorFactoryRegistry *v8; // rax
  __int64 *v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rbx
  __int64 *v12; // rax
  __int64 v13; // r14
  volatile signed __int32 *v14; // rdi
  void (__fastcall ***v15)(_QWORD, __int64); // rcx
  volatile signed __int32 *v16; // rcx
  void (__fastcall ***v17)(_QWORD, volatile signed __int32 *); // r8
  unsigned int *v18; // rbx
  __int64 v19; // rcx
  volatile signed __int32 *v20; // r14
  volatile signed __int32 *v21; // rax
  volatile signed __int32 *v22; // rbx
  volatile signed __int32 *v23; // rbx
  _OWORD v25[2]; // [rsp+20h] [rbp-A9h] BYREF
  __int128 v26; // [rsp+40h] [rbp-89h] BYREF
  __int128 v27; // [rsp+50h] [rbp-79h] BYREF
  volatile signed __int32 *v28; // [rsp+60h] [rbp-69h] BYREF
  _QWORD *v29; // [rsp+78h] [rbp-51h]
  _OWORD *v30; // [rsp+80h] [rbp-49h]
  _BYTE pExceptionObject[24]; // [rsp+88h] [rbp-41h] BYREF
  __int128 v32; // [rsp+A0h] [rbp-29h] BYREF
  __int128 v33; // [rsp+B0h] [rbp-19h] BYREF
  _BYTE v34[16]; // [rsp+C0h] [rbp-9h] BYREF

  v29 = a1;
  v33 = 0;
  v8 = asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance();
  v27 = *a2;
  asg::SemanticPipelines::ModelAccessorFactoryRegistry::TryGetImageModelAccessorFactory(v8, &v33, &v27, a4);
  if ( !(_QWORD)v33 || !(*(unsigned __int8 (__fastcall **)(_QWORD, _QWORD))(*(_QWORD *)v33 + 8LL))(v33, a3) )
  {
    std::invalid_argument::invalid_argument(
      (std::invalid_argument *)pExceptionObject,
      "A compatible image model accessor factory could not be found");
    throw (std::invalid_argument *)pExceptionObject;
  }
  v32 = 0;
  v27 = *a2;
  asg::SemanticRegistry::VectorSpaceRegistry::GetModel(a4, &v32, &v27);
  asg::SemanticRegistry::ModelDescriptor::QuantizationParameters(v32, v34);
  v27 = 0;
  v9 = (__int64 *)(**(__int64 (__fastcall ***)(_QWORD, volatile signed __int32 **, _BYTE *))v33)(v33, &v28, v34);
  v25[0] = 0;
  v11 = *v9;
  *v9 = 0;
  *(_QWORD *)&v25[0] = v11;
  BYTE8(v25[0]) = 1;
  if ( !v11 || *(_BYTE *)(v11 + 200) )
    std::_Throw_future_error2(4);
  LOBYTE(v10) = 1;
  v12 = (__int64 *)(*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v11 + 16LL))(v11, v10);
  v13 = *v12;
  *(_QWORD *)&v27 = *v12;
  v14 = (volatile signed __int32 *)v12[1];
  *((_QWORD *)&v27 + 1) = v14;
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
  v16 = v28;
  if ( v28 && _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
  {
    v17 = (void (__fastcall ***)(_QWORD, volatile signed __int32 *))*((_QWORD *)v16 + 27);
    if ( v17 )
      (**v17)(*((_QWORD *)v16 + 27), v16);
    else
      (**(void (__fastcall ***)(volatile signed __int32 *, __int64))v16)(v16, 1);
  }
  if ( !v13 )
  {
    std::runtime_error::runtime_error((std::runtime_error *)v25, "Failed to create an image model accessor");
    throw (std::runtime_error *)v25;
  }
  v18 = (unsigned int *)operator new(0x28u);
  v29 = v18;
  if ( v18 )
  {
    *(_OWORD *)v18 = 0;
    *((_OWORD *)v18 + 1) = 0;
    *((_QWORD *)v18 + 4) = 0;
    v25[0] = 0;
    if ( v14 )
      _InterlockedIncrement(v14 + 2);
    v25[0] = v27;
    v30 = v25;
    v26 = 0;
    if ( *((_QWORD *)&v32 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL));
    v26 = v32;
    v28 = (volatile signed __int32 *)&v26;
    *v18 = a3;
    *((_QWORD *)v18 + 1) = 0;
    *((_QWORD *)v18 + 2) = 0;
    *(_OWORD *)(v18 + 2) = v26;
    v26 = 0;
    *((_QWORD *)v18 + 3) = 0;
    *((_QWORD *)v18 + 4) = 0;
    if ( *((_QWORD *)&v25[0] + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v25[0] + 1) + 8LL));
    v19 = *(_QWORD *)&v25[0];
    *(_OWORD *)(v18 + 6) = v25[0];
    if ( !v19 || !(*(unsigned __int8 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v19 + 8LL))(v19, *v18) )
    {
      std::runtime_error::runtime_error(
        (std::runtime_error *)pExceptionObject,
        "Pipeline's Embedding element type is not supported by the image model accessor. ");
      throw (std::runtime_error *)pExceptionObject;
    }
    v20 = (volatile signed __int32 *)*((_QWORD *)&v26 + 1);
    if ( *((_QWORD *)&v26 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v20)(v20);
        if ( _InterlockedExchangeAdd(v20 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v20 + 8LL))(v20);
      }
    }
    std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(v25);
  }
  else
  {
    v18 = 0;
  }
  *a1 = 0;
  a1[1] = 0;
  v28 = (volatile signed __int32 *)v18;
  v21 = (volatile signed __int32 *)operator new(0x18u);
  v28 = v21;
  if ( v21 )
  {
    *(_OWORD *)v21 = 0;
    *((_DWORD *)v21 + 2) = 1;
    *((_DWORD *)v21 + 3) = 1;
    *(_QWORD *)v21 = &std::_Ref_count<asg::SemanticPipelines::SingleImageEmbeddingPipeline>::`vftable';
    *((_QWORD *)v21 + 2) = v18;
  }
  else
  {
    v21 = 0;
  }
  *a1 = v18;
  a1[1] = v21;
  if ( v14 )
  {
    if ( _InterlockedExchangeAdd(v14 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v14)(v14);
      if ( _InterlockedExchangeAdd(v14 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v14 + 8LL))(v14);
    }
  }
  v22 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v22)(v22);
      if ( _InterlockedExchangeAdd(v22 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v22 + 8LL))(v22);
    }
  }
  v23 = (volatile signed __int32 *)*((_QWORD *)&v33 + 1);
  if ( *((_QWORD *)&v33 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v33 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v23)(v23);
      if ( _InterlockedExchangeAdd(v23 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v23 + 8LL))(v23);
    }
  }
  return a1;
}

```

## disassembly

```asm
0x1800a1fc0  push    rbp
0x1800a1fc2  push    rbx
0x1800a1fc3  push    rsi
0x1800a1fc4  push    rdi
0x1800a1fc5  push    r12
0x1800a1fc7  push    r13
0x1800a1fc9  push    r14
0x1800a1fcb  push    r15
0x1800a1fcd  lea     rbp, [rsp-1Fh]
0x1800a1fd2  sub     rsp, 0E8h
0x1800a1fd9  mov     rax, cs:__security_cookie
0x1800a1fe0  xor     rax, rsp
0x1800a1fe3  mov     [rbp+57h+var_50], rax
0x1800a1fe7  mov     rdi, r9
0x1800a1fea  mov     r12d, r8d
0x1800a1fed  mov     rbx, rdx
0x1800a1ff0  mov     r15, rcx
0x1800a1ff3  mov     [rbp+57h+var_A8], rcx
0x1800a1ff7  xor     r13d, r13d
0x1800a1ffa  xorps   xmm0, xmm0
0x1800a1ffd  movups  [rbp+57h+var_70], xmm0
0x1800a2001  call    ?Instance@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@SAAEAU123@XZ; asg::SemanticPipelines::ModelAccessorFactoryRegistry::Instance(void)
0x1800a2006  movups  xmm0, xmmword ptr [rbx]
0x1800a2009  movaps  [rbp+57h+var_D0], xmm0
0x1800a200d  mov     r9, rdi
0x1800a2010  lea     r8, [rbp+57h+var_D0]
0x1800a2014  lea     rdx, [rbp+57h+var_70]
0x1800a2018  mov     rcx, rax
0x1800a201b  call    ?TryGetImageModelAccessorFactory@ModelAccessorFactoryRegistry@SemanticPipelines@asg@@QEBA?AV?$shared_ptr@UIImageModelAccessorFactory@SemanticPipelines@asg@@@std@@UGuid@3@PEBVVectorSpaceRegistry@SemanticRegistry@3@@Z; asg::SemanticPipelines::ModelAccessorFactoryRegistry::TryGetImageModelAccessorFactory(asg::Guid,asg::SemanticRegistry::VectorSpaceRegistry const *)
0x1800a2020  nop
0x1800a2021  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800a2025  test    rcx, rcx
0x1800a2028  jz      loc_1800A2376
0x1800a202e  mov     rax, [rcx]
0x1800a2031  mov     edx, r12d
0x1800a2034  call    qword ptr [rax+8]
0x1800a2037  test    al, al
0x1800a2039  jz      loc_1800A2376
0x1800a203f  xorps   xmm0, xmm0
0x1800a2042  movups  [rbp+57h+var_80], xmm0
0x1800a2046  movups  xmm1, xmmword ptr [rbx]
0x1800a2049  movaps  [rbp+57h+var_D0], xmm1
0x1800a204d  lea     r8, [rbp+57h+var_D0]
0x1800a2051  lea     rdx, [rbp+57h+var_80]
0x1800a2055  mov     rcx, rdi
0x1800a2058  call    ?GetModel@VectorSpaceRegistry@SemanticRegistry@asg@@QEBA?AV?$shared_ptr@$$CBUModelDescriptor@SemanticRegistry@asg@@@std@@UGuid@3@@Z; asg::SemanticRegistry::VectorSpaceRegistry::GetModel(asg::Guid)
0x1800a205d  nop
0x1800a205e  lea     rdx, [rbp+57h+var_60]
0x1800a2062  mov     rcx, qword ptr [rbp+57h+var_80]
0x1800a2066  call    ?QuantizationParameters@ModelDescriptor@SemanticRegistry@asg@@QEBA?AV?$optional@UEmbeddingQuantizationParameters@SemanticRegistry@asg@@@std@@XZ; asg::SemanticRegistry::ModelDescriptor::QuantizationParameters(void)
0x1800a206b  xorps   xmm0, xmm0
0x1800a206e  movups  [rbp+57h+var_D0], xmm0
0x1800a2072  mov     rcx, qword ptr [rbp+57h+var_70]
0x1800a2076  mov     rax, [rcx]
0x1800a2079  lea     r8, [rbp+57h+var_60]
0x1800a207d  lea     rdx, [rbp+57h+var_C0]
0x1800a2081  call    qword ptr [rax]
0x1800a2083  nop
0x1800a2084  xorps   xmm0, xmm0
0x1800a2087  movups  [rsp+120h+var_100], xmm0
0x1800a208c  mov     rbx, [rax]
0x1800a208f  mov     [rax], r13
0x1800a2092  mov     qword ptr [rsp+120h+var_100], rbx
0x1800a2097  mov     byte ptr [rsp+120h+var_100+8], 1
0x1800a209c  test    rbx, rbx
0x1800a209f  jz      loc_1800A236B
0x1800a20a5  cmp     [rbx+0C8h], r13b
0x1800a20ac  jnz     loc_1800A236B
0x1800a20b2  mov     rax, [rbx]
0x1800a20b5  mov     dl, 1
0x1800a20b7  mov     rcx, rbx
0x1800a20ba  call    qword ptr [rax+10h]
0x1800a20bd  mov     r14, [rax]
0x1800a20c0  mov     qword ptr [rbp+57h+var_D0], r14
0x1800a20c4  mov     rdi, [rax+8]
0x1800a20c8  mov     qword ptr [rbp+57h+var_D0+8], rdi
0x1800a20cc  mov     [rax], r13
0x1800a20cf  mov     [rax+8], r13
0x1800a20d3  mov     esi, 0FFFFFFFFh
0x1800a20d8  mov     eax, esi
0x1800a20da  lock xadd [rbx+8], eax
0x1800a20df  cmp     eax, 1
0x1800a20e2  jnz     short loc_1800A2108
0x1800a20e4  mov     rcx, [rbx+0D8h]
0x1800a20eb  test    rcx, rcx
0x1800a20ee  jz      short loc_1800A20FA
0x1800a20f0  mov     rax, [rcx]
0x1800a20f3  mov     rdx, rbx
0x1800a20f6  call    qword ptr [rax]
0x1800a20f8  jmp     short loc_1800A2108
0x1800a20fa  mov     rax, [rbx]
0x1800a20fd  mov     edx, 1
0x1800a2102  mov     rcx, rbx
0x1800a2105  call    qword ptr [rax]
0x1800a2107  nop
0x1800a2108  mov     rcx, [rbp+57h+var_C0]
0x1800a210c  test    rcx, rcx
0x1800a210f  jz      short loc_1800A2140
0x1800a2111  mov     eax, esi
0x1800a2113  lock xadd [rcx+8], eax
0x1800a2118  cmp     eax, 1
0x1800a211b  jnz     short loc_1800A2140
0x1800a211d  mov     r8, [rcx+0D8h]
0x1800a2124  test    r8, r8
0x1800a2127  jz      short loc_1800A2136
0x1800a2129  mov     rax, [r8]
0x1800a212c  mov     rdx, rcx
0x1800a212f  mov     rcx, r8
0x1800a2132  call    qword ptr [rax]
0x1800a2134  jmp     short loc_1800A2140
0x1800a2136  mov     rax, [rcx]
0x1800a2139  mov     edx, 1
0x1800a213e  call    qword ptr [rax]
0x1800a2140  test    r14, r14
0x1800a2143  jz      loc_1800A2397
0x1800a2149  mov     ecx, 28h ; '('; Size
0x1800a214e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a2153  mov     rbx, rax
0x1800a2156  mov     [rbp+57h+var_A8], rax
0x1800a215a  test    rax, rax
0x1800a215d  jz      loc_1800A2267
0x1800a2163  xorps   xmm0, xmm0
0x1800a2166  xor     eax, eax
0x1800a2168  movups  xmmword ptr [rbx], xmm0
0x1800a216b  movups  xmmword ptr [rbx+10h], xmm0
0x1800a216f  mov     [rbx+20h], rax
0x1800a2173  movdqa  [rsp+120h+var_100], xmm0
0x1800a2179  test    rdi, rdi
0x1800a217c  jz      short loc_1800A2182
0x1800a217e  lock inc dword ptr [rdi+8]
0x1800a2182  movaps  xmm0, [rbp+57h+var_D0]
0x1800a2186  movdqa  [rsp+120h+var_100], xmm0
0x1800a218c  lea     rax, [rsp+120h+var_100]
0x1800a2191  mov     [rbp+57h+var_A0], rax
0x1800a2195  xorps   xmm0, xmm0
0x1800a2198  movdqa  [rsp+120h+var_E0], xmm0
0x1800a219e  mov     rax, qword ptr [rbp+57h+var_80+8]
0x1800a21a2  test    rax, rax
0x1800a21a5  jz      short loc_1800A21AB
0x1800a21a7  lock inc dword ptr [rax+8]
0x1800a21ab  movaps  xmm0, [rbp+57h+var_80]
0x1800a21af  movdqa  [rsp+120h+var_E0], xmm0
0x1800a21b5  lea     rax, [rsp+120h+var_E0]
0x1800a21ba  mov     [rbp+57h+var_C0], rax
0x1800a21be  mov     [rbx], r12d
0x1800a21c1  mov     [rbx+8], r13
0x1800a21c5  mov     [rbx+10h], r13
0x1800a21c9  mov     rax, qword ptr [rsp+120h+var_E0]
0x1800a21ce  mov     [rbx+8], rax
0x1800a21d2  mov     rax, qword ptr [rsp+120h+var_E0+8]
0x1800a21d7  mov     [rbx+10h], rax
0x1800a21db  xorps   xmm0, xmm0
0x1800a21de  movdqa  [rsp+120h+var_E0], xmm0
0x1800a21e4  mov     [rbx+18h], r13
0x1800a21e8  mov     [rbx+20h], r13
0x1800a21ec  mov     rax, qword ptr [rsp+120h+var_100+8]
0x1800a21f1  test    rax, rax
0x1800a21f4  jz      short loc_1800A21FA
0x1800a21f6  lock inc dword ptr [rax+8]
0x1800a21fa  mov     rcx, qword ptr [rsp+120h+var_100]
0x1800a21ff  mov     [rbx+18h], rcx
0x1800a2203  mov     rax, qword ptr [rsp+120h+var_100+8]
0x1800a2208  mov     [rbx+20h], rax
0x1800a220c  test    rcx, rcx
0x1800a220f  jz      loc_1800A23BA
0x1800a2215  mov     rax, [rcx]
0x1800a2218  mov     edx, [rbx]
0x1800a221a  call    qword ptr [rax+8]
0x1800a221d  test    al, al
0x1800a221f  jz      loc_1800A23BA
0x1800a2225  mov     r14, qword ptr [rsp+120h+var_E0+8]
0x1800a222a  test    r14, r14
0x1800a222d  jz      short loc_1800A225B
0x1800a222f  mov     eax, esi
0x1800a2231  lock xadd [r14+8], eax
0x1800a2237  cmp     eax, 1
0x1800a223a  jnz     short loc_1800A225B
0x1800a223c  mov     rax, [r14]
0x1800a223f  mov     rcx, r14
0x1800a2242  call    qword ptr [rax]
0x1800a2244  mov     eax, esi
0x1800a2246  lock xadd [r14+0Ch], eax
0x1800a224c  cmp     eax, 1
0x1800a224f  jnz     short loc_1800A225B
0x1800a2251  mov     rax, [r14]
0x1800a2254  mov     rcx, r14
0x1800a2257  call    qword ptr [rax+8]
0x1800a225a  nop
0x1800a225b  lea     rcx, [rsp+120h+var_100]
0x1800a2260  call    ??1?$shared_ptr@V?$vector@UGuid@asg@@V?$allocator@UGuid@asg@@@std@@@std@@@std@@QEAA@XZ; std::shared_ptr<std::vector<asg::Guid>>::~shared_ptr<std::vector<asg::Guid>>(void)
0x1800a2265  jmp     short loc_1800A226A
0x1800a2267  mov     rbx, r13
0x1800a226a  mov     [r15], r13
0x1800a226d  mov     [r15+8], r13
0x1800a2271  mov     [rbp+57h+var_C0], rbx
0x1800a2275  mov     ecx, 18h; Size
0x1800a227a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800a227f  mov     [rbp+57h+var_C0], rax
0x1800a2283  test    rax, rax
0x1800a2286  jz      short loc_1800A22AC
0x1800a2288  xorps   xmm0, xmm0
0x1800a228b  movups  xmmword ptr [rax], xmm0
0x1800a228e  mov     dword ptr [rax+8], 1
0x1800a2295  mov     dword ptr [rax+0Ch], 1
0x1800a229c  lea     rcx, ??_7?$_Ref_count@VSingleImageEmbeddingPipeline@SemanticPipelines@asg@@@std@@6B@; const std::_Ref_count<asg::SemanticPipelines::SingleImageEmbeddingPipeline>::`vftable'
0x1800a22a3  mov     [rax], rcx
0x1800a22a6  mov     [rax+10h], rbx
0x1800a22aa  jmp     short loc_1800A22AF
0x1800a22ac  mov     rax, r13
0x1800a22af  mov     [r15], rbx
0x1800a22b2  mov     [r15+8], rax
0x1800a22b6  test    rdi, rdi
0x1800a22b9  jz      short loc_1800A22E5
0x1800a22bb  mov     eax, esi
0x1800a22bd  lock xadd [rdi+8], eax
0x1800a22c2  cmp     eax, 1
0x1800a22c5  jnz     short loc_1800A22E5
0x1800a22c7  mov     rax, [rdi]
0x1800a22ca  mov     rcx, rdi
0x1800a22cd  call    qword ptr [rax]
0x1800a22cf  mov     eax, esi
0x1800a22d1  lock xadd [rdi+0Ch], eax
0x1800a22d6  cmp     eax, 1
0x1800a22d9  jnz     short loc_1800A22E5
0x1800a22db  mov     rax, [rdi]
0x1800a22de  mov     rcx, rdi
0x1800a22e1  call    qword ptr [rax+8]
0x1800a22e4  nop
0x1800a22e5  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x1800a22e9  test    rbx, rbx
0x1800a22ec  jz      short loc_1800A2318
0x1800a22ee  mov     eax, esi
0x1800a22f0  lock xadd [rbx+8], eax
0x1800a22f5  cmp     eax, 1
0x1800a22f8  jnz     short loc_1800A2318
0x1800a22fa  mov     rax, [rbx]
0x1800a22fd  mov     rcx, rbx
0x1800a2300  call    qword ptr [rax]
0x1800a2302  mov     eax, esi
0x1800a2304  lock xadd [rbx+0Ch], eax
0x1800a2309  cmp     eax, 1
0x1800a230c  jnz     short loc_1800A2318
0x1800a230e  mov     rax, [rbx]
0x1800a2311  mov     rcx, rbx
0x1800a2314  call    qword ptr [rax+8]
0x1800a2317  nop
0x1800a2318  mov     rbx, qword ptr [rbp+57h+var_70+8]
0x1800a231c  test    rbx, rbx
0x1800a231f  jz      short loc_1800A2348
0x1800a2321  mov     eax, esi
0x1800a2323  lock xadd [rbx+8], eax
0x1800a2328  cmp     eax, 1
0x1800a232b  jnz     short loc_1800A2348
0x1800a232d  mov     rax, [rbx]
0x1800a2330  mov     rcx, rbx
0x1800a2333  call    qword ptr [rax]
0x1800a2335  lock xadd [rbx+0Ch], esi
0x1800a233a  cmp     esi, 1
0x1800a233d  jnz     short loc_1800A2348
0x1800a233f  mov     rdx, [rbx]
0x1800a2342  mov     rcx, rbx
0x1800a2345  call    qword ptr [rdx+8]
0x1800a2348  mov     rax, r15
0x1800a234b  mov     rcx, [rbp+57h+var_50]
0x1800a234f  xor     rcx, rsp; StackCookie
0x1800a2352  call    __security_check_cookie
0x1800a2357  add     rsp, 0E8h
0x1800a235e  pop     r15
0x1800a2360  pop     r14
0x1800a2362  pop     r13
0x1800a2364  pop     r12
0x1800a2366  pop     rdi
0x1800a2367  pop     rsi
0x1800a2368  pop     rbx
0x1800a2369  pop     rbp
0x1800a236a  retn
0x1800a236b  mov     ecx, 4
0x1800a2370  call    ?_Throw_future_error2@std@@YAXW4future_errc@1@@Z; std::_Throw_future_error2(std::future_errc)
0x1800a2376  lea     rdx, aACompatibleIma; "A compatible image model accessor facto"...
0x1800a237d  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800a2381  call    ??0invalid_argument@std@@QEAA@PEBD@Z; std::invalid_argument::invalid_argument(char const *)
0x1800a2386  lea     rdx, _TI3?AVinvalid_argument@std@@; pThrowInfo
0x1800a238d  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a2391  call    _CxxThrowException
0x1800a2397  lea     rdx, aFailedToCreate_1; "Failed to create an image model accesso"...
0x1800a239e  lea     rcx, [rsp+120h+var_100]; this
0x1800a23a3  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800a23a8  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800a23af  lea     rcx, [rsp+120h+var_100]; pExceptionObject
0x1800a23b4  call    _CxxThrowException
0x1800a23ba  lea     rdx, aPipelineSEmbed; "Pipeline's Embedding element type is no"...
0x1800a23c1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800a23c5  call    ??0runtime_error@std@@QEAA@PEBD@Z; std::runtime_error::runtime_error(char const *)
0x1800a23ca  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x1800a23d1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800a23d5  call    _CxxThrowException
```
