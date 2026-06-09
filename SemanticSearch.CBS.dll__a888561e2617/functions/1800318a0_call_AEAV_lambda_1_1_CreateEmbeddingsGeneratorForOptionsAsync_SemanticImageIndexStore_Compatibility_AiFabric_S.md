# ??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x1800318a0`
- end: `0x180031a9c`
- name: `??$call@AEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031aa0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800318a0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800319bf`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180031a11`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800318e1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateEmbeddingsGeneratorForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateEmbeddingsGeneratorForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
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
    LODWORD(v10) = 780;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 64LL))(v5, **a3, &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086918;
  _InterlockedIncrement64(&qword_180086918);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086920);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 780;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
                                                             + 64LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086918);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x1800318a0  mov     [rsp-18h+arg_0], rbx
0x1800318a5  mov     [rsp-18h+arg_18], rsi
0x1800318aa  push    rbp
0x1800318ab  push    rdi
0x1800318ac  push    r14
0x1800318ae  mov     rbp, rsp
0x1800318b1  sub     rsp, 80h
0x1800318b8  mov     rax, cs:__security_cookie
0x1800318bf  xor     rax, rsp
0x1800318c2  mov     [rbp+var_8], rax
0x1800318c6  mov     rsi, r8
0x1800318c9  mov     rdi, rdx
0x1800318cc  mov     [rbp+var_20], rdx
0x1800318d0  xor     r14d, r14d
0x1800318d3  mov     [rbp+var_38], 1
0x1800318da  mov     [rbp+var_34], 4Ah ; 'J'
0x1800318e1  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800318e8  mov     [rbp+var_28], rax
0x1800318ec  lea     rax, [rbp+var_38]
0x1800318f0  mov     [rbp+var_40], rax
0x1800318f4  mov     [rbp+var_18], r14
0x1800318f8  mov     dword ptr [rbp+var_58], 1804h
0x1800318ff  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031906  mov     [rbp+var_50], rax
0x18003190a  lea     r9, [rbp+var_18]
0x18003190e  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031915  lea     rdx, [rbp+var_40]
0x180031919  lea     rcx, [rbp+var_60]
0x18003191d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180031922  mov     ecx, dword ptr [rbp+var_60]
0x180031925  test    ecx, ecx
0x180031927  js      loc_180031A80
0x18003192d  mov     rbx, [rbp+var_18]
0x180031931  mov     [rbp+var_60], rbx
0x180031935  test    rbx, rbx
0x180031938  jz      loc_180031A06
0x18003193e  mov     [rbp+var_20], r14
0x180031942  mov     rax, [rbx]
0x180031945  lea     r8, [rbp+var_20]
0x180031949  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180031950  mov     rcx, rbx
0x180031953  mov     rax, [rax]
0x180031956  call    cs:__guard_dispatch_icall_fptr
0x18003195c  mov     rax, [rbp+var_20]
0x180031960  mov     [rbp+var_20], rax
0x180031964  test    rax, rax
0x180031967  jz      loc_180031A06
0x18003196d  lea     rcx, [rbp+var_20]
0x180031971  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031976  lea     rax, qword_180086918
0x18003197d  mov     [rbp+var_58], rax
0x180031981  lock inc cs:qword_180086918
0x180031989  mov     rcx, [rbp+var_18]
0x18003198d  xor     eax, eax
0x18003198f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031998  jnz     short loc_1800319B4
0x18003199a  mov     [rbp+var_60], r14
0x18003199e  lea     rdx, stru_180086920; ListEntry
0x1800319a5  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800319ac  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800319b1  mov     ebx, r14d
0x1800319b4  mov     [rbp+var_20], r14
0x1800319b8  mov     dword ptr [rbp+var_18], 30Ch
0x1800319bf  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800319c6  mov     [rbp+var_10], rax
0x1800319ca  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800319d1  mov     rdx, [rsi]
0x1800319d4  mov     rax, [rcx]
0x1800319d7  lea     r8, [rbp+var_20]
0x1800319db  mov     rdx, [rdx]
0x1800319de  mov     rax, [rax+40h]
0x1800319e2  call    cs:__guard_dispatch_icall_fptr
0x1800319e8  test    eax, eax
0x1800319ea  js      loc_180031A8D
0x1800319f0  mov     rcx, [rbp+var_20]
0x1800319f4  mov     [rdi], rcx
0x1800319f7  lock dec cs:qword_180086918
0x1800319ff  test    rbx, rbx
0x180031a02  jz      short loc_180031A4A
0x180031a04  jmp     short loc_180031A41
0x180031a06  mov     [rbp+var_20], r14
0x180031a0a  mov     dword ptr [rbp+var_58], 30Ch
0x180031a11  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031a18  mov     [rbp+var_50], rax
0x180031a1c  mov     rdx, [rsi]
0x180031a1f  mov     rax, [rbx]
0x180031a22  lea     r8, [rbp+var_20]
0x180031a26  mov     rdx, [rdx]
0x180031a29  mov     rcx, rbx
0x180031a2c  mov     rax, [rax+40h]
0x180031a30  call    cs:__guard_dispatch_icall_fptr
0x180031a36  test    eax, eax
0x180031a38  js      short loc_180031A71
0x180031a3a  mov     rax, [rbp+var_20]
0x180031a3e  mov     [rdi], rax
0x180031a41  lea     rcx, [rbp+var_60]
0x180031a45  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031a4a  mov     rax, rdi
0x180031a4d  mov     rcx, [rbp+var_8]
0x180031a51  xor     rcx, rsp; StackCookie
0x180031a54  call    __security_check_cookie
0x180031a59  lea     r11, [rsp+80h+var_s0]
0x180031a61  mov     rbx, [r11+20h]
0x180031a65  mov     rsi, [r11+38h]
0x180031a69  mov     rsp, r11
0x180031a6c  pop     r14
0x180031a6e  pop     rdi
0x180031a6f  pop     rbp
0x180031a70  retn
0x180031a71  lfence
0x180031a74  lea     rdx, [rbp+var_58]
0x180031a78  mov     ecx, eax
0x180031a7a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031a80  lfence
0x180031a83  lea     rdx, [rbp+var_58]
0x180031a87  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031a8d  lfence
0x180031a90  lea     rdx, [rbp+var_18]
0x180031a94  mov     ecx, eax
0x180031a96  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
