# ??$call@AEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x1800309e0`
- end: `0x180030bf4`
- name: `??$call@AEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeTextQueryEmbeddingsGeneratorAvailableAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `532`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180020900`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800309e0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180030b04`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030b61`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030a23`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeTextQueryEmbeddingsGeneratorAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeTextQueryEmbeddingsGeneratorAvailableAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
        __int64 a1,
        _QWORD *a2,
        __int128 **a3)
{
  signed __int64 v5; // rbx
  __int128 *v6; // rax
  int v7; // eax
  __int128 *v8; // rax
  int v9; // eax
  signed __int64 v11; // [rsp+20h] [rbp-29h] BYREF
  __int64 *v12; // [rsp+28h] [rbp-21h] BYREF
  const char *v13; // [rsp+30h] [rbp-19h]
  __int128 v14; // [rsp+40h] [rbp-9h] BYREF
  _DWORD *v15; // [rsp+50h] [rbp+7h] BYREF
  _DWORD v16[4]; // [rsp+58h] [rbp+Fh] BYREF
  const wchar_t *v17; // [rsp+68h] [rbp+1Fh]
  _QWORD *v18; // [rsp+70h] [rbp+27h] BYREF
  signed __int64 v19[2]; // [rsp+78h] [rbp+2Fh] BYREF

  v18 = a2;
  v16[0] = 1;
  v16[1] = 74;
  v17 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v15 = v16;
  v19[0] = 0;
  LODWORD(v12) = 6148;
  v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v15,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
    (__int64)v19);
  if ( (int)v11 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v11, &v12);
  }
  v5 = v19[0];
  v11 = v19[0];
  if ( !v19[0]
    || (v18 = 0,
        (**(void (__fastcall ***)(signed __int64, __int64 *, _QWORD **))v19[0])(
          v19[0],
          &winrt::impl::guid_v<winrt::impl::IAgileObject>,
          &v18),
        !v18) )
  {
    v8 = *a3;
    v18 = 0;
    LODWORD(v12) = 752;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v14 = *v8;
    v9 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _QWORD **))(*(_QWORD *)v5 + 152LL))(v5, &v14, &v18);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v12);
    }
    *a2 = v18;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v18);
  v12 = &qword_180086938;
  _InterlockedIncrement64(&qword_180086938);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
          v19[0],
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
    v5 = 0;
  }
  v6 = *a3;
  v18 = 0;
  LODWORD(v19[0]) = 752;
  v19[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                                 + 152LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
         &v14,
         &v18);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v19);
  }
  *a2 = v18;
  _InterlockedDecrement64(&qword_180086938);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x1800309e0  mov     [rsp-8+arg_0], rbx
0x1800309e5  mov     [rsp-8+arg_10], rsi
0x1800309ea  push    rbp
0x1800309eb  push    rdi
0x1800309ec  push    r14
0x1800309ee  lea     rbp, [rsp-47h]
0x1800309f3  sub     rsp, 90h
0x1800309fa  mov     rax, cs:__security_cookie
0x180030a01  xor     rax, rsp
0x180030a04  mov     [rbp+57h+var_18], rax
0x180030a08  mov     rsi, r8
0x180030a0b  mov     rdi, rdx
0x180030a0e  mov     [rbp+57h+var_30], rdx
0x180030a12  xor     r14d, r14d
0x180030a15  mov     [rbp+57h+var_48], 1
0x180030a1c  mov     [rbp+57h+var_44], 4Ah ; 'J'
0x180030a23  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180030a2a  mov     [rbp+57h+var_38], rax
0x180030a2e  lea     rax, [rbp+57h+var_48]
0x180030a32  mov     [rbp+57h+var_50], rax
0x180030a36  mov     [rbp+57h+var_28], r14
0x180030a3a  mov     dword ptr [rbp+57h+var_78], 1804h
0x180030a41  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030a48  mov     [rbp+57h+var_70], rax
0x180030a4c  lea     r9, [rbp+57h+var_28]
0x180030a50  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030a57  lea     rdx, [rbp+57h+var_50]
0x180030a5b  lea     rcx, [rbp+57h+var_80]
0x180030a5f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030a64  mov     ecx, dword ptr [rbp+57h+var_80]
0x180030a67  test    ecx, ecx
0x180030a69  js      loc_180030BD8
0x180030a6f  mov     rbx, [rbp+57h+var_28]
0x180030a73  mov     [rbp+57h+var_80], rbx
0x180030a77  test    rbx, rbx
0x180030a7a  jz      loc_180030B53
0x180030a80  mov     [rbp+57h+var_30], r14
0x180030a84  mov     rax, [rbx]
0x180030a87  lea     r8, [rbp+57h+var_30]
0x180030a8b  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030a92  mov     rcx, rbx
0x180030a95  mov     rax, [rax]
0x180030a98  call    cs:__guard_dispatch_icall_fptr
0x180030a9e  mov     rax, [rbp+57h+var_30]
0x180030aa2  mov     [rbp+57h+var_30], rax
0x180030aa6  test    rax, rax
0x180030aa9  jz      loc_180030B53
0x180030aaf  lea     rcx, [rbp+57h+var_30]
0x180030ab3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030ab8  lea     rax, qword_180086938
0x180030abf  mov     [rbp+57h+var_78], rax
0x180030ac3  lock inc cs:qword_180086938
0x180030acb  mov     rcx, [rbp+57h+var_28]
0x180030acf  xor     eax, eax
0x180030ad1  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030ada  jnz     short loc_180030AF6
0x180030adc  mov     [rbp+57h+var_80], r14
0x180030ae0  lea     rdx, stru_180086940; ListEntry
0x180030ae7  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180030aee  call    WINRT_IMPL_InterlockedPushEntrySList
0x180030af3  mov     ebx, r14d
0x180030af6  mov     rax, [rsi]
0x180030af9  mov     [rbp+57h+var_30], r14
0x180030afd  mov     dword ptr [rbp+57h+var_28], 2F0h
0x180030b04  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030b0b  mov     [rbp+57h+var_20], rcx
0x180030b0f  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030b16  movups  xmm0, xmmword ptr [rax]
0x180030b19  movaps  [rbp+57h+var_60], xmm0
0x180030b1d  mov     rax, [rcx]
0x180030b20  lea     r8, [rbp+57h+var_30]
0x180030b24  lea     rdx, [rbp+57h+var_60]
0x180030b28  mov     rax, [rax+98h]
0x180030b2f  call    cs:__guard_dispatch_icall_fptr
0x180030b35  test    eax, eax
0x180030b37  js      loc_180030BE5
0x180030b3d  mov     rcx, [rbp+57h+var_30]
0x180030b41  mov     [rdi], rcx
0x180030b44  lock dec cs:qword_180086938
0x180030b4c  test    rbx, rbx
0x180030b4f  jz      short loc_180030BA2
0x180030b51  jmp     short loc_180030B99
0x180030b53  mov     rax, [rsi]
0x180030b56  mov     [rbp+57h+var_30], r14
0x180030b5a  mov     dword ptr [rbp+57h+var_78], 2F0h
0x180030b61  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030b68  mov     [rbp+57h+var_70], rcx
0x180030b6c  movups  xmm0, xmmword ptr [rax]
0x180030b6f  movaps  [rbp+57h+var_60], xmm0
0x180030b73  mov     rax, [rbx]
0x180030b76  lea     r8, [rbp+57h+var_30]
0x180030b7a  lea     rdx, [rbp+57h+var_60]
0x180030b7e  mov     rcx, rbx
0x180030b81  mov     rax, [rax+98h]
0x180030b88  call    cs:__guard_dispatch_icall_fptr
0x180030b8e  test    eax, eax
0x180030b90  js      short loc_180030BC9
0x180030b92  mov     rax, [rbp+57h+var_30]
0x180030b96  mov     [rdi], rax
0x180030b99  lea     rcx, [rbp+57h+var_80]
0x180030b9d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030ba2  mov     rax, rdi
0x180030ba5  mov     rcx, [rbp+57h+var_18]
0x180030ba9  xor     rcx, rsp; StackCookie
0x180030bac  call    __security_check_cookie
0x180030bb1  lea     r11, [rsp+0A0h+var_10]
0x180030bb9  mov     rbx, [r11+20h]
0x180030bbd  mov     rsi, [r11+30h]
0x180030bc1  mov     rsp, r11
0x180030bc4  pop     r14
0x180030bc6  pop     rdi
0x180030bc7  pop     rbp
0x180030bc8  retn
0x180030bc9  lfence
0x180030bcc  lea     rdx, [rbp+57h+var_78]
0x180030bd0  mov     ecx, eax
0x180030bd2  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030bd8  lfence
0x180030bdb  lea     rdx, [rbp+57h+var_78]
0x180030bdf  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030be5  lfence
0x180030be8  lea     rdx, [rbp+57h+var_28]
0x180030bec  mov     ecx, eax
0x180030bee  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
