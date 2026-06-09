# ??$call@AEAV_lambda_65__@?0???0SemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@AEBUhstring@param@8@AEBW4IndexCreationDisposition@345678@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@8@@Z@@?$factory_cache_entry@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_65__@?0???0SemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@QEAA@AEBUhstring@param@2@AEBW4IndexCreationDisposition@567892@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@2@@Z@@Z

- ea: `0x1800327d0`
- end: `0x1800329f4`
- name: `??$call@AEAV_lambda_65__@?0???0SemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@QEAA@AEBUhstring@param@8@AEBW4IndexCreationDisposition@345678@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@8@@Z@@?$factory_cache_entry@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_65__@?0???0SemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@QEAA@AEBUhstring@param@2@AEBW4IndexCreationDisposition@567892@AEBU?$IReference@Uguid@winrt@@@Foundation@Windows@2@@Z@@Z`
- size: `548`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18001e330`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800327d0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800328f1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180032956`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180032813`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStoreOptions`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_65____0___0SemanticImageIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__QEAA_AEBUhstring_param_8_AEBW4IndexCreationDisposition_345678_AEBU__IReference_Uguid_winrt___Foundation_Windows_8__Z____factory_cache_entry_USemanticImageIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreOptionsFactory2_234567__impl_winrt__QEAA_A_PAEAV_lambda_65____0___0SemanticImageIndexStoreOptions_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_QEAA_AEBUhstring_param_2_AEBW4IndexCreationDisposition_567892_AEBU__IReference_Uguid_winrt___Foundation_Windows_2__Z__Z(
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
  v13[1] = 81;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStoreOptions";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>,
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
    LODWORD(v10) = 668;
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
  v10 = &qword_1800869C8;
  _InterlockedIncrement64(&qword_1800869C8);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_1800869D0);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 668;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>
                                                                             + 48LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>,
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
  _InterlockedDecrement64(&qword_1800869C8);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800327d0  mov     [rsp-8+arg_0], rbx
