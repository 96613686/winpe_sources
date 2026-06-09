# ??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180031ec0`
- end: `0x180032070`
- name: `??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180032070`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180031e40`
- `0x180031ec0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180031ff0`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180031efb`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsEmbeddingsGeneratorAvailableForOptions_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsEmbeddingsGeneratorAvailableForOptions_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsEmbeddingsGeneratorAvailableForOptions'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>);
    _InterlockedDecrement64(&qword_180086918);
  }
  else
  {
    v13[0] = 0;
    LODWORD(v12[0]) = 768;
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
0x180031ec0  mov     [rsp-8+arg_0], rbx
0x180031ec5  mov     [rsp-8+arg_10], rsi
0x180031eca  mov     [rsp-8+arg_18], rdi
0x180031ecf  push    rbp
0x180031ed0  mov     rbp, rsp
0x180031ed3  sub     rsp, 80h
0x180031eda  mov     rax, cs:__security_cookie
0x180031ee1  xor     rax, rsp
0x180031ee4  mov     [rbp+var_10], rax
0x180031ee8  mov     rdi, rdx
0x180031eeb  xor     esi, esi
0x180031eed  mov     [rbp+var_48], 1
0x180031ef4  mov     [rbp+var_44], 4Ah ; 'J'
0x180031efb  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180031f02  mov     [rbp+var_38], rax
0x180031f06  lea     rax, [rbp+var_48]
0x180031f0a  mov     [rbp+var_50], rax
0x180031f0e  mov     [rbp+var_28], rsi
0x180031f12  mov     dword ptr [rbp+var_60], 1804h
0x180031f19  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031f20  mov     [rbp+var_58], rax
0x180031f24  lea     r9, [rbp+var_28]
0x180031f28  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031f2f  lea     rdx, [rbp+var_50]
0x180031f33  lea     rcx, [rbp+var_30]
0x180031f37  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180031f3c  mov     ecx, dword ptr [rbp+var_30]
0x180031f3f  test    ecx, ecx
0x180031f41  js      loc_180032063
0x180031f47  mov     rbx, [rbp+var_28]
0x180031f4b  mov     [rbp+var_60], rbx
0x180031f4f  test    rbx, rbx
0x180031f52  jz      loc_180031FE5
0x180031f58  mov     [rbp+var_30], rsi
0x180031f5c  mov     rax, [rbx]
0x180031f5f  lea     r8, [rbp+var_30]
0x180031f63  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180031f6a  mov     rcx, rbx
0x180031f6d  mov     rax, [rax]
0x180031f70  call    cs:__guard_dispatch_icall_fptr
0x180031f76  mov     rax, [rbp+var_30]
0x180031f7a  mov     [rbp+var_30], rax
0x180031f7e  test    rax, rax
0x180031f81  jz      short loc_180031FE5
0x180031f83  lea     rcx, [rbp+var_30]
0x180031f87  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031f8c  lea     rax, qword_180086918
0x180031f93  mov     [rbp+var_30], rax
0x180031f97  lock inc cs:qword_180086918
0x180031f9f  mov     rdx, [rbp+var_28]
0x180031fa3  xor     eax, eax
0x180031fa5  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031fae  jnz     short loc_180031FC9
0x180031fb0  mov     [rbp+var_60], rsi
0x180031fb4  lea     rdx, stru_180086920; ListEntry
0x180031fbb  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180031fc2  call    WINRT_IMPL_InterlockedPushEntrySList
0x180031fc7  mov     ebx, esi
0x180031fc9  lea     rdx, ??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031fd0  mov     rcx, rdi
0x180031fd3  call    ??R_lambda_1_@?1??IsEmbeddingsGeneratorAvailableForOptions@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@345678@@Z@QEBA@AEBUISemanticImageIndexStoreStatics2@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsEmbeddingsGeneratorAvailableForOptions(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2 const &)
0x180031fd8  movzx   edi, al
0x180031fdb  lock dec cs:qword_180086918
0x180031fe3  jmp     short loc_18003201D
0x180031fe5  mov     [rbp+var_18], 0
0x180031fe9  mov     dword ptr [rbp+var_28], 300h
0x180031ff0  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031ff7  mov     [rbp+var_20], rax
0x180031ffb  mov     rdx, [rdi]
0x180031ffe  mov     rax, [rbx]
0x180032001  lea     r8, [rbp+var_18]
0x180032005  mov     rdx, [rdx]
0x180032008  mov     rcx, rbx
0x18003200b  mov     rax, [rax+30h]
0x18003200f  call    cs:__guard_dispatch_icall_fptr
0x180032015  test    eax, eax
0x180032017  js      short loc_180032054
0x180032019  movzx   edi, [rbp+var_18]
0x18003201d  test    rbx, rbx
0x180032020  jz      short loc_18003202B
0x180032022  lea     rcx, [rbp+var_60]
0x180032026  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003202b  movzx   eax, dil
0x18003202f  mov     rcx, [rbp+var_10]
0x180032033  xor     rcx, rsp; StackCookie
0x180032036  call    __security_check_cookie
0x18003203b  lea     r11, [rsp+80h+var_s0]
0x180032043  mov     rbx, [r11+10h]
0x180032047  mov     rsi, [r11+20h]
0x18003204b  mov     rdi, [r11+28h]
0x18003204f  mov     rsp, r11
0x180032052  pop     rbp
0x180032053  retn
0x180032054  lfence
0x180032057  lea     rdx, [rbp+var_28]
0x18003205b  mov     ecx, eax
0x18003205d  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180032063  lfence
0x180032066  lea     rdx, [rbp+var_60]
0x18003206a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
