# ??$call@AEAV_lambda_1_@?1??IsAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003e010`
- end: `0x18003e1c0`
- name: `??$call@AEAV_lambda_1_@?1??IsAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180037ff0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003df90`
- `0x18003e010`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003e140`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003e04b`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsAvailable_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsAvailable_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
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
    v11 = &qword_180086A78;
    _InterlockedIncrement64(&qword_180086A78);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
            v12[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A80);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsAvailable'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>);
    _InterlockedDecrement64(&qword_180086A78);
  }
  else
  {
    v13[0] = 0;
    LODWORD(v12[0]) = 1156;
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
0x18003e010  mov     [rsp-8+arg_0], rbx
0x18003e015  mov     [rsp-8+arg_10], rsi
0x18003e01a  mov     [rsp-8+arg_18], rdi
0x18003e01f  push    rbp
0x18003e020  mov     rbp, rsp
0x18003e023  sub     rsp, 80h
0x18003e02a  mov     rax, cs:__security_cookie
0x18003e031  xor     rax, rsp
0x18003e034  mov     [rbp+var_10], rax
0x18003e038  mov     rdi, rdx
0x18003e03b  xor     esi, esi
0x18003e03d  mov     [rbp+var_48], 1
0x18003e044  mov     [rbp+var_44], 49h ; 'I'
0x18003e04b  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003e052  mov     [rbp+var_38], rax
0x18003e056  lea     rax, [rbp+var_48]
0x18003e05a  mov     [rbp+var_50], rax
0x18003e05e  mov     [rbp+var_28], rsi
0x18003e062  mov     dword ptr [rbp+var_60], 1804h
0x18003e069  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003e070  mov     [rbp+var_58], rax
0x18003e074  lea     r9, [rbp+var_28]
0x18003e078  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003e07f  lea     rdx, [rbp+var_50]
0x18003e083  lea     rcx, [rbp+var_30]
0x18003e087  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003e08c  mov     ecx, dword ptr [rbp+var_30]
0x18003e08f  test    ecx, ecx
0x18003e091  js      loc_18003E1B3
0x18003e097  mov     rbx, [rbp+var_28]
0x18003e09b  mov     [rbp+var_60], rbx
0x18003e09f  test    rbx, rbx
0x18003e0a2  jz      loc_18003E135
0x18003e0a8  mov     [rbp+var_30], rsi
0x18003e0ac  mov     rax, [rbx]
0x18003e0af  lea     r8, [rbp+var_30]
0x18003e0b3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003e0ba  mov     rcx, rbx
0x18003e0bd  mov     rax, [rax]
0x18003e0c0  call    cs:__guard_dispatch_icall_fptr
0x18003e0c6  mov     rax, [rbp+var_30]
0x18003e0ca  mov     [rbp+var_30], rax
0x18003e0ce  test    rax, rax
0x18003e0d1  jz      short loc_18003E135
0x18003e0d3  lea     rcx, [rbp+var_30]
0x18003e0d7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003e0dc  lea     rax, qword_180086A78
0x18003e0e3  mov     [rbp+var_30], rax
0x18003e0e7  lock inc cs:qword_180086A78
0x18003e0ef  mov     rdx, [rbp+var_28]
0x18003e0f3  xor     eax, eax
0x18003e0f5  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003e0fe  jnz     short loc_18003E119
0x18003e100  mov     [rbp+var_60], rsi
0x18003e104  lea     rdx, stru_180086A80; ListEntry
0x18003e10b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003e112  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003e117  mov     ebx, esi
0x18003e119  lea     rdx, ??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003e120  mov     rcx, rdi
0x18003e123  call    ??R_lambda_1_@?1??IsAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@345678@@Z@QEBA@AEBUISemanticTextIndexStoreStatics@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsAvailable(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics const &)
0x18003e128  movzx   edi, al
0x18003e12b  lock dec cs:qword_180086A78
0x18003e133  jmp     short loc_18003E16D
0x18003e135  mov     [rbp+var_18], 0
0x18003e139  mov     dword ptr [rbp+var_28], 484h
0x18003e140  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003e147  mov     [rbp+var_20], rax
0x18003e14b  mov     rdx, [rdi]
0x18003e14e  mov     rax, [rbx]
0x18003e151  lea     r8, [rbp+var_18]
0x18003e155  mov     rdx, [rdx]
0x18003e158  mov     rcx, rbx
0x18003e15b  mov     rax, [rax+30h]
0x18003e15f  call    cs:__guard_dispatch_icall_fptr
0x18003e165  test    eax, eax
0x18003e167  js      short loc_18003E1A4
0x18003e169  movzx   edi, [rbp+var_18]
0x18003e16d  test    rbx, rbx
0x18003e170  jz      short loc_18003E17B
0x18003e172  lea     rcx, [rbp+var_60]
0x18003e176  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003e17b  movzx   eax, dil
0x18003e17f  mov     rcx, [rbp+var_10]
0x18003e183  xor     rcx, rsp; StackCookie
0x18003e186  call    __security_check_cookie
0x18003e18b  lea     r11, [rsp+80h+var_s0]
0x18003e193  mov     rbx, [r11+10h]
0x18003e197  mov     rsi, [r11+20h]
0x18003e19b  mov     rdi, [r11+28h]
0x18003e19f  mov     rsp, r11
0x18003e1a2  pop     rbp
0x18003e1a3  retn
0x18003e1a4  lfence
0x18003e1a7  lea     rdx, [rbp+var_28]
0x18003e1ab  mov     ecx, eax
0x18003e1ad  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003e1b3  lfence
0x18003e1b6  lea     rdx, [rbp+var_60]
0x18003e1ba  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
