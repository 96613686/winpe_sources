# winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextRegionResultSink::OnEmbeddingGenerated(asg::SemanticPipelines::TextEmbedding)

- ea: `0x180065270`
- end: `0x1800654cb`
- name: `?OnEmbeddingGenerated@TextRegionResultSink@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UEAA_NUTextEmbedding@SemanticPipelines@asg@@@Z`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x180003bd0`
- `0x180009820`
- `0x18000d230`
- `0x180032070`
- `0x180065270`
- `0x1800657f0`
- `0x18006fdf0`
- `0x1801f97e0`
- `0x180242120`

## string_xrefs

- `0x180065499`: `OnEmbeddingGenerated() called after completion.`
- `0x18006544f`: `Already at max embedding count.`
- `0x18006543e`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextRegionResultSink.cpp`
- `0x180065488`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\TextRegionResultSink.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
_BOOL8 __fastcall winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextRegionResultSink::OnEmbeddingGenerated(
        __int64 a1,
        __int64 a2)
{
  __int64 v4; // rdx
  signed __int32 v5; // eax
  signed __int32 v6; // ett
  unsigned __int128 v7; // kr00_16
  bool v8; // si
  volatile signed __int32 *v9; // rbx
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  _OWORD v13[2]; // [rsp+30h] [rbp-29h] BYREF
  _OWORD pExceptionObject[2]; // [rsp+50h] [rbp-9h] BYREF
  __int128 v15; // [rsp+70h] [rbp+17h] BYREF
  __int64 v16; // [rsp+80h] [rbp+27h]
  __int64 v17; // [rsp+C0h] [rbp+67h] BYREF
  __int64 v18; // [rsp+C8h] [rbp+6Fh]
  __int64 v19; // [rsp+D0h] [rbp+77h] BYREF

  v18 = a2;
  if ( *(_BYTE *)(a1 + 48) )
  {
    LODWORD(v15) = 44;
    *((_QWORD *)&v15 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextRegionResultSink.cpp";
    v16 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v13, L"OnEmbeddingGenerated() called after completion.");
    winrt::hresult_illegal_method_call::hresult_illegal_method_call(
      (winrt::hresult_illegal_method_call *)pExceptionObject,
      (const struct winrt::param::hstring *)v13,
      (const struct winrt::impl::slim_source_location *)&v15);
    throw (winrt::hresult_illegal_method_call *)pExceptionObject;
  }
  if ( *(_QWORD *)(a1 + 40) == *(_QWORD *)(a1 + 32) )
  {
    LODWORD(v15) = 49;
    *((_QWORD *)&v15 + 1) = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\TextRegionResultSink.cpp";
    v16 = 0;
    winrt::param::hstring::hstring((winrt::param::hstring *)v13, L"Already at max embedding count.");
    winrt::hresult_illegal_method_call::hresult_illegal_method_call(
      (winrt::hresult_illegal_method_call *)pExceptionObject,
      (const struct winrt::param::hstring *)v13,
      (const struct winrt::impl::slim_source_location *)&v15);
    throw (winrt::hresult_illegal_method_call *)pExceptionObject;
  }
  v13[0] = *(_OWORD *)(a2 + 24);
  *(_QWORD *)(a2 + 24) = 0;
  *(_QWORD *)(a2 + 32) = 0;
  pExceptionObject[0] = *(_OWORD *)a2;
  v15 = *(_OWORD *)(a1 + 8);
  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeTextEmbedding(
    (unsigned int)&v17,
    (unsigned int)&v15,
    a1 + 24,
    (unsigned int)pExceptionObject,
    (__int64)v13);
  v13[0] = 0;
  v4 = *(_QWORD *)(a1 + 88);
  if ( v4 && (v5 = *(_DWORD *)(v4 + 8)) != 0 )
  {
    while ( 1 )
    {
      v6 = v5;
      v5 = _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 8), v5 + 1, v5);
      if ( v6 == v5 )
        break;
      if ( !v5 )
        goto LABEL_7;
    }
    v11 = *(_QWORD *)(a1 + 80);
    *(_QWORD *)&v13[0] = v11;
    v12 = *(_QWORD *)(a1 + 88);
    *((_QWORD *)&v13[0] + 1) = v12;
    v7 = __PAIR128__(v12, v11);
  }
  else
  {
LABEL_7:
    v7 = v13[0];
  }
  if ( (_QWORD)v7 )
  {
    v19 = v17;
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession::AddRegionEmbeddingToItem(
      v7,
      a1 + 24,
      &v19);
  }
  std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_one_at_back<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>(
    (__int64 **)(a1 + 56),
    &v17);
  v8 = ++*(_QWORD *)(a1 + 40) < *(_QWORD *)(a1 + 32);
  if ( *((_QWORD *)&v7 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v7 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (***((void (__fastcall ****)(_QWORD))&v7 + 1))(*((_QWORD *)&v7 + 1));
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v7 + 1) + 12LL), 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v7 + 1) + 8LL))(*((_QWORD *)&v7 + 1));
    }
  }
  if ( v17 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v17);
  v9 = *(volatile signed __int32 **)(a2 + 32);
  if ( v9 )
  {
    if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
      if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
    }
  }
  return v8;
}

