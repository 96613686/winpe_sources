# ??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x18003ca30`
- end: `0x18003cbf8`
- name: `??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `456`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038c70`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003ca30`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003cb42`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003cba6`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003ca61`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall ___call_AEAV_lambda_1___1__DeleteIndex_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__DeleteIndex_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2__Z__Z(
        __int64 a1,
        _QWORD **a2)
{
  void (__fastcall ***v3)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 result; // rax
  _QWORD v5[2]; // [rsp+20h] [rbp-50h] BYREF
  _DWORD *v6; // [rsp+30h] [rbp-40h] BYREF
  _DWORD v7[4]; // [rsp+38h] [rbp-38h] BYREF
  const wchar_t *v8; // [rsp+48h] [rbp-28h]
  __int64 *v9; // [rsp+50h] [rbp-20h] BYREF
  void (__fastcall ***v10)(_QWORD, __int64 *, __int64 **); // [rsp+58h] [rbp-18h] BYREF
  const char *v11; // [rsp+60h] [rbp-10h]

  v7[0] = 1;
  v7[1] = 73;
  v8 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v6 = v7;
  v10 = 0;
  LODWORD(v5[0]) = 6148;
  v5[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v6,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
    (__int64)&v10);
  if ( (int)v9 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v9, v5);
  }
  v3 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v10;
  v5[0] = v10;
  if ( v10 && (v9 = 0, (**v10)(v10, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v9), v9) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
    v9 = &qword_180086A78;
    _InterlockedIncrement64(&qword_180086A78);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
            (signed __int64)v10,
            0) )
    {
      v3 = 0;
      v5[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A80);
    }
    LODWORD(v10) = 1209;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
                                                        + 120LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
               **a2);
    if ( (int)result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, &v10);
    }
    _InterlockedDecrement64(&qword_180086A78);
  }
  else
  {
    LODWORD(v10) = 1209;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD))(*v3)[15])(v3, **a2);
    if ( (int)result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, &v10);
    }
  }
  if ( v3 )
    return winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(v5);
  return result;
}

```

## disassembly

```asm
0x18003ca30  mov     [rsp-8+arg_0], rbx
0x18003ca35  mov     [rsp-8+arg_10], rdi
0x18003ca3a  push    rbp
0x18003ca3b  mov     rbp, rsp
0x18003ca3e  sub     rsp, 70h
0x18003ca42  mov     rax, cs:__security_cookie
0x18003ca49  xor     rax, rsp
0x18003ca4c  mov     [rbp+var_8], rax
0x18003ca50  mov     rdi, rdx
0x18003ca53  mov     [rbp+var_38], 1
0x18003ca5a  mov     [rbp+var_34], 49h ; 'I'
0x18003ca61  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003ca68  mov     [rbp+var_28], rax
0x18003ca6c  lea     rax, [rbp+var_38]
0x18003ca70  mov     [rbp+var_40], rax
0x18003ca74  mov     [rbp+var_18], 0
0x18003ca7c  mov     dword ptr [rbp+var_50], 1804h
0x18003ca83  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003ca8a  mov     [rbp+var_48], rax
0x18003ca8e  lea     r9, [rbp+var_18]
0x18003ca92  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003ca99  lea     rdx, [rbp+var_40]
0x18003ca9d  lea     rcx, [rbp+var_20]
0x18003caa1  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003caa6  mov     ecx, dword ptr [rbp+var_20]
0x18003caa9  test    ecx, ecx
0x18003caab  js      loc_18003CBEB
0x18003cab1  mov     rbx, [rbp+var_18]
0x18003cab5  mov     [rbp+var_50], rbx
0x18003cab9  test    rbx, rbx
0x18003cabc  jz      loc_18003CB9F
0x18003cac2  mov     [rbp+var_20], 0
0x18003caca  mov     rax, [rbx]
0x18003cacd  lea     r8, [rbp+var_20]
0x18003cad1  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003cad8  mov     rcx, rbx
0x18003cadb  mov     rax, [rax]
0x18003cade  call    cs:__guard_dispatch_icall_fptr
0x18003cae4  mov     rax, [rbp+var_20]
0x18003cae8  mov     [rbp+var_20], rax
0x18003caec  test    rax, rax
0x18003caef  jz      loc_18003CB9F
0x18003caf5  lea     rcx, [rbp+var_20]
0x18003caf9  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003cafe  lea     rax, qword_180086A78
0x18003cb05  mov     [rbp+var_20], rax
0x18003cb09  lock inc cs:qword_180086A78
0x18003cb11  mov     rcx, [rbp+var_18]
0x18003cb15  xor     eax, eax
0x18003cb17  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003cb20  jnz     short loc_18003CB3B
0x18003cb22  xor     ebx, ebx
0x18003cb24  mov     [rbp+var_50], rbx
0x18003cb28  lea     rdx, stru_180086A80; ListEntry
0x18003cb2f  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003cb36  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003cb3b  mov     dword ptr [rbp+var_18], 4B9h
0x18003cb42  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003cb49  mov     [rbp+var_10], rax
0x18003cb4d  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003cb54  mov     rdx, [rdi]
0x18003cb57  mov     rax, [rcx]
0x18003cb5a  mov     rdx, [rdx]
0x18003cb5d  mov     rax, [rax+78h]
0x18003cb61  call    cs:__guard_dispatch_icall_fptr
0x18003cb67  test    eax, eax
0x18003cb69  js      short loc_18003CBCD
0x18003cb6b  lock dec cs:qword_180086A78
0x18003cb73  test    rbx, rbx
0x18003cb76  jz      short loc_18003CB81
0x18003cb78  lea     rcx, [rbp+var_50]
0x18003cb7c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003cb81  mov     rcx, [rbp+var_8]
0x18003cb85  xor     rcx, rsp; StackCookie
0x18003cb88  call    __security_check_cookie
0x18003cb8d  lea     r11, [rsp+70h+var_s0]
0x18003cb92  mov     rbx, [r11+10h]
0x18003cb96  mov     rdi, [r11+20h]
0x18003cb9a  mov     rsp, r11
0x18003cb9d  pop     rbp
0x18003cb9e  retn
0x18003cb9f  mov     dword ptr [rbp+var_18], 4B9h
0x18003cba6  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003cbad  mov     [rbp+var_10], rax
0x18003cbb1  mov     rdx, [rdi]
0x18003cbb4  mov     rax, [rbx]
0x18003cbb7  mov     rdx, [rdx]
0x18003cbba  mov     rcx, rbx
0x18003cbbd  mov     rax, [rax+78h]
0x18003cbc1  call    cs:__guard_dispatch_icall_fptr
0x18003cbc7  test    eax, eax
0x18003cbc9  js      short loc_18003CBDC
0x18003cbcb  jmp     short loc_18003CB73
0x18003cbcd  lfence
0x18003cbd0  lea     rdx, [rbp+var_18]
0x18003cbd4  mov     ecx, eax
0x18003cbd6  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003cbdc  lfence
0x18003cbdf  lea     rdx, [rbp+var_18]
0x18003cbe3  mov     ecx, eax
0x18003cbe5  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003cbeb  lfence
0x18003cbee  lea     rdx, [rbp+var_50]
0x18003cbf2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
