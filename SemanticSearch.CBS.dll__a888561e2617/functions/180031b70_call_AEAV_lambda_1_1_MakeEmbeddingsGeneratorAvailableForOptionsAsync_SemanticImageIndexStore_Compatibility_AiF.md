# ??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180031b70`
- end: `0x180031d6c`
- name: `??$call@AEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeEmbeddingsGeneratorAvailableForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031d70`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180031b70`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180031c8f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180031ce1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180031bb1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeEmbeddingsGeneratorAvailableForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    LODWORD(v10) = 774;
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
  LODWORD(v16[0]) = 774;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
                                                             + 56LL))(
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
0x180031b70  mov     [rsp-18h+arg_0], rbx
0x180031b75  mov     [rsp-18h+arg_18], rsi
0x180031b7a  push    rbp
0x180031b7b  push    rdi
0x180031b7c  push    r14
0x180031b7e  mov     rbp, rsp
0x180031b81  sub     rsp, 80h
0x180031b88  mov     rax, cs:__security_cookie
0x180031b8f  xor     rax, rsp
0x180031b92  mov     [rbp+var_8], rax
0x180031b96  mov     rsi, r8
0x180031b99  mov     rdi, rdx
0x180031b9c  mov     [rbp+var_20], rdx
0x180031ba0  xor     r14d, r14d
0x180031ba3  mov     [rbp+var_38], 1
0x180031baa  mov     [rbp+var_34], 4Ah ; 'J'
0x180031bb1  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180031bb8  mov     [rbp+var_28], rax
0x180031bbc  lea     rax, [rbp+var_38]
0x180031bc0  mov     [rbp+var_40], rax
0x180031bc4  mov     [rbp+var_18], r14
0x180031bc8  mov     dword ptr [rbp+var_58], 1804h
0x180031bcf  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031bd6  mov     [rbp+var_50], rax
0x180031bda  lea     r9, [rbp+var_18]
0x180031bde  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031be5  lea     rdx, [rbp+var_40]
0x180031be9  lea     rcx, [rbp+var_60]
0x180031bed  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180031bf2  mov     ecx, dword ptr [rbp+var_60]
0x180031bf5  test    ecx, ecx
0x180031bf7  js      loc_180031D50
0x180031bfd  mov     rbx, [rbp+var_18]
0x180031c01  mov     [rbp+var_60], rbx
0x180031c05  test    rbx, rbx
0x180031c08  jz      loc_180031CD6
0x180031c0e  mov     [rbp+var_20], r14
0x180031c12  mov     rax, [rbx]
0x180031c15  lea     r8, [rbp+var_20]
0x180031c19  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180031c20  mov     rcx, rbx
0x180031c23  mov     rax, [rax]
0x180031c26  call    cs:__guard_dispatch_icall_fptr
0x180031c2c  mov     rax, [rbp+var_20]
0x180031c30  mov     [rbp+var_20], rax
0x180031c34  test    rax, rax
0x180031c37  jz      loc_180031CD6
0x180031c3d  lea     rcx, [rbp+var_20]
0x180031c41  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031c46  lea     rax, qword_180086918
0x180031c4d  mov     [rbp+var_58], rax
0x180031c51  lock inc cs:qword_180086918
0x180031c59  mov     rcx, [rbp+var_18]
0x180031c5d  xor     eax, eax
0x180031c5f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031c68  jnz     short loc_180031C84
0x180031c6a  mov     [rbp+var_60], r14
0x180031c6e  lea     rdx, stru_180086920; ListEntry
0x180031c75  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180031c7c  call    WINRT_IMPL_InterlockedPushEntrySList
0x180031c81  mov     ebx, r14d
0x180031c84  mov     [rbp+var_20], r14
0x180031c88  mov     dword ptr [rbp+var_18], 306h
0x180031c8f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031c96  mov     [rbp+var_10], rax
0x180031c9a  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031ca1  mov     rdx, [rsi]
0x180031ca4  mov     rax, [rcx]
0x180031ca7  lea     r8, [rbp+var_20]
0x180031cab  mov     rdx, [rdx]
0x180031cae  mov     rax, [rax+38h]
0x180031cb2  call    cs:__guard_dispatch_icall_fptr
0x180031cb8  test    eax, eax
0x180031cba  js      loc_180031D5D
0x180031cc0  mov     rcx, [rbp+var_20]
0x180031cc4  mov     [rdi], rcx
0x180031cc7  lock dec cs:qword_180086918
0x180031ccf  test    rbx, rbx
0x180031cd2  jz      short loc_180031D1A
0x180031cd4  jmp     short loc_180031D11
0x180031cd6  mov     [rbp+var_20], r14
0x180031cda  mov     dword ptr [rbp+var_58], 306h
0x180031ce1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031ce8  mov     [rbp+var_50], rax
0x180031cec  mov     rdx, [rsi]
0x180031cef  mov     rax, [rbx]
0x180031cf2  lea     r8, [rbp+var_20]
0x180031cf6  mov     rdx, [rdx]
0x180031cf9  mov     rcx, rbx
0x180031cfc  mov     rax, [rax+38h]
0x180031d00  call    cs:__guard_dispatch_icall_fptr
0x180031d06  test    eax, eax
0x180031d08  js      short loc_180031D41
0x180031d0a  mov     rax, [rbp+var_20]
0x180031d0e  mov     [rdi], rax
0x180031d11  lea     rcx, [rbp+var_60]
0x180031d15  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031d1a  mov     rax, rdi
0x180031d1d  mov     rcx, [rbp+var_8]
0x180031d21  xor     rcx, rsp; StackCookie
0x180031d24  call    __security_check_cookie
0x180031d29  lea     r11, [rsp+80h+var_s0]
0x180031d31  mov     rbx, [r11+20h]
0x180031d35  mov     rsi, [r11+38h]
0x180031d39  mov     rsp, r11
0x180031d3c  pop     r14
0x180031d3e  pop     rdi
0x180031d3f  pop     rbp
0x180031d40  retn
0x180031d41  lfence
0x180031d44  lea     rdx, [rbp+var_58]
0x180031d48  mov     ecx, eax
0x180031d4a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031d50  lfence
0x180031d53  lea     rdx, [rbp+var_58]
0x180031d57  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031d5d  lfence
0x180031d60  lea     rdx, [rbp+var_18]
0x180031d64  mov     ecx, eax
0x180031d66  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
