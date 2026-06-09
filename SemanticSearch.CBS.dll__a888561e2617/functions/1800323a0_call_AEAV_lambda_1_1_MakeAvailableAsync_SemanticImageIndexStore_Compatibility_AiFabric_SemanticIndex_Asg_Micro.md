# ??$call@AEAV_lambda_1_@?1??MakeAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x1800323a0`
- end: `0x18003259c`
- name: `??$call@AEAV_lambda_1_@?1??MakeAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001f8e0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800323a0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800324bf`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180032511`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800323e1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
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
    LODWORD(v10) = 680;
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
  v10 = &qword_180086938;
  _InterlockedIncrement64(&qword_180086938);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 680;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                             + 56LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086938);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800323a0  mov     [rsp-18h+arg_0], rbx
0x1800323a5  mov     [rsp-18h+arg_18], rsi
0x1800323aa  push    rbp
0x1800323ab  push    rdi
0x1800323ac  push    r14
0x1800323ae  mov     rbp, rsp
0x1800323b1  sub     rsp, 80h
0x1800323b8  mov     rax, cs:__security_cookie
0x1800323bf  xor     rax, rsp
0x1800323c2  mov     [rbp+var_8], rax
0x1800323c6  mov     rsi, r8
0x1800323c9  mov     rdi, rdx
0x1800323cc  mov     [rbp+var_20], rdx
0x1800323d0  xor     r14d, r14d
0x1800323d3  mov     [rbp+var_38], 1
0x1800323da  mov     [rbp+var_34], 4Ah ; 'J'
0x1800323e1  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800323e8  mov     [rbp+var_28], rax
0x1800323ec  lea     rax, [rbp+var_38]
0x1800323f0  mov     [rbp+var_40], rax
0x1800323f4  mov     [rbp+var_18], r14
0x1800323f8  mov     dword ptr [rbp+var_58], 1804h
0x1800323ff  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032406  mov     [rbp+var_50], rax
0x18003240a  lea     r9, [rbp+var_18]
0x18003240e  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180032415  lea     rdx, [rbp+var_40]
0x180032419  lea     rcx, [rbp+var_60]
0x18003241d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180032422  mov     ecx, dword ptr [rbp+var_60]
0x180032425  test    ecx, ecx
0x180032427  js      loc_180032580
0x18003242d  mov     rbx, [rbp+var_18]
0x180032431  mov     [rbp+var_60], rbx
0x180032435  test    rbx, rbx
0x180032438  jz      loc_180032506
0x18003243e  mov     [rbp+var_20], r14
0x180032442  mov     rax, [rbx]
0x180032445  lea     r8, [rbp+var_20]
0x180032449  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180032450  mov     rcx, rbx
0x180032453  mov     rax, [rax]
0x180032456  call    cs:__guard_dispatch_icall_fptr
0x18003245c  mov     rax, [rbp+var_20]
0x180032460  mov     [rbp+var_20], rax
0x180032464  test    rax, rax
0x180032467  jz      loc_180032506
0x18003246d  lea     rcx, [rbp+var_20]
0x180032471  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180032476  lea     rax, qword_180086938
0x18003247d  mov     [rbp+var_58], rax
0x180032481  lock inc cs:qword_180086938
0x180032489  mov     rcx, [rbp+var_18]
0x18003248d  xor     eax, eax
0x18003248f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180032498  jnz     short loc_1800324B4
0x18003249a  mov     [rbp+var_60], r14
0x18003249e  lea     rdx, stru_180086940; ListEntry
0x1800324a5  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800324ac  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800324b1  mov     ebx, r14d
0x1800324b4  mov     [rbp+var_20], r14
0x1800324b8  mov     dword ptr [rbp+var_18], 2A8h
0x1800324bf  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800324c6  mov     [rbp+var_10], rax
0x1800324ca  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800324d1  mov     rdx, [rsi]
0x1800324d4  mov     rax, [rcx]
0x1800324d7  lea     r8, [rbp+var_20]
0x1800324db  mov     rdx, [rdx]
0x1800324de  mov     rax, [rax+38h]
0x1800324e2  call    cs:__guard_dispatch_icall_fptr
0x1800324e8  test    eax, eax
0x1800324ea  js      loc_18003258D
0x1800324f0  mov     rcx, [rbp+var_20]
0x1800324f4  mov     [rdi], rcx
0x1800324f7  lock dec cs:qword_180086938
0x1800324ff  test    rbx, rbx
0x180032502  jz      short loc_18003254A
0x180032504  jmp     short loc_180032541
0x180032506  mov     [rbp+var_20], r14
0x18003250a  mov     dword ptr [rbp+var_58], 2A8h
0x180032511  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032518  mov     [rbp+var_50], rax
0x18003251c  mov     rdx, [rsi]
0x18003251f  mov     rax, [rbx]
0x180032522  lea     r8, [rbp+var_20]
0x180032526  mov     rdx, [rdx]
0x180032529  mov     rcx, rbx
0x18003252c  mov     rax, [rax+38h]
0x180032530  call    cs:__guard_dispatch_icall_fptr
0x180032536  test    eax, eax
0x180032538  js      short loc_180032571
0x18003253a  mov     rax, [rbp+var_20]
0x18003253e  mov     [rdi], rax
0x180032541  lea     rcx, [rbp+var_60]
0x180032545  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003254a  mov     rax, rdi
0x18003254d  mov     rcx, [rbp+var_8]
0x180032551  xor     rcx, rsp; StackCookie
0x180032554  call    __security_check_cookie
0x180032559  lea     r11, [rsp+80h+var_s0]
0x180032561  mov     rbx, [r11+20h]
0x180032565  mov     rsi, [r11+38h]
0x180032569  mov     rsp, r11
0x18003256c  pop     r14
0x18003256e  pop     rdi
0x18003256f  pop     rbp
0x180032570  retn
0x180032571  lfence
0x180032574  lea     rdx, [rbp+var_58]
0x180032578  mov     ecx, eax
0x18003257a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180032580  lfence
0x180032583  lea     rdx, [rbp+var_58]
0x180032587  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003258d  lfence
0x180032590  lea     rdx, [rbp+var_18]
0x180032594  mov     ecx, eax
0x180032596  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