```

## disassembly

```asm
0x180065270  mov     [rsp-8+arg_18], rbx
0x180065275  mov     [rsp-8+arg_8], rdx
0x18006527a  push    rbp
0x18006527b  push    rsi
0x18006527c  push    rdi
0x18006527d  push    r14
0x18006527f  push    r15
0x180065281  lea     rbp, [rsp-37h]
0x180065286  sub     rsp, 90h
0x18006528d  mov     r14, rdx
0x180065290  mov     rdi, rcx
0x180065293  cmp     byte ptr [rcx+30h], 0
0x180065297  jnz     loc_180065481
0x18006529d  mov     rax, [rcx+20h]
0x1800652a1  cmp     [rcx+28h], rax
0x1800652a5  jz      loc_180065437
0x1800652ab  mov     rax, [rdx+18h]
0x1800652af  mov     qword ptr [rbp+57h+var_80], rax
0x1800652b3  mov     rax, [rdx+20h]
0x1800652b7  mov     qword ptr [rbp+57h+var_80+8], rax
0x1800652bb  xor     eax, eax
0x1800652bd  mov     [rdx+18h], rax
0x1800652c1  mov     [rdx+20h], rax
0x1800652c5  movups  xmm0, xmmword ptr [rdx]
0x1800652c8  movaps  [rbp+57h+pExceptionObject], xmm0
0x1800652cc  movups  xmm1, xmmword ptr [rcx+8]
0x1800652d0  movaps  [rbp+57h+var_40], xmm1
0x1800652d4  lea     rax, [rbp+57h+var_80]
0x1800652d8  mov     [rsp+0B0h+var_90], rax
0x1800652dd  lea     r9, [rbp+57h+pExceptionObject]
0x1800652e1  lea     r8, [rcx+18h]
0x1800652e5  lea     rdx, [rbp+57h+var_40]
0x1800652e9  lea     rcx, [rbp+57h+arg_0]
0x1800652ed  call    ?MakeTextEmbedding@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@YA?AUEmbedding@234567@Uguid@7@AEBUhstring@7@UTextSlice@SemanticPipelines@asg@@V?$shared_ptr@UIModelEmbedding@SemanticPipelines@asg@@@std@@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::MakeTextEmbedding(winrt::guid,winrt::hstring const &,asg::SemanticPipelines::TextSlice,std::shared_ptr<asg::SemanticPipelines::IModelEmbedding>)
0x1800652f2  nop
0x1800652f3  xorps   xmm0, xmm0
0x1800652f6  movdqu  [rbp+57h+var_80], xmm0
0x1800652fb  mov     rdx, [rdi+58h]
0x1800652ff  test    rdx, rdx
0x180065302  jz      short loc_180065322
0x180065304  mov     eax, [rdx+8]
0x180065307  test    eax, eax
0x180065309  jz      short loc_180065322
0x18006530b  nop     dword ptr [rax+rax+00h]
0x180065310  lea     ecx, [rax+1]
0x180065313  lock cmpxchg [rdx+8], ecx
0x180065318  jz      loc_180065422
0x18006531e  test    eax, eax
0x180065320  jnz     short loc_180065310
0x180065322  mov     rsi, qword ptr [rbp+57h+var_80]
0x180065326  mov     rbx, qword ptr [rbp+57h+var_80+8]
0x18006532a  test    rsi, rsi
0x18006532d  jz      short loc_180065359
0x18006532f  mov     rcx, [rbp+57h+arg_0]
0x180065333  mov     [rbp+57h+arg_10], rcx
0x180065337  test    rcx, rcx
0x18006533a  jz      short loc_180065349
0x18006533c  mov     rax, [rcx]
0x18006533f  mov     rax, [rax+8]
0x180065343  call    cs:__guard_dispatch_icall_fptr
0x180065349  lea     r8, [rbp+57h+arg_10]
0x18006534d  lea     rdx, [rdi+18h]
0x180065351  mov     rcx, rsi
0x180065354  call    ?AddRegionEmbeddingToItem@ItemEmbeddingGenerationSession@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAAXAEBUhstring@8@UEmbedding@345678@@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ItemEmbeddingGenerationSession::AddRegionEmbeddingToItem(winrt::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding)
0x180065359  lea     rcx, [rdi+38h]
0x18006535d  lea     rdx, [rbp+57h+arg_0]
0x180065361  call    ??$_Emplace_one_at_back@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@?$vector@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@V?$allocator@UEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@std@@@std@@AEAAAEAUEmbedding@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@$$QEAU2345678@@Z; std::vector<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>::_Emplace_one_at_back<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding>(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::Embedding &&)
0x180065366  inc     qword ptr [rdi+28h]
0x18006536a  mov     rax, [rdi+28h]
0x18006536e  cmp     rax, [rdi+20h]
0x180065372  setb    sil
0x180065376  mov     edi, 0FFFFFFFFh
0x18006537b  test    rbx, rbx
0x18006537e  jz      short loc_1800653B8
0x180065380  mov     eax, edi
0x180065382  lock xadd [rbx+8], eax
0x180065387  cmp     eax, 1
0x18006538a  jnz     short loc_1800653B8
0x18006538c  mov     rax, [rbx]
0x18006538f  mov     rcx, rbx
0x180065392  mov     rax, [rax]
0x180065395  call    cs:__guard_dispatch_icall_fptr
0x18006539b  mov     eax, edi
0x18006539d  lock xadd [rbx+0Ch], eax
0x1800653a2  cmp     eax, 1
0x1800653a5  jnz     short loc_1800653B8
0x1800653a7  mov     rax, [rbx]
0x1800653aa  mov     rcx, rbx
0x1800653ad  mov     rax, [rax+8]
0x1800653b1  call    cs:__guard_dispatch_icall_fptr
0x1800653b7  nop
0x1800653b8  cmp     [rbp+57h+arg_0], 0
0x1800653bd  jz      short loc_1800653C9
0x1800653bf  lea     rcx, [rbp+57h+arg_0]
0x1800653c3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800653c8  nop
0x1800653c9  mov     rbx, [r14+20h]
0x1800653cd  test    rbx, rbx
0x1800653d0  jz      short loc_180065407
0x1800653d2  mov     eax, edi
0x1800653d4  lock xadd [rbx+8], eax
0x1800653d9  cmp     eax, 1
0x1800653dc  jnz     short loc_180065407
0x1800653de  mov     rax, [rbx]
0x1800653e1  mov     rcx, rbx
0x1800653e4  mov     rax, [rax]
0x1800653e7  call    cs:__guard_dispatch_icall_fptr
0x1800653ed  lock xadd [rbx+0Ch], edi
0x1800653f2  cmp     edi, 1
0x1800653f5  jnz     short loc_180065407
0x1800653f7  mov     rdx, [rbx]
0x1800653fa  mov     rcx, rbx
0x1800653fd  mov     rax, [rdx+8]
0x180065401  call    cs:__guard_dispatch_icall_fptr
0x180065407  movzx   eax, sil
0x18006540b  mov     rbx, [rsp+0B0h+arg_18]
0x180065413  add     rsp, 90h
0x18006541a  pop     r15
0x18006541c  pop     r14
0x18006541e  pop     rdi
0x18006541f  pop     rsi
0x180065420  pop     rbp
0x180065421  retn
0x180065422  mov     rsi, [rdi+50h]
0x180065426  mov     qword ptr [rbp+57h+var_80], rsi
0x18006542a  mov     rbx, [rdi+58h]
0x18006542e  mov     qword ptr [rbp+57h+var_80+8], rbx
0x180065432  jmp     loc_18006532A
0x180065437  mov     dword ptr [rbp+57h+var_40], 31h ; '1'
0x18006543e  lea     rax, aCW1SSrcSemanti_45; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x180065445  mov     qword ptr [rbp+57h+var_40+8], rax
0x180065449  xor     eax, eax
0x18006544b  mov     [rbp+57h+var_30], rax
0x18006544f  lea     rdx, aAlreadyAtMaxEm; "Already at max embedding count."
0x180065456  lea     rcx, [rbp+57h+var_80]; this
0x18006545a  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18006545f  lea     r8, [rbp+57h+var_40]; struct winrt::impl::slim_source_location *
0x180065463  lea     rdx, [rbp+57h+var_80]; struct winrt::param::hstring *
0x180065467  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18006546b  call    ??0hresult_illegal_method_call@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180065470  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x180065477  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18006547b  call    _CxxThrowException
0x180065481  mov     dword ptr [rbp+57h+var_40], 2Ch ; ','
0x180065488  lea     rax, aCW1SSrcSemanti_45; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18006548f  mov     qword ptr [rbp+57h+var_40+8], rax
0x180065493  xor     eax, eax
0x180065495  mov     [rbp+57h+var_30], rax
0x180065499  lea     rdx, aOnembeddinggen; "OnEmbeddingGenerated() called after com"...
0x1800654a0  lea     rcx, [rbp+57h+var_80]; this
0x1800654a4  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x1800654a9  lea     r8, [rbp+57h+var_40]; struct winrt::impl::slim_source_location *
0x1800654ad  lea     rdx, [rbp+57h+var_80]; struct winrt::param::hstring *
0x1800654b1  lea     rcx, [rbp+57h+pExceptionObject]; this
0x1800654b5  call    ??0hresult_illegal_method_call@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_illegal_method_call::hresult_illegal_method_call(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800654ba  lea     rdx, _TI2?AUhresult_illegal_method_call@winrt@@; pThrowInfo
0x1800654c1  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x1800654c5  call    _CxxThrowException
```
