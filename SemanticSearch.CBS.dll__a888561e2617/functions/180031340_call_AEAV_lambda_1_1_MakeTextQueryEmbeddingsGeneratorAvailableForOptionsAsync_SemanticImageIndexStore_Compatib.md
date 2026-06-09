# ??$call@AEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180031340`
- end: `0x18003153c`
- name: `??$call@AEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031540`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180031340`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003145f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800314b1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180031381`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeTextQueryEmbeddingsGeneratorAvailableForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        _QWORD **a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  signed __int64 v9; // [rsp+20h] [rbp-60h] BYREF
  __int64 *v10; // [rsp+28h] [rbp-58h] BYREF
  const char *v11; // [rsp+30h] [rbp-50h]
  _DWORD *v12; // [rsp+40h] [rbp-40h] BYREF
  _DWORD v13[4]; // [rsp+48h] [rbp-38h] BYREF
  const wchar_t *v14; // [rsp+58h] [rbp-28h]
  _QWORD *v15; // [rsp+60h] [rbp-20h] BYREF
  signed __int64 v16[2]; // [rsp+68h] [rbp-18h] BYREF

  v15 = a2;
  v13[0] = 1;
  v13[1] = 74;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
    (__int64)v16);
  if ( (int)v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9, &v10);
  }
  v5 = v16[0];
  v9 = v16[0];
  if ( !v16[0]
    || (v15 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, _QWORD **))v16[0])(
          v16[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v15),
        !v15) )
  {
    v15 = 0;
    LODWORD(v10) = 792;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 80LL))(v5, **a3, &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086918;
  _InterlockedIncrement64(&qword_180086918);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086920);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 792;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
                                                             + 80LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086918);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x180031340  mov     [rsp-18h+arg_0], rbx
0x180031345  mov     [rsp-18h+arg_18], rsi
0x18003134a  push    rbp
0x18003134b  push    rdi
0x18003134c  push    r14
0x18003134e  mov     rbp, rsp
0x180031351  sub     rsp, 80h
0x180031358  mov     rax, cs:__security_cookie
0x18003135f  xor     rax, rsp
0x180031362  mov     [rbp+var_8], rax
0x180031366  mov     rsi, r8
0x180031369  mov     rdi, rdx
0x18003136c  mov     [rbp+var_20], rdx
0x180031370  xor     r14d, r14d
0x180031373  mov     [rbp+var_38], 1
0x18003137a  mov     [rbp+var_34], 4Ah ; 'J'
0x180031381  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180031388  mov     [rbp+var_28], rax
0x18003138c  lea     rax, [rbp+var_38]
0x180031390  mov     [rbp+var_40], rax
0x180031394  mov     [rbp+var_18], r14
0x180031398  mov     dword ptr [rbp+var_58], 1804h
0x18003139f  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800313a6  mov     [rbp+var_50], rax
0x1800313aa  lea     r9, [rbp+var_18]
0x1800313ae  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800313b5  lea     rdx, [rbp+var_40]
0x1800313b9  lea     rcx, [rbp+var_60]
0x1800313bd  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800313c2  mov     ecx, dword ptr [rbp+var_60]
0x1800313c5  test    ecx, ecx
0x1800313c7  js      loc_180031520
0x1800313cd  mov     rbx, [rbp+var_18]
0x1800313d1  mov     [rbp+var_60], rbx
0x1800313d5  test    rbx, rbx
0x1800313d8  jz      loc_1800314A6
0x1800313de  mov     [rbp+var_20], r14
0x1800313e2  mov     rax, [rbx]
0x1800313e5  lea     r8, [rbp+var_20]
0x1800313e9  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800313f0  mov     rcx, rbx
0x1800313f3  mov     rax, [rax]
0x1800313f6  call    cs:__guard_dispatch_icall_fptr
0x1800313fc  mov     rax, [rbp+var_20]
0x180031400  mov     [rbp+var_20], rax
0x180031404  test    rax, rax
0x180031407  jz      loc_1800314A6
0x18003140d  lea     rcx, [rbp+var_20]
0x180031411  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031416  lea     rax, qword_180086918
0x18003141d  mov     [rbp+var_58], rax
0x180031421  lock inc cs:qword_180086918
0x180031429  mov     rcx, [rbp+var_18]
0x18003142d  xor     eax, eax
0x18003142f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031438  jnz     short loc_180031454
0x18003143a  mov     [rbp+var_60], r14
0x18003143e  lea     rdx, stru_180086920; ListEntry
0x180031445  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003144c  call    WINRT_IMPL_InterlockedPushEntrySList
0x180031451  mov     ebx, r14d
0x180031454  mov     [rbp+var_20], r14
0x180031458  mov     dword ptr [rbp+var_18], 318h
0x18003145f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031466  mov     [rbp+var_10], rax
0x18003146a  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031471  mov     rdx, [rsi]
0x180031474  mov     rax, [rcx]
0x180031477  lea     r8, [rbp+var_20]
0x18003147b  mov     rdx, [rdx]
0x18003147e  mov     rax, [rax+50h]
0x180031482  call    cs:__guard_dispatch_icall_fptr
0x180031488  test    eax, eax
0x18003148a  js      loc_18003152D
0x180031490  mov     rcx, [rbp+var_20]
0x180031494  mov     [rdi], rcx
0x180031497  lock dec cs:qword_180086918
0x18003149f  test    rbx, rbx
0x1800314a2  jz      short loc_1800314EA
0x1800314a4  jmp     short loc_1800314E1
0x1800314a6  mov     [rbp+var_20], r14
0x1800314aa  mov     dword ptr [rbp+var_58], 318h
0x1800314b1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800314b8  mov     [rbp+var_50], rax
0x1800314bc  mov     rdx, [rsi]
0x1800314bf  mov     rax, [rbx]
0x1800314c2  lea     r8, [rbp+var_20]
0x1800314c6  mov     rdx, [rdx]
0x1800314c9  mov     rcx, rbx
0x1800314cc  mov     rax, [rax+50h]
0x1800314d0  call    cs:__guard_dispatch_icall_fptr
0x1800314d6  test    eax, eax
0x1800314d8  js      short loc_180031511
0x1800314da  mov     rax, [rbp+var_20]
0x1800314de  mov     [rdi], rax
0x1800314e1  lea     rcx, [rbp+var_60]
0x1800314e5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800314ea  mov     rax, rdi
0x1800314ed  mov     rcx, [rbp+var_8]
0x1800314f1  xor     rcx, rsp; StackCookie
0x1800314f4  call    __security_check_cookie
0x1800314f9  lea     r11, [rsp+80h+var_s0]
0x180031501  mov     rbx, [r11+20h]
0x180031505  mov     rsi, [r11+38h]
0x180031509  mov     rsp, r11
0x18003150c  pop     r14
0x18003150e  pop     rdi
0x18003150f  pop     rbp
0x180031510  retn
0x180031511  lfence
0x180031514  lea     rdx, [rbp+var_58]
0x180031518  mov     ecx, eax
0x18003151a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031520  lfence
0x180031523  lea     rdx, [rbp+var_58]
0x180031527  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003152d  lfence
0x180031530  lea     rdx, [rbp+var_18]
0x180031534  mov     ecx, eax
0x180031536  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
