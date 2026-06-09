# ??$call@AEAV_lambda_68__@?0???0SemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@AEBUhstring@param@8@AEBW4IndexCreationDisposition@345678@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@8@@Z@@?$factory_cache_entry@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_68__@?0???0SemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@QEAA@AEBUhstring@param@2@AEBW4IndexCreationDisposition@567892@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@2@@Z@@Z

- ea: `0x18003e1c0`
- end: `0x18003e3e4`
- name: `??$call@AEAV_lambda_68__@?0???0SemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@AEBUhstring@param@8@AEBW4IndexCreationDisposition@345678@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@8@@Z@@?$factory_cache_entry@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_68__@?0???0SemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@QEAA@AEBUhstring@param@2@AEBW4IndexCreationDisposition@567892@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@2@@Z@@Z`
- size: `548`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180037490`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003e1c0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003e2e1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003e346`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003e203`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStoreOptions`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_68____0___0SemanticTextIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AEBUhstring_param_8_AEBW4IndexCreationDisposition_345678_AEBU__IReference_Uguid_winrt___Foundation_Windows_8__Z____factory_cache_entry_USemanticTextIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreOptionsFactory2_234567__impl_winrt__QEAA_A_PAEAV_lambda_68____0___0SemanticTextIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_QEAA_AEBUhstring_param_2_AEBW4IndexCreationDisposition_567892_AEBU__IReference_Uguid_winrt___Foundation_Windows_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  signed __int64 v5; // rbx
  int v6; // eax
  int v7; // eax
  signed __int64 v9; // [rsp+30h] [rbp-19h] BYREF
  __int64 *v10; // [rsp+38h] [rbp-11h] BYREF
  const char *v11; // [rsp+40h] [rbp-9h]
  _DWORD *v12; // [rsp+50h] [rbp+7h] BYREF
  _DWORD v13[4]; // [rsp+58h] [rbp+Fh] BYREF
  const wchar_t *v14; // [rsp+68h] [rbp+1Fh]
  _QWORD *v15; // [rsp+70h] [rbp+27h] BYREF
  signed __int64 v16[2]; // [rsp+78h] [rbp+2Fh] BYREF

  v15 = a2;
  v13[0] = 1;
  v13[1] = 80;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStoreOptions";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>,
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
    LODWORD(v10) = 1150;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)v5 + 48LL))(
           v5,
           **(_QWORD **)a3,
           **(unsigned int **)(a3 + 8),
           **(_QWORD **)(a3 + 16),
           &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086A98;
  _InterlockedIncrement64(&qword_180086A98);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086AA0);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 1150;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>
                                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>,
         **(_QWORD **)a3,
         **(unsigned int **)(a3 + 8),
         **(_QWORD **)(a3 + 16),
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086A98);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18003e1c0  mov     [rsp-8+arg_0], rbx
0x18003e1c5  mov     [rsp-8+arg_18], rsi
0x18003e1ca  push    rbp
0x18003e1cb  push    rdi
0x18003e1cc  push    r14
0x18003e1ce  lea     rbp, [rsp-47h]
0x18003e1d3  sub     rsp, 90h
0x18003e1da  mov     rax, cs:__security_cookie
0x18003e1e1  xor     rax, rsp
0x18003e1e4  mov     [rbp+57h+var_18], rax
0x18003e1e8  mov     rsi, r8
0x18003e1eb  mov     rdi, rdx
0x18003e1ee  mov     [rbp+57h+var_30], rdx
0x18003e1f2  xor     r14d, r14d
0x18003e1f5  mov     [rbp+57h+var_48], 1
0x18003e1fc  mov     [rbp+57h+var_44], 50h ; 'P'
0x18003e203  lea     rax, aMicrosoftAsgSe_8; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003e20a  mov     [rbp+57h+var_38], rax
0x18003e20e  lea     rax, [rbp+57h+var_48]
0x18003e212  mov     [rbp+57h+var_50], rax
0x18003e216  mov     [rbp+57h+var_28], r14
0x18003e21a  mov     dword ptr [rbp+57h+var_68], 1804h
0x18003e221  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003e228  mov     [rbp+57h+var_60], rax
0x18003e22c  lea     r9, [rbp+57h+var_28]
0x18003e230  lea     r8, ??$guid_v@UISemanticTextIndexStoreOptionsFactory2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>
0x18003e237  lea     rdx, [rbp+57h+var_50]
0x18003e23b  lea     rcx, [rbp+57h+var_70]
0x18003e23f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003e244  mov     ecx, dword ptr [rbp+57h+var_70]
0x18003e247  test    ecx, ecx
0x18003e249  js      loc_18003E3C8
0x18003e24f  mov     rbx, [rbp+57h+var_28]
0x18003e253  mov     [rbp+57h+var_70], rbx
0x18003e257  test    rbx, rbx
0x18003e25a  jz      loc_18003E33B
0x18003e260  mov     [rbp+57h+var_30], r14
0x18003e264  mov     rax, [rbx]
0x18003e267  lea     r8, [rbp+57h+var_30]
0x18003e26b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003e272  mov     rcx, rbx
0x18003e275  mov     rax, [rax]
0x18003e278  call    cs:__guard_dispatch_icall_fptr
0x18003e27e  mov     rax, [rbp+57h+var_30]
0x18003e282  mov     [rbp+57h+var_30], rax
0x18003e286  test    rax, rax
0x18003e289  jz      loc_18003E33B
0x18003e28f  lea     rcx, [rbp+57h+var_30]
0x18003e293  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003e298  lea     rax, qword_180086A98
0x18003e29f  mov     [rbp+57h+var_68], rax
0x18003e2a3  lock inc cs:qword_180086A98
0x18003e2ab  mov     rcx, [rbp+57h+var_28]
0x18003e2af  xor     eax, eax
0x18003e2b1  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>
0x18003e2ba  jnz     short loc_18003E2D6
0x18003e2bc  mov     [rbp+57h+var_70], r14
0x18003e2c0  lea     rdx, stru_180086AA0; ListEntry
0x18003e2c7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003e2ce  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003e2d3  mov     ebx, r14d
0x18003e2d6  mov     [rbp+57h+var_30], r14
0x18003e2da  mov     dword ptr [rbp+57h+var_28], 47Eh
0x18003e2e1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003e2e8  mov     [rbp+57h+var_20], rax
0x18003e2ec  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreOptionsFactory2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreOptionsFactory2>
0x18003e2f3  mov     r9, [rsi+10h]
0x18003e2f7  mov     r8, [rsi+8]
0x18003e2fb  mov     rdx, [rsi]
0x18003e2fe  mov     rax, [rcx]
0x18003e301  lea     r10, [rbp+57h+var_30]
0x18003e305  mov     [rsp+0A0h+var_80], r10
0x18003e30a  mov     r9, [r9]
0x18003e30d  mov     r8d, [r8]
0x18003e310  mov     rdx, [rdx]
0x18003e313  mov     rax, [rax+30h]
0x18003e317  call    cs:__guard_dispatch_icall_fptr
0x18003e31d  test    eax, eax
0x18003e31f  js      loc_18003E3D5
0x18003e325  mov     rcx, [rbp+57h+var_30]
0x18003e329  mov     [rdi], rcx
0x18003e32c  lock dec cs:qword_180086A98
0x18003e334  test    rbx, rbx
0x18003e337  jz      short loc_18003E392
0x18003e339  jmp     short loc_18003E389
0x18003e33b  mov     [rbp+57h+var_30], r14
0x18003e33f  mov     dword ptr [rbp+57h+var_68], 47Eh
0x18003e346  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003e34d  mov     [rbp+57h+var_60], rax
0x18003e351  mov     r9, [rsi+10h]
0x18003e355  mov     r8, [rsi+8]
0x18003e359  mov     rdx, [rsi]
0x18003e35c  mov     rax, [rbx]
0x18003e35f  lea     rcx, [rbp+57h+var_30]
0x18003e363  mov     [rsp+0A0h+var_80], rcx
0x18003e368  mov     r9, [r9]
0x18003e36b  mov     r8d, [r8]
0x18003e36e  mov     rdx, [rdx]
0x18003e371  mov     rcx, rbx
0x18003e374  mov     rax, [rax+30h]
0x18003e378  call    cs:__guard_dispatch_icall_fptr
0x18003e37e  test    eax, eax
0x18003e380  js      short loc_18003E3B9
0x18003e382  mov     rax, [rbp+57h+var_30]
0x18003e386  mov     [rdi], rax
0x18003e389  lea     rcx, [rbp+57h+var_70]
0x18003e38d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003e392  mov     rax, rdi
0x18003e395  mov     rcx, [rbp+57h+var_18]
0x18003e399  xor     rcx, rsp; StackCookie
0x18003e39c  call    __security_check_cookie
0x18003e3a1  lea     r11, [rsp+0A0h+var_10]
0x18003e3a9  mov     rbx, [r11+20h]
0x18003e3ad  mov     rsi, [r11+38h]
0x18003e3b1  mov     rsp, r11
0x18003e3b4  pop     r14
0x18003e3b6  pop     rdi
0x18003e3b7  pop     rbp
0x18003e3b8  retn
0x18003e3b9  lfence
0x18003e3bc  lea     rdx, [rbp+57h+var_68]
0x18003e3c0  mov     ecx, eax
0x18003e3c2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003e3c8  lfence
0x18003e3cb  lea     rdx, [rbp+57h+var_68]
0x18003e3cf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003e3d5  lfence
0x18003e3d8  lea     rdx, [rbp+57h+var_28]
0x18003e3dc  mov     ecx, eax
0x18003e3de  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
