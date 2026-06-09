# ??$call@AEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x180030c90`
- end: `0x180030e4b`
- name: `??$call@AEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `443`
- prototype: `__int64 __fastcall(__int64, __int128 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800207b0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180030c00`
- `0x180030c90`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180030dc3`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030ccb`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsTextQueryEmbeddingsGeneratorAvailable_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsTextQueryEmbeddingsGeneratorAvailable_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
        __int64 a1,
        __int128 **a2)
{
  signed __int64 v3; // rbx
  unsigned __int8 v4; // di
  __int128 *v5; // rax
  int v6; // eax
  _QWORD v8[2]; // [rsp+20h] [rbp-60h] BYREF
  _DWORD *v9; // [rsp+30h] [rbp-50h] BYREF
  _DWORD v10[4]; // [rsp+38h] [rbp-48h] BYREF
  const wchar_t *v11; // [rsp+48h] [rbp-38h]
  __int128 v12; // [rsp+50h] [rbp-30h] BYREF
  signed __int64 v13[2]; // [rsp+60h] [rbp-20h] BYREF
  _BYTE v14[8]; // [rsp+70h] [rbp-10h] BYREF

  v10[0] = 1;
  v10[1] = 74;
  v11 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v9 = v10;
  v13[0] = 0;
  LODWORD(v8[0]) = 6148;
  v8[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
    (__int64)v13);
  if ( (int)v12 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v12, v8);
  }
  v3 = v13[0];
  v8[0] = v13[0];
  if ( v13[0]
    && (*(_QWORD *)&v12 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, __int128 *))v13[0])(
          v13[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v12),
        (_QWORD)v12) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v12);
    *(_QWORD *)&v12 = &qword_180086938;
    _InterlockedIncrement64(&qword_180086938);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
            v13[0],
            0) )
    {
      v8[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsTextQueryEmbeddingsGeneratorAvailable'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>);
    _InterlockedDecrement64(&qword_180086938);
  }
  else
  {
    v5 = *a2;
    v14[0] = 0;
    LODWORD(v13[0]) = 746;
    v13[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v12 = *v5;
    v6 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _BYTE *))(*(_QWORD *)v3 + 144LL))(v3, &v12, v14);
    if ( v6 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v6, v13);
    }
    v4 = v14[0];
  }
  if ( v3 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v8);
  return v4;
}

```

## disassembly

```asm
0x180030c90  mov     [rsp-8+arg_0], rbx
0x180030c95  mov     [rsp-8+arg_10], rsi
0x180030c9a  mov     [rsp-8+arg_18], rdi
0x180030c9f  push    rbp
0x180030ca0  mov     rbp, rsp
0x180030ca3  sub     rsp, 80h
0x180030caa  mov     rax, cs:__security_cookie
0x180030cb1  xor     rax, rsp
0x180030cb4  mov     [rbp+var_8], rax
0x180030cb8  mov     rdi, rdx
0x180030cbb  xor     esi, esi
0x180030cbd  mov     [rbp+var_48], 1
0x180030cc4  mov     [rbp+var_44], 4Ah ; 'J'
0x180030ccb  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180030cd2  mov     [rbp+var_38], rax
0x180030cd6  lea     rax, [rbp+var_48]
0x180030cda  mov     [rbp+var_50], rax
0x180030cde  mov     [rbp+var_20], rsi
0x180030ce2  mov     dword ptr [rbp+var_60], 1804h
0x180030ce9  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030cf0  mov     [rbp+var_58], rax
0x180030cf4  lea     r9, [rbp+var_20]
0x180030cf8  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030cff  lea     rdx, [rbp+var_50]
0x180030d03  lea     rcx, [rbp+var_30]
0x180030d07  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030d0c  mov     ecx, dword ptr [rbp+var_30]
0x180030d0f  test    ecx, ecx
0x180030d11  js      loc_180030E3E
0x180030d17  mov     rbx, [rbp+var_20]
0x180030d1b  mov     [rbp+var_60], rbx
0x180030d1f  test    rbx, rbx
0x180030d22  jz      loc_180030DB5
0x180030d28  mov     qword ptr [rbp+var_30], rsi
0x180030d2c  mov     rax, [rbx]
0x180030d2f  lea     r8, [rbp+var_30]
0x180030d33  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030d3a  mov     rcx, rbx
0x180030d3d  mov     rax, [rax]
0x180030d40  call    cs:__guard_dispatch_icall_fptr
0x180030d46  mov     rax, qword ptr [rbp+var_30]
0x180030d4a  mov     qword ptr [rbp+var_30], rax
0x180030d4e  test    rax, rax
0x180030d51  jz      short loc_180030DB5
0x180030d53  lea     rcx, [rbp+var_30]
0x180030d57  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030d5c  lea     rax, qword_180086938
0x180030d63  mov     qword ptr [rbp+var_30], rax
0x180030d67  lock inc cs:qword_180086938
0x180030d6f  mov     rdx, [rbp+var_20]
0x180030d73  xor     eax, eax
0x180030d75  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030d7e  jnz     short loc_180030D99
0x180030d80  mov     [rbp+var_60], rsi
0x180030d84  lea     rdx, stru_180086940; ListEntry
0x180030d8b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180030d92  call    WINRT_IMPL_InterlockedPushEntrySList
0x180030d97  mov     ebx, esi
0x180030d99  lea     rdx, ??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030da0  mov     rcx, rdi
0x180030da3  call    ??R_lambda_1_@?1??IsTextQueryEmbeddingsGeneratorAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@8@@Z@QEBA@AEBUISemanticImageIndexStoreStatics@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsTextQueryEmbeddingsGeneratorAvailable(winrt::guid const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics const &)
0x180030da8  movzx   edi, al
0x180030dab  lock dec cs:qword_180086938
0x180030db3  jmp     short loc_180030DF8
0x180030db5  mov     rax, [rdi]
0x180030db8  mov     [rbp+var_10], 0
0x180030dbc  mov     dword ptr [rbp+var_20], 2EAh
0x180030dc3  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030dca  mov     [rbp+var_18], rcx
0x180030dce  movups  xmm0, xmmword ptr [rax]
0x180030dd1  movaps  [rbp+var_30], xmm0
0x180030dd5  mov     rax, [rbx]
0x180030dd8  lea     r8, [rbp+var_10]
0x180030ddc  lea     rdx, [rbp+var_30]
0x180030de0  mov     rcx, rbx
0x180030de3  mov     rax, [rax+90h]
0x180030dea  call    cs:__guard_dispatch_icall_fptr
0x180030df0  test    eax, eax
0x180030df2  js      short loc_180030E2F
0x180030df4  movzx   edi, [rbp+var_10]
0x180030df8  test    rbx, rbx
0x180030dfb  jz      short loc_180030E06
0x180030dfd  lea     rcx, [rbp+var_60]
0x180030e01  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030e06  movzx   eax, dil
0x180030e0a  mov     rcx, [rbp+var_8]
0x180030e0e  xor     rcx, rsp; StackCookie
0x180030e11  call    __security_check_cookie
0x180030e16  lea     r11, [rsp+80h+var_s0]
0x180030e1e  mov     rbx, [r11+10h]
0x180030e22  mov     rsi, [r11+20h]
0x180030e26  mov     rdi, [r11+28h]
0x180030e2a  mov     rsp, r11
0x180030e2d  pop     rbp
0x180030e2e  retn
0x180030e2f  lfence
0x180030e32  lea     rdx, [rbp+var_20]
0x180030e36  mov     ecx, eax
0x180030e38  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030e3e  lfence
0x180030e41  lea     rdx, [rbp+var_60]
0x180030e45  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
