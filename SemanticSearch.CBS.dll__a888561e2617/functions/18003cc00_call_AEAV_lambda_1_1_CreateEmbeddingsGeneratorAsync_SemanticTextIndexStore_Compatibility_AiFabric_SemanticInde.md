# ??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x18003cc00`
- end: `0x18003ce0e`
- name: `??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUguid@9@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUguid@2@@Z@@Z`
- size: `526`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18005a820`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003cc00`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003cd24`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003cd7e`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003cc43`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateEmbeddingsGeneratorAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUguid_9__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateEmbeddingsGeneratorAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUguid_2__Z__Z(
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
  v16[1] = 73;
  v17 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v15 = v16;
  v19[0] = 0;
  LODWORD(v12) = 6148;
  v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v15,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
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
    LODWORD(v12) = 1204;
    v13 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v14 = *v8;
    v9 = (*(__int64 (__fastcall **)(signed __int64, __int128 *, _QWORD **))(*(_QWORD *)v5 + 112LL))(v5, &v14, &v18);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v12);
    }
    *a2 = v18;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v18);
  v12 = &qword_180086A78;
  _InterlockedIncrement64(&qword_180086A78);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
          v19[0],
          0) )
  {
    v11 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A80);
    v5 = 0;
  }
  v6 = *a3;
  v18 = 0;
  LODWORD(v19[0]) = 1204;
  v19[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v14 = *v6;
  v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
                                                                 + 112LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
         &v14,
         &v18);
  if ( v7 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v7, v19);
  }
  *a2 = v18;
  _InterlockedDecrement64(&qword_180086A78);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
  return a2;
}

```

## disassembly

