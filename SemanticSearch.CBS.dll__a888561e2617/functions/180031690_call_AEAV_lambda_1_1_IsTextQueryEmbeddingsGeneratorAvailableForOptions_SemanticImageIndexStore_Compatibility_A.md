# ??$call@AEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180031690`
- end: `0x180031840`
- name: `??$call@AEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180031840`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180031610`
- `0x180031690`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800317c0`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800316cb`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsTextQueryEmbeddingsGeneratorAvailableForOptions_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsTextQueryEmbeddingsGeneratorAvailableForOptions_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
  v9[1] = 74;
  v10 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v8 = v9;
  v12[0] = 0;
  LODWORD(v7[0]) = 6148;
  v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
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
    v11 = &qword_180086918;
    _InterlockedIncrement64(&qword_180086918);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
            v12[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086920);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsTextQueryEmbeddingsGeneratorAvailableForOptions'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>);
    _InterlockedDecrement64(&qword_180086918);
  }
  else
  {
    v13[0] = 0;
    LODWORD(v12[0]) = 786;
    v12[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v5 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _BYTE *))(*(_QWORD *)v3 + 72LL))(v3, **a2, v13);
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
0x180031690  mov     [rsp-8+arg_0], rbx
0x180031695  mov     [rsp-8+arg_10], rsi
0x18003169a  mov     [rsp-8+arg_18], rdi
0x18003169f  push    rbp
0x1800316a0  mov     rbp, rsp
0x1800316a3  sub     rsp, 80h
0x1800316aa  mov     rax, cs:__security_cookie
0x1800316b1  xor     rax, rsp
0x1800316b4  mov     [rbp+var_10], rax
0x1800316b8  mov     rdi, rdx
0x1800316bb  xor     esi, esi
0x1800316bd  mov     [rbp+var_48], 1
0x1800316c4  mov     [rbp+var_44], 4Ah ; 'J'
0x1800316cb  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800316d2  mov     [rbp+var_38], rax
0x1800316d6  lea     rax, [rbp+var_48]
0x1800316da  mov     [rbp+var_50], rax
0x1800316de  mov     [rbp+var_28], rsi
0x1800316e2  mov     dword ptr [rbp+var_60], 1804h
0x1800316e9  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800316f0  mov     [rbp+var_58], rax
0x1800316f4  lea     r9, [rbp+var_28]
0x1800316f8  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800316ff  lea     rdx, [rbp+var_50]
0x180031703  lea     rcx, [rbp+var_30]
0x180031707  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003170c  mov     ecx, dword ptr [rbp+var_30]
0x18003170f  test    ecx, ecx
0x180031711  js      loc_180031833
0x180031717  mov     rbx, [rbp+var_28]
0x18003171b  mov     [rbp+var_60], rbx
0x18003171f  test    rbx, rbx
0x180031722  jz      loc_1800317B5
0x180031728  mov     [rbp+var_30], rsi
0x18003172c  mov     rax, [rbx]
0x18003172f  lea     r8, [rbp+var_30]
0x180031733  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003173a  mov     rcx, rbx
0x18003173d  mov     rax, [rax]
0x180031740  call    cs:__guard_dispatch_icall_fptr
0x180031746  mov     rax, [rbp+var_30]
0x18003174a  mov     [rbp+var_30], rax
0x18003174e  test    rax, rax
0x180031751  jz      short loc_1800317B5
0x180031753  lea     rcx, [rbp+var_30]
0x180031757  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003175c  lea     rax, qword_180086918
0x180031763  mov     [rbp+var_30], rax
0x180031767  lock inc cs:qword_180086918
0x18003176f  mov     rdx, [rbp+var_28]
0x180031773  xor     eax, eax
0x180031775  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x18003177e  jnz     short loc_180031799
0x180031780  mov     [rbp+var_60], rsi
0x180031784  lea     rdx, stru_180086920; ListEntry
0x18003178b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180031792  call    WINRT_IMPL_InterlockedPushEntrySList
0x180031797  mov     ebx, esi
0x180031799  lea     rdx, ??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800317a0  mov     rcx, rdi
0x1800317a3  call    ??R_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@345678@@Z@QEBA@AEBUISemanticImageIndexStoreStatics2@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsTextQueryEmbeddingsGeneratorAvailableForOptions(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2 const &)
0x1800317a8  movzx   edi, al
0x1800317ab  lock dec cs:qword_180086918
0x1800317b3  jmp     short loc_1800317ED
0x1800317b5  mov     [rbp+var_18], 0
0x1800317b9  mov     dword ptr [rbp+var_28], 312h
0x1800317c0  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800317c7  mov     [rbp+var_20], rax
0x1800317cb  mov     rdx, [rdi]
0x1800317ce  mov     rax, [rbx]
0x1800317d1  lea     r8, [rbp+var_18]
0x1800317d5  mov     rdx, [rdx]
0x1800317d8  mov     rcx, rbx
0x1800317db  mov     rax, [rax+48h]
0x1800317df  call    cs:__guard_dispatch_icall_fptr
0x1800317e5  test    eax, eax
0x1800317e7  js      short loc_180031824
0x1800317e9  movzx   edi, [rbp+var_18]
0x1800317ed  test    rbx, rbx
0x1800317f0  jz      short loc_1800317FB
0x1800317f2  lea     rcx, [rbp+var_60]
0x1800317f6  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800317fb  movzx   eax, dil
0x1800317ff  mov     rcx, [rbp+var_10]
0x180031803  xor     rcx, rsp; StackCookie
0x180031806  call    __security_check_cookie
0x18003180b  lea     r11, [rsp+80h+var_s0]
0x180031813  mov     rbx, [r11+10h]
0x180031817  mov     rsi, [r11+20h]
0x18003181b  mov     rdi, [r11+28h]
0x18003181f  mov     rsp, r11
0x180031822  pop     rbp
0x180031823  retn
0x180031824  lfence
0x180031827  lea     rdx, [rbp+var_28]
0x18003182b  mov     ecx, eax
0x18003182d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031833  lfence
0x180031836  lea     rdx, [rbp+var_60]
0x18003183a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
