# ??$call@AEAV_lambda_1_@?1??ResetVectorSpaceIds@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@AEBUIndexEncryptionOptions@456789@AEBUguid@9@2@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??ResetVectorSpaceIds@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@AEBUIndexEncryptionOptions@6789Microsoft@2@AEBUguid@2@2@Z@@Z

- ea: `0x18003c780`
- end: `0x18003c951`
- name: `??$call@AEAV_lambda_1_@?1??ResetVectorSpaceIds@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@AEBUIndexEncryptionOptions@456789@AEBUguid@9@2@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??ResetVectorSpaceIds@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@AEBUIndexEncryptionOptions@6789Microsoft@2@AEBUguid@2@2@Z@@Z`
- size: `465`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180038e00`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003c700`
- `0x18003c780`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003c8e9`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003c7bd`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__ResetVectorSpaceIds_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9_AEBUIndexEncryptionOptions_456789_AEBUguid_9_2_Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics3_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__ResetVectorSpaceIds_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2_AEBUIndexEncryptionOptions_6789Microsoft_2_AEBUguid_2_2_Z__Z(
        __int64 a1,
        __int64 a2)
{
  signed __int64 v3; // rbx
  __int64 result; // rax
  __int128 *v5; // rax
  __int128 *v6; // rcx
  _QWORD v7[2]; // [rsp+30h] [rbp-19h] BYREF
  _DWORD *v8; // [rsp+40h] [rbp-9h] BYREF
  _DWORD v9[4]; // [rsp+48h] [rbp-1h] BYREF
  const wchar_t *v10; // [rsp+58h] [rbp+Fh]
  __int128 v11; // [rsp+60h] [rbp+17h] BYREF
  __int128 v12; // [rsp+70h] [rbp+27h] BYREF
  signed __int64 v13[2]; // [rsp+80h] [rbp+37h] BYREF

  v9[0] = 1;
  v9[1] = 73;
  v10 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v8 = v9;
  v13[0] = 0;
  LODWORD(v7[0]) = 6148;
  v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>,
    (__int64)v13);
  if ( (int)v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, v7);
  }
  v3 = v13[0];
  v7[0] = v13[0];
  if ( v13[0]
    && (*(_QWORD *)&v12 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int128 *))v13[0])(
          v13[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v12),
        (_QWORD)v12) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v12);
    *(_QWORD *)&v12 = &qword_180086A38;
    _InterlockedIncrement64(&qword_180086A38);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>,
            v13[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A40);
      v3 = 0;
    }
    result = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::ResetVectorSpaceIds'::`2'::_lambda_1_::operator()(
               a2,
               &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>);
    _InterlockedDecrement64(&qword_180086A38);
  }
  else
  {
    v5 = *(__int128 **)(a2 + 24);
    v6 = *(__int128 **)(a2 + 16);
    LODWORD(v13[0]) = 1231;
    v13[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v12 = *v5;
    v11 = *v6;
    result = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, __int128 *, __int128 *))(*(_QWORD *)v3 + 48LL))(
               v3,
               **(_QWORD **)a2,
               **(_QWORD **)(a2 + 8),
               &v11,
               &v12);
    if ( (int)result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, v13);
    }
  }
  if ( v3 )
    return winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v7);
  return result;
}

