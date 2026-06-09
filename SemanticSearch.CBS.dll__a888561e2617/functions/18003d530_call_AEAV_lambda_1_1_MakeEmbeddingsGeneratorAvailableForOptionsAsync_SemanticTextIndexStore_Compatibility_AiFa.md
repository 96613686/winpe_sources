# ??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003d530`
- end: `0x18003d72c`
- name: `??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003d730`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003d530`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003d64f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d6a1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d571`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableForOptionsAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableForOptionsAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
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
  v13[1] = 73;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>,
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
    LODWORD(v10) = 1220;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 56LL))(v5, **a3, &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086A58;
  _InterlockedIncrement64(&qword_180086A58);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A60);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 1220;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
                                                             + 56LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086A58);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18003d530  mov     [rsp-18h+arg_0], rbx
0x18003d535  mov     [rsp-18h+arg_18], rsi
0x18003d53a  push    rbp
0x18003d53b  push    rdi
0x18003d53c  push    r14
0x18003d53e  mov     rbp, rsp
0x18003d541  sub     rsp, 80h
0x18003d548  mov     rax, cs:__security_cookie
0x18003d54f  xor     rax, rsp
0x18003d552  mov     [rbp+var_8], rax
0x18003d556  mov     rsi, r8
0x18003d559  mov     rdi, rdx
0x18003d55c  mov     [rbp+var_20], rdx
0x18003d560  xor     r14d, r14d
0x18003d563  mov     [rbp+var_38], 1
0x18003d56a  mov     [rbp+var_34], 49h ; 'I'
0x18003d571  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003d578  mov     [rbp+var_28], rax
0x18003d57c  lea     rax, [rbp+var_38]
0x18003d580  mov     [rbp+var_40], rax
0x18003d584  mov     [rbp+var_18], r14
0x18003d588  mov     dword ptr [rbp+var_58], 1804h
0x18003d58f  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d596  mov     [rbp+var_50], rax
0x18003d59a  lea     r9, [rbp+var_18]
0x18003d59e  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d5a5  lea     rdx, [rbp+var_40]
0x18003d5a9  lea     rcx, [rbp+var_60]
0x18003d5ad  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003d5b2  mov     ecx, dword ptr [rbp+var_60]
0x18003d5b5  test    ecx, ecx
0x18003d5b7  js      loc_18003D710
0x18003d5bd  mov     rbx, [rbp+var_18]
0x18003d5c1  mov     [rbp+var_60], rbx
0x18003d5c5  test    rbx, rbx
0x18003d5c8  jz      loc_18003D696
0x18003d5ce  mov     [rbp+var_20], r14
0x18003d5d2  mov     rax, [rbx]
0x18003d5d5  lea     r8, [rbp+var_20]
0x18003d5d9  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003d5e0  mov     rcx, rbx
0x18003d5e3  mov     rax, [rax]
0x18003d5e6  call    cs:__guard_dispatch_icall_fptr
0x18003d5ec  mov     rax, [rbp+var_20]
0x18003d5f0  mov     [rbp+var_20], rax
0x18003d5f4  test    rax, rax
0x18003d5f7  jz      loc_18003D696
0x18003d5fd  lea     rcx, [rbp+var_20]
0x18003d601  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d606  lea     rax, qword_180086A58
0x18003d60d  mov     [rbp+var_58], rax
0x18003d611  lock inc cs:qword_180086A58
0x18003d619  mov     rcx, [rbp+var_18]
0x18003d61d  xor     eax, eax
0x18003d61f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d628  jnz     short loc_18003D644
0x18003d62a  mov     [rbp+var_60], r14
0x18003d62e  lea     rdx, stru_180086A60; ListEntry
0x18003d635  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003d63c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003d641  mov     ebx, r14d
0x18003d644  mov     [rbp+var_20], r14
0x18003d648  mov     dword ptr [rbp+var_18], 4C4h
0x18003d64f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d656  mov     [rbp+var_10], rax
0x18003d65a  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d661  mov     rdx, [rsi]
0x18003d664  mov     rax, [rcx]
0x18003d667  lea     r8, [rbp+var_20]
0x18003d66b  mov     rdx, [rdx]
0x18003d66e  mov     rax, [rax+38h]
0x18003d672  call    cs:__guard_dispatch_icall_fptr
0x18003d678  test    eax, eax
0x18003d67a  js      loc_18003D71D
0x18003d680  mov     rcx, [rbp+var_20]
0x18003d684  mov     [rdi], rcx
0x18003d687  lock dec cs:qword_180086A58
0x18003d68f  test    rbx, rbx
0x18003d692  jz      short loc_18003D6DA
0x18003d694  jmp     short loc_18003D6D1
0x18003d696  mov     [rbp+var_20], r14
0x18003d69a  mov     dword ptr [rbp+var_58], 4C4h
0x18003d6a1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d6a8  mov     [rbp+var_50], rax
0x18003d6ac  mov     rdx, [rsi]
0x18003d6af  mov     rax, [rbx]
0x18003d6b2  lea     r8, [rbp+var_20]
0x18003d6b6  mov     rdx, [rdx]
0x18003d6b9  mov     rcx, rbx
0x18003d6bc  mov     rax, [rax+38h]
0x18003d6c0  call    cs:__guard_dispatch_icall_fptr
0x18003d6c6  test    eax, eax
0x18003d6c8  js      short loc_18003D701
0x18003d6ca  mov     rax, [rbp+var_20]
0x18003d6ce  mov     [rdi], rax
0x18003d6d1  lea     rcx, [rbp+var_60]
0x18003d6d5  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d6da  mov     rax, rdi
0x18003d6dd  mov     rcx, [rbp+var_8]
0x18003d6e1  xor     rcx, rsp; StackCookie
0x18003d6e4  call    __security_check_cookie
0x18003d6e9  lea     r11, [rsp+80h+var_s0]
0x18003d6f1  mov     rbx, [r11+20h]
0x18003d6f5  mov     rsi, [r11+38h]
0x18003d6f9  mov     rsp, r11
0x18003d6fc  pop     r14
0x18003d6fe  pop     rdi
0x18003d6ff  pop     rbp
0x18003d700  retn
0x18003d701  lfence
0x18003d704  lea     rdx, [rbp+var_58]
0x18003d708  mov     ecx, eax
0x18003d70a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003d710  lfence
0x18003d713  lea     rdx, [rbp+var_58]
0x18003d717  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003d71d  lfence
0x18003d720  lea     rdx, [rbp+var_18]
0x18003d724  mov     ecx, eax
0x18003d726  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
