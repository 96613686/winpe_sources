# ??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003d260`
- end: `0x18003d45c`
- name: `??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003d460`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003d260`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003d37f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d3d1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d2a1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateEmbeddingsGeneratorForOptionsAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateEmbeddingsGeneratorForOptionsAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    LODWORD(v10) = 1226;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 64LL))(v5, **a3, &v15);
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
  LODWORD(v16[0]) = 1226;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
                                                             + 64LL))(
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
0x18003d260  mov     [rsp-18h+arg_0], rbx
0x18003d265  mov     [rsp-18h+arg_18], rsi
0x18003d26a  push    rbp
0x18003d26b  push    rdi
0x18003d26c  push    r14
0x18003d26e  mov     rbp, rsp
0x18003d271  sub     rsp, 80h
0x18003d278  mov     rax, cs:__security_cookie
0x18003d27f  xor     rax, rsp
0x18003d282  mov     [rbp+var_8], rax
0x18003d286  mov     rsi, r8
0x18003d289  mov     rdi, rdx
0x18003d28c  mov     [rbp+var_20], rdx
0x18003d290  xor     r14d, r14d
0x18003d293  mov     [rbp+var_38], 1
0x18003d29a  mov     [rbp+var_34], 49h ; 'I'
0x18003d2a1  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003d2a8  mov     [rbp+var_28], rax
0x18003d2ac  lea     rax, [rbp+var_38]
0x18003d2b0  mov     [rbp+var_40], rax
0x18003d2b4  mov     [rbp+var_18], r14
0x18003d2b8  mov     dword ptr [rbp+var_58], 1804h
0x18003d2bf  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d2c6  mov     [rbp+var_50], rax
0x18003d2ca  lea     r9, [rbp+var_18]
0x18003d2ce  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d2d5  lea     rdx, [rbp+var_40]
0x18003d2d9  lea     rcx, [rbp+var_60]
0x18003d2dd  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003d2e2  mov     ecx, dword ptr [rbp+var_60]
0x18003d2e5  test    ecx, ecx
0x18003d2e7  js      loc_18003D440
0x18003d2ed  mov     rbx, [rbp+var_18]
0x18003d2f1  mov     [rbp+var_60], rbx
0x18003d2f5  test    rbx, rbx
0x18003d2f8  jz      loc_18003D3C6
0x18003d2fe  mov     [rbp+var_20], r14
0x18003d302  mov     rax, [rbx]
0x18003d305  lea     r8, [rbp+var_20]
0x18003d309  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003d310  mov     rcx, rbx
0x18003d313  mov     rax, [rax]
0x18003d316  call    cs:__guard_dispatch_icall_fptr
0x18003d31c  mov     rax, [rbp+var_20]
0x18003d320  mov     [rbp+var_20], rax
0x18003d324  test    rax, rax
0x18003d327  jz      loc_18003D3C6
0x18003d32d  lea     rcx, [rbp+var_20]
0x18003d331  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d336  lea     rax, qword_180086A58
0x18003d33d  mov     [rbp+var_58], rax
0x18003d341  lock inc cs:qword_180086A58
0x18003d349  mov     rcx, [rbp+var_18]
0x18003d34d  xor     eax, eax
0x18003d34f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d358  jnz     short loc_18003D374
0x18003d35a  mov     [rbp+var_60], r14
0x18003d35e  lea     rdx, stru_180086A60; ListEntry
0x18003d365  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003d36c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003d371  mov     ebx, r14d
0x18003d374  mov     [rbp+var_20], r14
0x18003d378  mov     dword ptr [rbp+var_18], 4CAh
0x18003d37f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d386  mov     [rbp+var_10], rax
0x18003d38a  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics2>
0x18003d391  mov     rdx, [rsi]
0x18003d394  mov     rax, [rcx]
0x18003d397  lea     r8, [rbp+var_20]
0x18003d39b  mov     rdx, [rdx]
0x18003d39e  mov     rax, [rax+40h]
0x18003d3a2  call    cs:__guard_dispatch_icall_fptr
0x18003d3a8  test    eax, eax
0x18003d3aa  js      loc_18003D44D
0x18003d3b0  mov     rcx, [rbp+var_20]
0x18003d3b4  mov     [rdi], rcx
0x18003d3b7  lock dec cs:qword_180086A58
0x18003d3bf  test    rbx, rbx
0x18003d3c2  jz      short loc_18003D40A
0x18003d3c4  jmp     short loc_18003D401
0x18003d3c6  mov     [rbp+var_20], r14
0x18003d3ca  mov     dword ptr [rbp+var_58], 4CAh
0x18003d3d1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d3d8  mov     [rbp+var_50], rax
0x18003d3dc  mov     rdx, [rsi]
0x18003d3df  mov     rax, [rbx]
0x18003d3e2  lea     r8, [rbp+var_20]
0x18003d3e6  mov     rdx, [rdx]
0x18003d3e9  mov     rcx, rbx
0x18003d3ec  mov     rax, [rax+40h]
0x18003d3f0  call    cs:__guard_dispatch_icall_fptr
0x18003d3f6  test    eax, eax
0x18003d3f8  js      short loc_18003D431
0x18003d3fa  mov     rax, [rbp+var_20]
0x18003d3fe  mov     [rdi], rax
0x18003d401  lea     rcx, [rbp+var_60]
0x18003d405  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d40a  mov     rax, rdi
0x18003d40d  mov     rcx, [rbp+var_8]
0x18003d411  xor     rcx, rsp; StackCookie
0x18003d414  call    __security_check_cookie
0x18003d419  lea     r11, [rsp+80h+var_s0]
0x18003d421  mov     rbx, [r11+20h]
0x18003d425  mov     rsi, [r11+38h]
0x18003d429  mov     rsp, r11
0x18003d42c  pop     r14
0x18003d42e  pop     rdi
0x18003d42f  pop     rbp
0x18003d430  retn
0x18003d431  lfence
0x18003d434  lea     rdx, [rbp+var_58]
0x18003d438  mov     ecx, eax
0x18003d43a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003d440  lfence
0x18003d443  lea     rdx, [rbp+var_58]
0x18003d447  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003d44d  lfence
0x18003d450  lea     rdx, [rbp+var_18]
0x18003d454  mov     ecx, eax
0x18003d456  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
