# ??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003d880`
- end: `0x18003da30`
- name: `??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18003da30`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003d800`
- `0x18003d880`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003d9b0`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d8bb`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsEmbeddingsGeneratorAvailableForOptions_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsEmbeddingsGeneratorAvailableForOptions_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
        __int64 a1,
        _QWORD **a2)
{
  signed __int64 v3; // rbx
  unsigned __int8 v4; // di
  int v5; // eax
  _QWORD v7[2]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD *v8; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v9[4]; // [rsp+38h] [rbp-48h] BYREF
  const wchar_t *v10; // [rsp+48h] [rbp-38h]
  __int64 *v11; // [rsp+50h] [rbp-30h] BYREF
  signed __int64 v12[2]; // [rsp+58h] [rbp-28h] BYREF
  _BYTE v13[8]; // [rsp+68h] [rbp-18h] BYREF

  v9[0] = 1;
  v9[1] = 73;
  v10 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v8 = v9;
  v12[0] = 0;
  LODWORD(v7[0]) = 6148;
  v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>,
    (__int64)v12);
  if ( (int)v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, v7);
  }
  v3 = v12[0];
  v7[0] = v12[0];
  if ( v12[0]
    && (v11 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int64 **))v12[0])(
          v12[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v11),
        v11) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
    v11 = &qword_180086A58;
    _InterlockedIncrement64(&qword_180086A58);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>,
            v12[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A60);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailableForOptions'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>);
    _InterlockedDecrement64(&qword_180086A58);
  }
  else
  {
    v13[0] = 0;
    LODWORD(v12[0]) = 1214;
    v12[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _BYTE *))(*(_QWORD *)v3 + 48LL))(v3, **a2, v13);
    if ( v5 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v5, v12);
    }
    v4 = v13[0];
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v7);
  return v4;
}

```

## disassembly

```asm
0x18003d880  mov     [rsp-8+arg_0], rbx
0x18003d885  mov     [rsp-8+arg_10], rsi
0x18003d88a  mov     [rsp-8+arg_18], rdi
0x18003d88f  push    rbp
0x18003d890  mov     rbp, rsp
0x18003d893  sub     rsp, 80h
0x18003d89a  mov     rax, cs:__security_cookie
0x18003d8a1  xor     rax, rsp
0x18003d8a4  mov     [rbp+var_10], rax
0x18003d8a8  mov     rdi, rdx
0x18003d8ab  xor     esi, esi
0x18003d8ad  mov     [rbp+var_48], 1
0x18003d8b4  mov     [rbp+var_44], 49h ; 'I'
0x18003d8bb  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003d8c2  mov     [rbp+var_38], rax
0x18003d8c6  lea     rax, [rbp+var_48]
0x18003d8ca  mov     [rbp+var_50], rax
0x18003d8ce  mov     [rbp+var_28], rsi
0x18003d8d2  mov     dword ptr [rbp+var_60], 1804h
0x18003d8d9  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d8e0  mov     [rbp+var_58], rax
0x18003d8e4  lea     r9, [rbp+var_28]
0x18003d8e8  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d8ef  lea     rdx, [rbp+var_50]
0x18003d8f3  lea     rcx, [rbp+var_30]
0x18003d8f7  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003d8fc  mov     ecx, dword ptr [rbp+var_30]
0x18003d8ff  test    ecx, ecx
0x18003d901  js      loc_18003DA23
0x18003d907  mov     rbx, [rbp+var_28]
0x18003d90b  mov     [rbp+var_60], rbx
0x18003d90f  test    rbx, rbx
0x18003d912  jz      loc_18003D9A5
0x18003d918  mov     [rbp+var_30], rsi
0x18003d91c  mov     rax, [rbx]
0x18003d91f  lea     r8, [rbp+var_30]
0x18003d923  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003d92a  mov     rcx, rbx
0x18003d92d  mov     rax, [rax]
0x18003d930  call    cs:__guard_dispatch_icall_fptr
0x18003d936  mov     rax, [rbp+var_30]
0x18003d93a  mov     [rbp+var_30], rax
0x18003d93e  test    rax, rax
0x18003d941  jz      short loc_18003D9A5
0x18003d943  lea     rcx, [rbp+var_30]
0x18003d947  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d94c  lea     rax, qword_180086A58
0x18003d953  mov     [rbp+var_30], rax
0x18003d957  lock inc cs:qword_180086A58
0x18003d95f  mov     rdx, [rbp+var_28]
0x18003d963  xor     eax, eax
0x18003d965  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d96e  jnz     short loc_18003D989
0x18003d970  mov     [rbp+var_60], rsi
0x18003d974  lea     rdx, stru_180086A60; ListEntry
0x18003d97b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003d982  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003d987  mov     ebx, esi
0x18003d989  lea     rdx, ??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d990  mov     rcx, rdi
0x18003d993  call    ??R_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@345678@@Z@QEBA@AEBUISemanticTextIndexStoreStatics2@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailableForOptions(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2 const &)
0x18003d998  movzx   edi, al
0x18003d99b  lock dec cs:qword_180086A58
0x18003d9a3  jmp     short loc_18003D9DD
0x18003d9a5  mov     [rbp+var_18], 0
0x18003d9a9  mov     dword ptr [rbp+var_28], 4BEh
0x18003d9b0  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d9b7  mov     [rbp+var_20], rax
0x18003d9bb  mov     rdx, [rdi]
0x18003d9be  mov     rax, [rbx]
0x18003d9c1  lea     r8, [rbp+var_18]
0x18003d9c5  mov     rdx, [rdx]
0x18003d9c8  mov     rcx, rbx
0x18003d9cb  mov     rax, [rax+30h]
0x18003d9cf  call    cs:__guard_dispatch_icall_fptr
0x18003d9d5  test    eax, eax
0x18003d9d7  js      short loc_18003DA14
0x18003d9d9  movzx   edi, [rbp+var_18]
0x18003d9dd  test    rbx, rbx
0x18003d9e0  jz      short loc_18003D9EB
0x18003d9e2  lea     rcx, [rbp+var_60]
0x18003d9e6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d9eb  movzx   eax, dil
0x18003d9ef  mov     rcx, [rbp+var_10]
0x18003d9f3  xor     rcx, rsp; StackCookie
0x18003d9f6  call    __security_check_cookie
0x18003d9fb  lea     r11, [rsp+80h+var_s0]
0x18003da03  mov     rbx, [r11+10h]
0x18003da07  mov     rsi, [r11+20h]
0x18003da0b  mov     rdi, [r11+28h]
0x18003da0f  mov     rsp, r11
0x18003da12  pop     rbp
0x18003da13  retn
0x18003da14  lfence
0x18003da17  lea     rdx, [rbp+var_28]
0x18003da1b  mov     ecx, eax
0x18003da1d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003da23  lfence
0x18003da26  lea     rdx, [rbp+var_60]
0x18003da2a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