```asm
0x18003cc00  mov     [rsp-8+arg_0], rbx
0x18003cc05  mov     [rsp-8+arg_10], rsi
0x18003cc0a  push    rbp
0x18003cc0b  push    rdi
0x18003cc0c  push    r14
0x18003cc0e  lea     rbp, [rsp-47h]
0x18003cc13  sub     rsp, 90h
0x18003cc1a  mov     rax, cs:__security_cookie
0x18003cc21  xor     rax, rsp
0x18003cc24  mov     [rbp+57h+var_18], rax
0x18003cc28  mov     rsi, r8
0x18003cc2b  mov     rdi, rdx
0x18003cc2e  mov     [rbp+57h+var_30], rdx
0x18003cc32  xor     r14d, r14d
0x18003cc35  mov     [rbp+57h+var_48], 1
0x18003cc3c  mov     [rbp+57h+var_44], 49h ; 'I'
0x18003cc43  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003cc4a  mov     [rbp+57h+var_38], rax
0x18003cc4e  lea     rax, [rbp+57h+var_48]
0x18003cc52  mov     [rbp+57h+var_50], rax
0x18003cc56  mov     [rbp+57h+var_28], r14
0x18003cc5a  mov     dword ptr [rbp+57h+var_78], 1804h
0x18003cc61  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003cc68  mov     [rbp+57h+var_70], rax
0x18003cc6c  lea     r9, [rbp+57h+var_28]
0x18003cc70  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003cc77  lea     rdx, [rbp+57h+var_50]
0x18003cc7b  lea     rcx, [rbp+57h+var_80]
0x18003cc7f  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003cc84  mov     ecx, dword ptr [rbp+57h+var_80]
0x18003cc87  test    ecx, ecx
0x18003cc89  js      loc_18003CDF2
0x18003cc8f  mov     rbx, [rbp+57h+var_28]
0x18003cc93  mov     [rbp+57h+var_80], rbx
0x18003cc97  test    rbx, rbx
0x18003cc9a  jz      loc_18003CD70
0x18003cca0  mov     [rbp+57h+var_30], r14
0x18003cca4  mov     rax, [rbx]
0x18003cca7  lea     r8, [rbp+57h+var_30]
0x18003ccab  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003ccb2  mov     rcx, rbx
0x18003ccb5  mov     rax, [rax]
0x18003ccb8  call    cs:__guard_dispatch_icall_fptr
0x18003ccbe  mov     rax, [rbp+57h+var_30]
0x18003ccc2  mov     [rbp+57h+var_30], rax
0x18003ccc6  test    rax, rax
0x18003ccc9  jz      loc_18003CD70
0x18003cccf  lea     rcx, [rbp+57h+var_30]
0x18003ccd3  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003ccd8  lea     rax, qword_180086A78
0x18003ccdf  mov     [rbp+57h+var_78], rax
0x18003cce3  lock inc cs:qword_180086A78
0x18003cceb  mov     rcx, [rbp+57h+var_28]
0x18003ccef  xor     eax, eax
0x18003ccf1  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003ccfa  jnz     short loc_18003CD16
0x18003ccfc  mov     [rbp+57h+var_80], r14
0x18003cd00  lea     rdx, stru_180086A80; ListEntry
0x18003cd07  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003cd0e  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003cd13  mov     ebx, r14d
0x18003cd16  mov     rax, [rsi]
0x18003cd19  mov     [rbp+57h+var_30], r14
0x18003cd1d  mov     dword ptr [rbp+57h+var_28], 4B4h
0x18003cd24  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003cd2b  mov     [rbp+57h+var_20], rcx
0x18003cd2f  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003cd36  movups  xmm0, xmmword ptr [rax]
0x18003cd39  movaps  [rbp+57h+var_60], xmm0
0x18003cd3d  mov     rax, [rcx]
0x18003cd40  lea     r8, [rbp+57h+var_30]
0x18003cd44  lea     rdx, [rbp+57h+var_60]
0x18003cd48  mov     rax, [rax+70h]
0x18003cd4c  call    cs:__guard_dispatch_icall_fptr
0x18003cd52  test    eax, eax
0x18003cd54  js      loc_18003CDFF
0x18003cd5a  mov     rcx, [rbp+57h+var_30]
0x18003cd5e  mov     [rdi], rcx
0x18003cd61  lock dec cs:qword_180086A78
0x18003cd69  test    rbx, rbx
0x18003cd6c  jz      short loc_18003CDBC
0x18003cd6e  jmp     short loc_18003CDB3
0x18003cd70  mov     rax, [rsi]
0x18003cd73  mov     [rbp+57h+var_30], r14
0x18003cd77  mov     dword ptr [rbp+57h+var_78], 4B4h
0x18003cd7e  lea     rcx, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003cd85  mov     [rbp+57h+var_70], rcx
0x18003cd89  movups  xmm0, xmmword ptr [rax]
0x18003cd8c  movaps  [rbp+57h+var_60], xmm0
0x18003cd90  mov     rax, [rbx]
0x18003cd93  lea     r8, [rbp+57h+var_30]
0x18003cd97  lea     rdx, [rbp+57h+var_60]
0x18003cd9b  mov     rcx, rbx
0x18003cd9e  mov     rax, [rax+70h]
0x18003cda2  call    cs:__guard_dispatch_icall_fptr
0x18003cda8  test    eax, eax
0x18003cdaa  js      short loc_18003CDE3
0x18003cdac  mov     rax, [rbp+57h+var_30]
0x18003cdb0  mov     [rdi], rax
0x18003cdb3  lea     rcx, [rbp+57h+var_80]
0x18003cdb7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003cdbc  mov     rax, rdi
0x18003cdbf  mov     rcx, [rbp+57h+var_18]
0x18003cdc3  xor     rcx, rsp; StackCookie
0x18003cdc6  call    __security_check_cookie
0x18003cdcb  lea     r11, [rsp+0A0h+var_10]
0x18003cdd3  mov     rbx, [r11+20h]
0x18003cdd7  mov     rsi, [r11+30h]
0x18003cddb  mov     rsp, r11
0x18003cdde  pop     r14
0x18003cde0  pop     rdi
0x18003cde1  pop     rbp
0x18003cde2  retn
0x18003cde3  lfence
0x18003cde6  lea     rdx, [rbp+57h+var_78]
0x18003cdea  mov     ecx, eax
0x18003cdec  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003cdf2  lfence
0x18003cdf5  lea     rdx, [rbp+57h+var_78]
0x18003cdf9  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003cdff  lfence
0x18003ce02  lea     rdx, [rbp+57h+var_28]
0x18003ce06  mov     ecx, eax
0x18003ce08  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
