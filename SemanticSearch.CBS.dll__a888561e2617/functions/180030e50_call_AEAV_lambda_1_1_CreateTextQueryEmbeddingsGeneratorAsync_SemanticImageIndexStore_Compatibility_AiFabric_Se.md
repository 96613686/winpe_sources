# ??$call@AEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x180030e50`
- end: `0x180031064`
- name: `??$call@AEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `532`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180056d90`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180030e50`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180030f74`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030fd1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030e93`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateTextQueryEmbeddingsGeneratorAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateTextQueryEmbeddingsGeneratorAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
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
    LODWORD(v12) = 758;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v14 = *v8;
    v9 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _QWORD **))(*(_QWORD *)v5 + 160LL))(v5, &v14, &v18);
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
  LODWORD(v19[0]) = 758;
  v19[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                                 + 160LL))(
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
0x180030e50  mov     [rsp-8+arg_0], rbx
0x180030e55  mov     [rsp-8+arg_10], rsi
0x180030e5a  push    rbp
0x180030e5b  push    rdi
0x180030e5c  push    r14
0x180030e5e  lea     rbp, [rsp-47h]
0x180030e63  sub     rsp, 90h
0x180030e6a  mov     rax, cs:__security_cookie
0x180030e71  xor     rax, rsp
0x180030e74  mov     [rbp+57h+var_18], rax
0x180030e78  mov     rsi, r8
0x180030e7b  mov     rdi, rdx
0x180030e7e  mov     [rbp+57h+var_30], rdx
0x180030e82  xor     r14d, r14d
0x180030e85  mov     [rbp+57h+var_48], 1
0x180030e8c  mov     [rbp+57h+var_44], 4Ah ; 'J'
0x180030e93  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180030e9a  mov     [rbp+57h+var_38], rax
0x180030e9e  lea     rax, [rbp+57h+var_48]
0x180030ea2  mov     [rbp+57h+var_50], rax
0x180030ea6  mov     [rbp+57h+var_28], r14
0x180030eaa  mov     dword ptr [rbp+57h+var_78], 1804h
0x180030eb1  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030eb8  mov     [rbp+57h+var_70], rax
0x180030ebc  lea     r9, [rbp+57h+var_28]
0x180030ec0  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030ec7  lea     rdx, [rbp+57h+var_50]
0x180030ecb  lea     rcx, [rbp+57h+var_80]
0x180030ecf  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030ed4  mov     ecx, dword ptr [rbp+57h+var_80]
0x180030ed7  test    ecx, ecx
0x180030ed9  js      loc_180031048
0x180030edf  mov     rbx, [rbp+57h+var_28]
0x180030ee3  mov     [rbp+57h+var_80], rbx
0x180030ee7  test    rbx, rbx
0x180030eea  jz      loc_180030FC3
0x180030ef0  mov     [rbp+57h+var_30], r14
0x180030ef4  mov     rax, [rbx]
0x180030ef7  lea     r8, [rbp+57h+var_30]
0x180030efb  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030f02  mov     rcx, rbx
0x180030f05  mov     rax, [rax]
0x180030f08  call    cs:__guard_dispatch_icall_fptr
0x180030f0e  mov     rax, [rbp+57h+var_30]
0x180030f12  mov     [rbp+57h+var_30], rax
0x180030f16  test    rax, rax
0x180030f19  jz      loc_180030FC3
0x180030f1f  lea     rcx, [rbp+57h+var_30]
0x180030f23  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030f28  lea     rax, qword_180086938
0x180030f2f  mov     [rbp+57h+var_78], rax
0x180030f33  lock inc cs:qword_180086938
0x180030f3b  mov     rcx, [rbp+57h+var_28]
0x180030f3f  xor     eax, eax
0x180030f41  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030f4a  jnz     short loc_180030F66
0x180030f4c  mov     [rbp+57h+var_80], r14
0x180030f50  lea     rdx, stru_180086940; ListEntry
0x180030f57  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180030f5e  call    WINRT_IMPL_InterlockedPushEntrySList
0x180030f63  mov     ebx, r14d
0x180030f66  mov     rax, [rsi]
0x180030f69  mov     [rbp+57h+var_30], r14
0x180030f6d  mov     dword ptr [rbp+57h+var_28], 2F6h
0x180030f74  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030f7b  mov     [rbp+57h+var_20], rcx
0x180030f7f  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030f86  movups  xmm0, xmmword ptr [rax]
0x180030f89  movaps  [rbp+57h+var_60], xmm0
0x180030f8d  mov     rax, [rcx]
0x180030f90  lea     r8, [rbp+57h+var_30]
0x180030f94  lea     rdx, [rbp+57h+var_60]
0x180030f98  mov     rax, [rax+0A0h]
0x180030f9f  call    cs:__guard_dispatch_icall_fptr
0x180030fa5  test    eax, eax
0x180030fa7  js      loc_180031055
0x180030fad  mov     rcx, [rbp+57h+var_30]
0x180030fb1  mov     [rdi], rcx
0x180030fb4  lock dec cs:qword_180086938
0x180030fbc  test    rbx, rbx
0x180030fbf  jz      short loc_180031012
0x180030fc1  jmp     short loc_180031009
0x180030fc3  mov     rax, [rsi]
0x180030fc6  mov     [rbp+57h+var_30], r14
0x180030fca  mov     dword ptr [rbp+57h+var_78], 2F6h
0x180030fd1  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030fd8  mov     [rbp+57h+var_70], rcx
0x180030fdc  movups  xmm0, xmmword ptr [rax]
0x180030fdf  movaps  [rbp+57h+var_60], xmm0
0x180030fe3  mov     rax, [rbx]
0x180030fe6  lea     r8, [rbp+57h+var_30]
0x180030fea  lea     rdx, [rbp+57h+var_60]
0x180030fee  mov     rcx, rbx
0x180030ff1  mov     rax, [rax+0A0h]
0x180030ff8  call    cs:__guard_dispatch_icall_fptr
0x180030ffe  test    eax, eax
0x180031000  js      short loc_180031039
0x180031002  mov     rax, [rbp+57h+var_30]
0x180031006  mov     [rdi], rax
0x180031009  lea     rcx, [rbp+57h+var_80]
0x18003100d  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031012  mov     rax, rdi
0x180031015  mov     rcx, [rbp+57h+var_18]
0x180031019  xor     rcx, rsp; StackCookie
0x18003101c  call    __security_check_cookie
0x180031021  lea     r11, [rsp+0A0h+var_10]
0x180031029  mov     rbx, [r11+20h]
0x18003102d  mov     rsi, [r11+30h]
0x180031031  mov     rsp, r11
0x180031034  pop     r14
0x180031036  pop     rdi
0x180031037  pop     rbp
0x180031038  retn
0x180031039  lfence
0x18003103c  lea     rdx, [rbp+57h+var_78]
0x180031040  mov     ecx, eax
0x180031042  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031048  lfence
0x18003104b  lea     rdx, [rbp+57h+var_78]
0x18003104f  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031055  lfence
0x180031058  lea     rdx, [rbp+57h+var_28]
0x18003105c  mov     ecx, eax
0x18003105e  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
