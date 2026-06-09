# ??$InvokeDbMethod@V_lambda_1_@?1??GetIndexingState2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUItemIndexingState2@56789winrt@@Uguid@winrt@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??GetIndexingState2@01234567@QEAA?AUItemIndexingState2@234567@Uguid@7@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z

- ea: `0x18004f800`
- end: `0x18004f9cf`
- name: `??$InvokeDbMethod@V_lambda_1_@?1??GetIndexingState2@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA?AUItemIndexingState2@56789winrt@@Uguid@winrt@@@Z@$$A6AXX_E@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEAA?A_P$$QEAV_lambda_1_@?1??GetIndexingState2@01234567@QEAA?AUItemIndexingState2@234567@Uguid@7@@Z@$$Q6AXX_EAEBUsource_location@std@@@Z`
- size: `463`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180051fa0`

## callees

- `0x180003df0`
- `0x18000d230`
- `0x18002f2e0`
- `0x18002f8e0`
- `0x18004f800`
- `0x180078ed0`
- `0x180192df0`
- `0x1801939e0`
- `0x1801d2b20`
- `0x1801f97e0`

## string_xrefs

- `0x18004f950`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18004f9ab`: `C:\__w\1\s\src\SemanticIndex\internal\winrt\aifabric_compatibility\IndexStoreCommon.h`
- `0x18004f9b7`: `struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2 __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Com`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ___InvokeDbMethod_V_lambda_1___1__GetIndexingState2___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AUItemIndexingState2_56789winrt__Uguid_winrt___Z___A6AXX_E___IndexStoreCommon_VSemanticIndexStore_SemanticIndex_asg__UTextEmbeddingsGenerator_Compatibility_AiFabric_2Asg_Microsoft_winrt__U4implementation_562789_U4562789_U4implementation_562789__implementation_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__AEAA_A_P__QEAV_lambda_1___1__GetIndexingState2_01234567_QEAA_AUItemIndexingState2_234567_Uguid_7__Z___Q6AXX_EAEBUsource_location_std___Z(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v7; // r8
  int IndexingState; // ebx
  asg::SemanticIndex::SemanticIndexStore *v9; // rdi
  __int128 v10; // xmm0
  char v11; // cl
  int v12; // ebx
  int v13; // ebx
  __int64 result; // rax
  __int64 v15; // rbx
  __int64 v16; // rax
  __int64 v17; // rax
  unsigned int *v18; // rax
  _BYTE v19[24]; // [rsp+20h] [rbp-E8h] BYREF
  _Mtx_t v20; // [rsp+40h] [rbp-C8h] BYREF
  char v21; // [rsp+48h] [rbp-C0h]
  _OWORD v22[2]; // [rsp+50h] [rbp-B8h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-98h] BYREF
  _BYTE v24[24]; // [rsp+88h] [rbp-80h] BYREF
  _BYTE v25[32]; // [rsp+A0h] [rbp-68h] BYREF
  _BYTE v26[64]; // [rsp+C0h] [rbp-48h] BYREF
  __int64 v28; // [rsp+128h] [rbp+20h] BYREF

  winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::EnsureNotCorrupted(a1);
  LOBYTE(v7) = 1;
  try
  {
    winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(
      *a3,
      &v20,
      v7);
    IndexingState = asg::SemanticIndex::SemanticIndexStore::GetIndexingState(*(_QWORD *)(*a3 + 168LL), a3[1]);
    v9 = *(asg::SemanticIndex::SemanticIndexStore **)(*a3 + 168LL);
    v22[0] = *(_OWORD *)(*((_QWORD *)v9 + 22) + 200LL);
    if ( asg::SemanticIndex::SemanticIndexStore::IsPreviousGraphEmpty(v9) )
    {
      v19[16] = 0;
      v10 = *(_OWORD *)v19;
      v11 = 0;
    }
    else
    {
      v10 = *(_OWORD *)(*((_QWORD *)v9 + 24) + 200LL);
      v19[16] = 1;
      v11 = 1;
    }
    if ( IndexingState )
    {
      v12 = IndexingState - 1;
      if ( !v12 )
      {
        *(_DWORD *)v19 = 2;
        v10 = v22[0];
        v19[20] = 0;
LABEL_15:
        *(_OWORD *)&v19[4] = v10;
        *(_OWORD *)a2 = *(_OWORD *)v19;
        *(_QWORD *)(a2 + 16) = *(_QWORD *)&v19[16];
        if ( v21 )
          Mtx_unlock(v20);
        return a2;
      }
      v13 = v12 - 1;
      if ( !v13 )
      {
        if ( !v11 )
        {
          *(_QWORD *)v19 = 0x1600000711LL;
          *(_QWORD *)&v19[8] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
          *(_QWORD *)&v19[16] = "struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ItemIndexingState2"
                                " __cdecl winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::"
                                "IndexStoreCommon<class asg::SemanticIndex::SemanticIndexStore,struct winrt::Microsoft::A"
                                "sg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,struct winrt::Micros"
                                "oft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerato"
                                "r,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGe"
                                "nerator,struct winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementa"
                                "tion::TextEmbeddingsGenerator>::MakeIndexingState(enum asg::SemanticIndex::ItemIndexingS"
                                "tatus,const struct asg::Guid &,const class std::optional<struct asg::Guid> &)";
          asg::details::AsgAssertFail(v19);
        }
        *(_DWORD *)v19 = 4;
        v19[20] = 1;
        goto LABEL_15;
      }
      if ( v13 != 1 )
      {
        *(_DWORD *)v19 = 1818;
        *(_QWORD *)&v19[8] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
        *(_QWORD *)&v19[16] = 0;
        winrt::param::hstring::hstring((winrt::param::hstring *)v22, L"Invalid indexing state");
        winrt::hresult_invalid_argument::hresult_invalid_argument(
          (winrt::hresult_invalid_argument *)pExceptionObject,
          (const struct winrt::param::hstring *)v22,
          (const struct winrt::impl::slim_source_location *)v19);
        throw (winrt::hresult_invalid_argument *)pExceptionObject;
      }
      *(_DWORD *)v19 = 4;
      v19[20] = 1;
    }
    else
    {
      *(_DWORD *)v19 = 0;
      v19[20] = 0;
    }
    v10 = `asg::EmptyGuid'::`2'::empty;
    goto LABEL_15;
  }
  catch ( ... )
  {
    v15 = (unsigned int)asg::SemanticIndex::ResultFromCaughtSemanticIndexException();
    asg::SemanticIndex::LogCaughtSemanticIndexException(v26, v15, a5);
    if ( (_DWORD)v15 == -2147023538 )
      winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::SetCorruptedAndClose(a1);
    *(_DWORD *)v19 = 2239;
    *(_QWORD *)&v19[8] = "C:\\__w\\1\\s\\src\\SemanticIndex\\internal\\winrt\\aifabric_compatibility\\IndexStoreCommon.h";
    *(_QWORD *)&v19[16] = 0;
    v16 = asg::LogStringView::View(v26, v22);
    v17 = asg::as_u16string_view(&v20, v16);
    winrt::param::hstring::hstring(v25, v17);
    v18 = (unsigned int *)winrt::hresult::hresult((winrt::hresult *)&v28, v15);
    winrt::hresult_error::hresult_error(v24, *v18, v25, v19);
    throw (winrt::hresult_error *)v24;
  }
  return result;
}

