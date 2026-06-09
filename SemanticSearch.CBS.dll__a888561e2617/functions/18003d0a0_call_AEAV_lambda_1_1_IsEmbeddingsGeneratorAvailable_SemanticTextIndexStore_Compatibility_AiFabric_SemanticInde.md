# ??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x18003d0a0`
- end: `0x18003d258`
- name: `??$call@AEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsEmbeddingsGeneratorAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `440`
- prototype: `__int64 __fastcall(__int64, __int128 **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180038820`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003d020`
- `0x18003d0a0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003d1d3`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003d0db`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsEmbeddingsGeneratorAvailable_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsEmbeddingsGeneratorAvailable_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
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
  v10[1] = 73;
  v11 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v9 = v10;
  v13[0] = 0;
  LODWORD(v8[0]) = 6148;
  v8[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v12,
    &v9,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
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
    *(_QWORD *)&v12 = &qword_180086A78;
    _InterlockedIncrement64(&qword_180086A78);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
            v13[0],
            0) )
    {
      v8[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A80);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailable'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>);
    _InterlockedDecrement64(&qword_180086A78);
  }
  else
  {
    v5 = *a2;
    v14[0] = 0;
    LODWORD(v13[0]) = 1192;
    v13[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Gener"
                             "ated Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v12 = *v5;
    v6 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _BYTE *))(*(_QWORD *)v3 + 96LL))(v3, &v12, v14);
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
0x18003d0a0  mov     [rsp-8+arg_0], rbx
0x18003d0a5  mov     [rsp-8+arg_10], rsi
0x18003d0aa  mov     [rsp-8+arg_18], rdi
0x18003d0af  push    rbp
0x18003d0b0  mov     rbp, rsp
0x18003d0b3  sub     rsp, 80h
0x18003d0ba  mov     rax, cs:__security_cookie
0x18003d0c1  xor     rax, rsp
0x18003d0c4  mov     [rbp+var_8], rax
0x18003d0c8  mov     rdi, rdx
0x18003d0cb  xor     esi, esi
0x18003d0cd  mov     [rbp+var_48], 1
0x18003d0d4  mov     [rbp+var_44], 49h ; 'I'
0x18003d0db  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003d0e2  mov     [rbp+var_38], rax
0x18003d0e6  lea     rax, [rbp+var_48]
0x18003d0ea  mov     [rbp+var_50], rax
0x18003d0ee  mov     [rbp+var_20], rsi
0x18003d0f2  mov     dword ptr [rbp+var_60], 1804h
0x18003d0f9  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d100  mov     [rbp+var_58], rax
0x18003d104  lea     r9, [rbp+var_20]
0x18003d108  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003d10f  lea     rdx, [rbp+var_50]
0x18003d113  lea     rcx, [rbp+var_30]
0x18003d117  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003d11c  mov     ecx, dword ptr [rbp+var_30]
0x18003d11f  test    ecx, ecx
0x18003d121  js      loc_18003D24B
0x18003d127  mov     rbx, [rbp+var_20]
0x18003d12b  mov     [rbp+var_60], rbx
0x18003d12f  test    rbx, rbx
0x18003d132  jz      loc_18003D1C5
0x18003d138  mov     qword ptr [rbp+var_30], rsi
0x18003d13c  mov     rax, [rbx]
0x18003d13f  lea     r8, [rbp+var_30]
0x18003d143  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003d14a  mov     rcx, rbx
0x18003d14d  mov     rax, [rax]
0x18003d150  call    cs:__guard_dispatch_icall_fptr
0x18003d156  mov     rax, qword ptr [rbp+var_30]
0x18003d15a  mov     qword ptr [rbp+var_30], rax
0x18003d15e  test    rax, rax
0x18003d161  jz      short loc_18003D1C5
0x18003d163  lea     rcx, [rbp+var_30]
0x18003d167  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d16c  lea     rax, qword_180086A78
0x18003d173  mov     qword ptr [rbp+var_30], rax
0x18003d177  lock inc cs:qword_180086A78
0x18003d17f  mov     rdx, [rbp+var_20]
0x18003d183  xor     eax, eax
0x18003d185  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003d18e  jnz     short loc_18003D1A9
0x18003d190  mov     [rbp+var_60], rsi
0x18003d194  lea     rdx, stru_180086A80; ListEntry
0x18003d19b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003d1a2  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003d1a7  mov     ebx, esi
0x18003d1a9  lea     rdx, ??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003d1b0  mov     rcx, rdi
0x18003d1b3  call    ??R_lambda_1_@?1??IsEmbeddingsGeneratorAvailable@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@8@@Z@QEBA@AEBUISemanticTextIndexStoreStatics@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore::IsEmbeddingsGeneratorAvailable(winrt::guid const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics const &)
0x18003d1b8  movzx   edi, al
0x18003d1bb  lock dec cs:qword_180086A78
0x18003d1c3  jmp     short loc_18003D205
0x18003d1c5  mov     rax, [rdi]
0x18003d1c8  mov     [rbp+var_10], 0
0x18003d1cc  mov     dword ptr [rbp+var_20], 4A8h
0x18003d1d3  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003d1da  mov     [rbp+var_18], rcx
0x18003d1de  movups  xmm0, xmmword ptr [rax]
0x18003d1e1  movaps  [rbp+var_30], xmm0
0x18003d1e5  mov     rax, [rbx]
0x18003d1e8  lea     r8, [rbp+var_10]
0x18003d1ec  lea     rdx, [rbp+var_30]
0x18003d1f0  mov     rcx, rbx
0x18003d1f3  mov     rax, [rax+60h]
0x18003d1f7  call    cs:__guard_dispatch_icall_fptr
0x18003d1fd  test    eax, eax
0x18003d1ff  js      short loc_18003D23C
0x18003d201  movzx   edi, [rbp+var_10]
0x18003d205  test    rbx, rbx
0x18003d208  jz      short loc_18003D213
0x18003d20a  lea     rcx, [rbp+var_60]
0x18003d20e  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003d213  movzx   eax, dil
0x18003d217  mov     rcx, [rbp+var_8]
0x18003d21b  xor     rcx, rsp; StackCookie
0x18003d21e  call    __security_check_cookie
0x18003d223  lea     r11, [rsp+80h+var_s0]
0x18003d22b  mov     rbx, [r11+10h]
0x18003d22f  mov     rsi, [r11+20h]
0x18003d233  mov     rdi, [r11+28h]
0x18003d237  mov     rsp, r11
0x18003d23a  pop     rbp
0x18003d23b  retn
0x18003d23c  lfence
0x18003d23f  lea     rdx, [rbp+var_20]
0x18003d243  mov     ecx, eax
0x18003d245  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003d24b  lfence
0x18003d24e  lea     rdx, [rbp+var_60]
0x18003d252  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