0x1800327d5  mov     [rsp-8+arg_18], rsi
0x1800327da  push    rbp
0x1800327db  push    rdi
0x1800327dc  push    r14
0x1800327de  lea     rbp, [rsp-47h]
0x1800327e3  sub     rsp, 90h
0x1800327ea  mov     rax, cs:__security_cookie
0x1800327f1  xor     rax, rsp
0x1800327f4  mov     [rbp+57h+var_18], rax
0x1800327f8  mov     rsi, r8
0x1800327fb  mov     rdi, rdx
0x1800327fe  mov     [rbp+57h+var_30], rdx
0x180032802  xor     r14d, r14d
0x180032805  mov     [rbp+57h+var_48], 1
0x18003280c  mov     [rbp+57h+var_44], 51h ; 'Q'
0x180032813  lea     rax, aMicrosoftAsgSe_2; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003281a  mov     [rbp+57h+var_38], rax
0x18003281e  lea     rax, [rbp+57h+var_48]
0x180032822  mov     [rbp+57h+var_50], rax
0x180032826  mov     [rbp+57h+var_28], r14
0x18003282a  mov     dword ptr [rbp+57h+var_68], 1804h
0x180032831  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032838  mov     [rbp+57h+var_60], rax
0x18003283c  lea     r9, [rbp+57h+var_28]
0x180032840  lea     r8, ??$guid_v@UISemanticImageIndexStoreOptionsFactory2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>
0x180032847  lea     rdx, [rbp+57h+var_50]
0x18003284b  lea     rcx, [rbp+57h+var_70]
0x18003284f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180032854  mov     ecx, dword ptr [rbp+57h+var_70]
0x180032857  test    ecx, ecx
0x180032859  js      loc_1800329D8
0x18003285f  mov     rbx, [rbp+57h+var_28]
0x180032863  mov     [rbp+57h+var_70], rbx
0x180032867  test    rbx, rbx
0x18003286a  jz      loc_18003294B
0x180032870  mov     [rbp+57h+var_30], r14
0x180032874  mov     rax, [rbx]
0x180032877  lea     r8, [rbp+57h+var_30]
0x18003287b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180032882  mov     rcx, rbx
0x180032885  mov     rax, [rax]
0x180032888  call    cs:__guard_dispatch_icall_fptr
0x18003288e  mov     rax, [rbp+57h+var_30]
0x180032892  mov     [rbp+57h+var_30], rax
0x180032896  test    rax, rax
0x180032899  jz      loc_18003294B
0x18003289f  lea     rcx, [rbp+57h+var_30]
0x1800328a3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800328a8  lea     rax, qword_1800869C8
0x1800328af  mov     [rbp+57h+var_68], rax
0x1800328b3  lock inc cs:qword_1800869C8
0x1800328bb  mov     rcx, [rbp+57h+var_28]
0x1800328bf  xor     eax, eax
0x1800328c1  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>
0x1800328ca  jnz     short loc_1800328E6
0x1800328cc  mov     [rbp+57h+var_70], r14
0x1800328d0  lea     rdx, stru_1800869D0; ListEntry
0x1800328d7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800328de  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800328e3  mov     ebx, r14d
0x1800328e6  mov     [rbp+57h+var_30], r14
0x1800328ea  mov     dword ptr [rbp+57h+var_28], 29Ch
0x1800328f1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800328f8  mov     [rbp+57h+var_20], rax
0x1800328fc  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStoreOptions@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreOptionsFactory2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreOptionsFactory2>
0x180032903  mov     r9, [rsi+10h]
0x180032907  mov     r8, [rsi+8]
0x18003290b  mov     rdx, [rsi]
0x18003290e  mov     rax, [rcx]
0x180032911  lea     r10, [rbp+57h+var_30]
0x180032915  mov     [rsp+0A0h+var_80], r10
0x18003291a  mov     r9, [r9]
0x18003291d  mov     r8d, [r8]
0x180032920  mov     rdx, [rdx]
0x180032923  mov     rax, [rax+30h]
0x180032927  call    cs:__guard_dispatch_icall_fptr
0x18003292d  test    eax, eax
0x18003292f  js      loc_1800329E5
0x180032935  mov     rcx, [rbp+57h+var_30]
0x180032939  mov     [rdi], rcx
0x18003293c  lock dec cs:qword_1800869C8
0x180032944  test    rbx, rbx
0x180032947  jz      short loc_1800329A2
0x180032949  jmp     short loc_180032999
0x18003294b  mov     [rbp+57h+var_30], r14
0x18003294f  mov     dword ptr [rbp+57h+var_68], 29Ch
0x180032956  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003295d  mov     [rbp+57h+var_60], rax
0x180032961  mov     r9, [rsi+10h]
0x180032965  mov     r8, [rsi+8]
0x180032969  mov     rdx, [rsi]
0x18003296c  mov     rax, [rbx]
0x18003296f  lea     rcx, [rbp+57h+var_30]
0x180032973  mov     [rsp+0A0h+var_80], rcx
0x180032978  mov     r9, [r9]
0x18003297b  mov     r8d, [r8]
0x18003297e  mov     rdx, [rdx]
0x180032981  mov     rcx, rbx
0x180032984  mov     rax, [rax+30h]
0x180032988  call    cs:__guard_dispatch_icall_fptr
0x18003298e  test    eax, eax
0x180032990  js      short loc_1800329C9
0x180032992  mov     rax, [rbp+57h+var_30]
0x180032996  mov     [rdi], rax
0x180032999  lea     rcx, [rbp+57h+var_70]
0x18003299d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800329a2  mov     rax, rdi
0x1800329a5  mov     rcx, [rbp+57h+var_18]
0x1800329a9  xor     rcx, rsp; StackCookie
0x1800329ac  call    __security_check_cookie
0x1800329b1  lea     r11, [rsp+0A0h+var_10]
0x1800329b9  mov     rbx, [r11+20h]
0x1800329bd  mov     rsi, [r11+38h]
0x1800329c1  mov     rsp, r11
0x1800329c4  pop     r14
0x1800329c6  pop     rdi
0x1800329c7  pop     rbp
0x1800329c8  retn
0x1800329c9  lfence
0x1800329cc  lea     rdx, [rbp+57h+var_68]
0x1800329d0  mov     ecx, eax
0x1800329d2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800329d8  lfence
0x1800329db  lea     rdx, [rbp+57h+var_68]
0x1800329df  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800329e5  lfence
0x1800329e8  lea     rdx, [rbp+57h+var_28]
0x1800329ec  mov     ecx, eax
0x1800329ee  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