```

## disassembly

```asm
0x18003c780  mov     [rsp-8+arg_0], rbx
0x18003c785  mov     [rsp-8+arg_10], rsi
0x18003c78a  mov     [rsp-8+arg_18], rdi
0x18003c78f  push    rbp
0x18003c790  lea     rbp, [rsp-57h]
0x18003c795  sub     rsp, 0A0h
0x18003c79c  mov     rax, cs:__security_cookie
0x18003c7a3  xor     rax, rsp
0x18003c7a6  mov     [rbp+57h+var_10], rax
0x18003c7aa  mov     rdi, rdx
0x18003c7ad  xor     esi, esi
0x18003c7af  mov     [rbp+57h+var_58], 1
0x18003c7b6  mov     [rbp+57h+var_54], 49h ; 'I'
0x18003c7bd  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003c7c4  mov     [rbp+57h+var_48], rax
0x18003c7c8  lea     rax, [rbp+57h+var_58]
0x18003c7cc  mov     [rbp+57h+var_60], rax
0x18003c7d0  mov     [rbp+57h+var_20], rsi
0x18003c7d4  mov     dword ptr [rbp+57h+var_70], 1804h
0x18003c7db  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003c7e2  mov     [rbp+57h+var_68], rax
0x18003c7e6  lea     r9, [rbp+57h+var_20]
0x18003c7ea  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics3@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>
0x18003c7f1  lea     rdx, [rbp+57h+var_60]
0x18003c7f5  lea     rcx, [rbp+57h+var_30]
0x18003c7f9  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003c7fe  mov     ecx, dword ptr [rbp+57h+var_30]
0x18003c801  test    ecx, ecx
0x18003c803  js      loc_18003C935
0x18003c809  mov     rbx, [rbp+57h+var_20]
0x18003c80d  mov     [rbp+57h+var_70], rbx
0x18003c811  test    rbx, rbx
0x18003c814  jz      loc_18003C8DA
0x18003c81a  mov     qword ptr [rbp+57h+var_30], rsi
0x18003c81e  mov     rax, [rbx]
0x18003c821  lea     r8, [rbp+57h+var_30]
0x18003c825  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003c82c  mov     rcx, rbx
0x18003c82f  mov     rax, [rax]
0x18003c832  call    cs:__guard_dispatch_icall_fptr
0x18003c838  mov     rax, qword ptr [rbp+57h+var_30]
0x18003c83c  mov     qword ptr [rbp+57h+var_30], rax
0x18003c840  test    rax, rax
0x18003c843  jz      loc_18003C8DA
0x18003c849  lea     rcx, [rbp+57h+var_30]
0x18003c84d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003c852  lea     rax, qword_180086A38
0x18003c859  mov     qword ptr [rbp+57h+var_30], rax
0x18003c85d  lock inc cs:qword_180086A38
0x18003c865  mov     rdx, [rbp+57h+var_20]
0x18003c869  xor     eax, eax
0x18003c86b  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>
0x18003c874  jnz     short loc_18003C88F
0x18003c876  mov     [rbp+57h+var_70], rsi
0x18003c87a  lea     rdx, stru_180086A40; ListEntry
0x18003c881  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003c888  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003c88d  mov     ebx, esi
0x18003c88f  lea     rdx, ??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics3@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3>
0x18003c896  mov     rcx, rdi
0x18003c899  call    ??R_lambda_1_@?1??ResetVectorSpaceIds@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@8@AEBUIndexEncryptionOptions@345678@AEBUguid@8@2@Z@QEBA@AEBUISemanticTextIndexStoreStatics3@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::ResetVectorSpaceIds(winrt::param::hstring const &,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::IndexEncryptionOptions const &,winrt::guid const &,winrt::guid const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics3 const &)
0x18003c89e  nop
0x18003c89f  lock dec cs:qword_180086A38
0x18003c8a7  test    rbx, rbx
0x18003c8aa  jz      short loc_18003C8B5
0x18003c8ac  lea     rcx, [rbp+57h+var_70]
0x18003c8b0  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003c8b5  mov     rcx, [rbp+57h+var_10]
0x18003c8b9  xor     rcx, rsp; StackCookie
0x18003c8bc  call    __security_check_cookie
0x18003c8c1  lea     r11, [rsp+0A0h+var_s0]
0x18003c8c9  mov     rbx, [r11+10h]
0x18003c8cd  mov     rsi, [r11+20h]
0x18003c8d1  mov     rdi, [r11+28h]
0x18003c8d5  mov     rsp, r11
0x18003c8d8  pop     rbp
0x18003c8d9  retn
0x18003c8da  mov     rax, [rdi+18h]
0x18003c8de  mov     rcx, [rdi+10h]
0x18003c8e2  mov     dword ptr [rbp+57h+var_20], 4CFh
0x18003c8e9  lea     rdx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003c8f0  mov     [rbp+57h+var_18], rdx
0x18003c8f4  movups  xmm0, xmmword ptr [rax]
0x18003c8f7  movaps  [rbp+57h+var_30], xmm0
0x18003c8fb  movups  xmm1, xmmword ptr [rcx]
0x18003c8fe  movaps  [rbp+57h+var_40], xmm1
0x18003c902  mov     r8, [rdi+8]
0x18003c906  mov     rdx, [rdi]
0x18003c909  mov     rax, [rbx]
0x18003c90c  lea     rcx, [rbp+57h+var_30]
0x18003c910  mov     [rsp+0A0h+var_80], rcx
0x18003c915  lea     r9, [rbp+57h+var_40]
0x18003c919  mov     r8, [r8]
0x18003c91c  mov     rdx, [rdx]
0x18003c91f  mov     rcx, rbx
0x18003c922  mov     rax, [rax+30h]
0x18003c926  call    cs:__guard_dispatch_icall_fptr
0x18003c92c  test    eax, eax
0x18003c92e  js      short loc_18003C942
0x18003c930  jmp     loc_18003C8A7
0x18003c935  lfence
0x18003c938  lea     rdx, [rbp+57h+var_70]
0x18003c93c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003c942  lfence
0x18003c945  lea     rdx, [rbp+57h+var_20]
0x18003c949  mov     ecx, eax
0x18003c94b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