```

## disassembly

```asm
0x18004f800  mov     [rsp+arg_8], rbx
0x18004f805  mov     [rsp+arg_10], rsi
0x18004f80a  mov     [rsp+arg_18], r9
0x18004f80f  mov     [rsp+arg_0], rcx
0x18004f814  push    rdi
0x18004f815  sub     rsp, 100h
0x18004f81c  mov     rdi, r8
0x18004f81f  mov     rsi, rdx
0x18004f822  call    ?EnsureNotCorrupted@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UImageEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@UTextEmbeddingsGenerator@562789@UTextEmbeddingsGenerator@implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBAXXZ; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::ImageEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::EnsureNotCorrupted(void)
0x18004f827  nop
0x18004f828  mov     r8b, 1
0x18004f82b  lea     rdx, [rsp+108h+var_C8]
0x18004f830  mov     rcx, [rdi]
0x18004f833  call    ?AcquireLock@?$IndexStoreCommon@VSemanticIndexStore@SemanticIndex@asg@@UTextEmbeddingsGenerator@Compatibility@AiFabric@2Asg@Microsoft@winrt@@U4implementation@562789@U4562789@U4implementation@562789@@implementation@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@AEBA?AV?$unique_lock@Vrecursive_mutex@std@@@std@@_N@Z; winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::IndexStoreCommon<asg::SemanticIndex::SemanticIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::TextEmbeddingsGenerator,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::implementation::TextEmbeddingsGenerator>::AcquireLock(bool)
0x18004f838  nop
0x18004f839  mov     rcx, [rdi]
0x18004f83c  mov     rdx, [rdi+8]
0x18004f840  mov     rcx, [rcx+0A8h]
0x18004f847  call    ?GetIndexingState@SemanticIndexStore@SemanticIndex@asg@@QEBA?AW4ItemIndexingStatus@23@AEBUGuid@3@@Z; asg::SemanticIndex::SemanticIndexStore::GetIndexingState(asg::Guid const &)
0x18004f84c  mov     ebx, eax
0x18004f84e  mov     rax, [rdi]
0x18004f851  mov     rdi, [rax+0A8h]
0x18004f858  mov     rax, [rdi+0B0h]
0x18004f85f  movups  xmm0, xmmword ptr [rax+0C8h]
0x18004f866  movups  [rsp+108h+var_B8], xmm0
0x18004f86b  mov     rcx, rdi; this
0x18004f86e  call    ?IsPreviousGraphEmpty@SemanticIndexStore@SemanticIndex@asg@@QEBA_NXZ; asg::SemanticIndex::SemanticIndexStore::IsPreviousGraphEmpty(void)
0x18004f873  test    al, al
0x18004f875  jz      short loc_18004F885
0x18004f877  mov     byte ptr [rsp+108h+var_D8], 0
0x18004f87c  movups  xmm0, [rsp+108h+var_E8]
0x18004f881  xor     cl, cl
0x18004f883  jmp     short loc_18004F89A
0x18004f885  mov     rax, [rdi+0C0h]
0x18004f88c  movups  xmm0, xmmword ptr [rax+0C8h]
0x18004f893  mov     byte ptr [rsp+108h+var_D8], 1
0x18004f898  mov     cl, 1
0x18004f89a  mov     eax, dword ptr [rsp+108h+var_D8]
0x18004f89e  mov     dword ptr [rsp+108h+var_D8], eax
0x18004f8a2  test    ebx, ebx
0x18004f8a4  jz      short loc_18004F8F3
0x18004f8a6  sub     ebx, 1
0x18004f8a9  jz      short loc_18004F8DF
0x18004f8ab  sub     ebx, 1
0x18004f8ae  jz      short loc_18004F8C8
0x18004f8b0  cmp     ebx, 1
0x18004f8b3  jnz     loc_18004F948
0x18004f8b9  mov     dword ptr [rsp+108h+var_E8], 4
0x18004f8c1  mov     byte ptr [rsp+108h+var_D8+4], 1
0x18004f8c6  jmp     short loc_18004F900
0x18004f8c8  test    cl, cl
0x18004f8ca  jz      loc_18004F99B
0x18004f8d0  mov     dword ptr [rsp+108h+var_E8], 4
0x18004f8d8  mov     byte ptr [rsp+108h+var_D8+4], 1
0x18004f8dd  jmp     short loc_18004F907
0x18004f8df  mov     dword ptr [rsp+108h+var_E8], 2
0x18004f8e7  movups  xmm0, [rsp+108h+var_B8]
0x18004f8ec  mov     byte ptr [rsp+108h+var_D8+4], 0
0x18004f8f1  jmp     short loc_18004F907
0x18004f8f3  mov     dword ptr [rsp+108h+var_E8], 0
0x18004f8fb  mov     byte ptr [rsp+108h+var_D8+4], 0
0x18004f900  movups  xmm0, cs:?empty@?1??EmptyGuid@asg@@YA?AUGuid@2@XZ@4U32@B; asg::Guid const `asg::EmptyGuid(void)'::`2'::empty
0x18004f907  movups  [rsp+108h+var_E8+4], xmm0
0x18004f90c  movups  xmm0, [rsp+108h+var_E8]
0x18004f911  movups  xmmword ptr [rsi], xmm0
0x18004f914  movsd   xmm1, [rsp+108h+var_D8]
0x18004f91a  movsd   qword ptr [rsi+10h], xmm1
0x18004f91f  cmp     [rsp+108h+var_C0], 0
0x18004f924  jz      short loc_18004F930
0x18004f926  mov     rcx, [rsp+108h+var_C8]; _Mtx_t
0x18004f92b  call    _Mtx_unlock
0x18004f930  mov     rax, rsi
0x18004f933  lea     r11, [rsp+108h+var_8]
0x18004f93b  mov     rbx, [r11+18h]
0x18004f93f  mov     rsi, [r11+20h]
0x18004f943  mov     rsp, r11
0x18004f946  pop     rdi
0x18004f947  retn
0x18004f948  mov     dword ptr [rsp+108h+var_E8], 71Ah
0x18004f950  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18004f957  mov     qword ptr [rsp+108h+var_E8+8], rax
0x18004f95c  mov     [rsp+108h+var_D8], 0
0x18004f965  lea     rdx, aInvalidIndexin; "Invalid indexing state"
0x18004f96c  lea     rcx, [rsp+108h+var_B8]; this
0x18004f971  call    ??0hstring@param@winrt@@QEAA@QEB_W@Z; winrt::param::hstring::hstring(wchar_t const * const)
0x18004f976  lea     r8, [rsp+108h+var_E8]; struct winrt::impl::slim_source_location *
0x18004f97b  lea     rdx, [rsp+108h+var_B8]; struct winrt::param::hstring *
0x18004f980  lea     rcx, [rsp+108h+pExceptionObject]; this
0x18004f985  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x18004f98a  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x18004f991  lea     rcx, [rsp+108h+pExceptionObject]; pExceptionObject
0x18004f996  call    _CxxThrowException
0x18004f99b  mov     dword ptr [rsp+108h+var_E8], 711h
0x18004f9a3  mov     dword ptr [rsp+108h+var_E8+4], 16h
0x18004f9ab  lea     rax, aCW1SSrcSemanti_21; "C:\\__w\\1\\s\\src\\SemanticIndex\\inte"...
0x18004f9b2  mov     qword ptr [rsp+108h+var_E8+8], rax
0x18004f9b7  lea     rdx, aStructWinrtMic_16; "struct winrt::Microsoft::Asg::SemanticI"...
0x18004f9be  mov     [rsp+108h+var_D8], rdx
0x18004f9c3  lea     rcx, [rsp+108h+var_E8]
0x18004f9c8  call    ?AsgAssertFail@details@asg@@YAXUsource_location@std@@PEBD@Z; asg::details::AsgAssertFail(std::source_location,char const *)
```
