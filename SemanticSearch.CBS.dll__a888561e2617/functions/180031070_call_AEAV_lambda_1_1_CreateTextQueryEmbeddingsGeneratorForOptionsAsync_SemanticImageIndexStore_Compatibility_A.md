# ??$call@AEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180031070`
- end: `0x18003126c`
- name: `??$call@AEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateTextQueryEmbeddingsGeneratorForOptionsAsync@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180031270`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x180031070`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003118f`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800311e1`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800310b1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateTextQueryEmbeddingsGeneratorForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics2_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateTextQueryEmbeddingsGeneratorForOptionsAsync_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    LODWORD(v10) = 798;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 88LL))(v5, **a3, &v15);
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
  LODWORD(v16[0]) = 798;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
                                                             + 88LL))(
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
0x180031070  mov     [rsp-18h+arg_0], rbx
0x180031075  mov     [rsp-18h+arg_18], rsi
0x18003107a  push    rbp
0x18003107b  push    rdi
0x18003107c  push    r14
0x18003107e  mov     rbp, rsp
0x180031081  sub     rsp, 80h
0x180031088  mov     rax, cs:__security_cookie
0x18003108f  xor     rax, rsp
0x180031092  mov     [rbp+var_8], rax
0x180031096  mov     rsi, r8
0x180031099  mov     rdi, rdx
0x18003109c  mov     [rbp+var_20], rdx
0x1800310a0  xor     r14d, r14d
0x1800310a3  mov     [rbp+var_38], 1
0x1800310aa  mov     [rbp+var_34], 4Ah ; 'J'
0x1800310b1  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800310b8  mov     [rbp+var_28], rax
0x1800310bc  lea     rax, [rbp+var_38]
0x1800310c0  mov     [rbp+var_40], rax
0x1800310c4  mov     [rbp+var_18], r14
0x1800310c8  mov     dword ptr [rbp+var_58], 1804h
0x1800310cf  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800310d6  mov     [rbp+var_50], rax
0x1800310da  lea     r9, [rbp+var_18]
0x1800310de  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics2@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800310e5  lea     rdx, [rbp+var_40]
0x1800310e9  lea     rcx, [rbp+var_60]
0x1800310ed  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x1800310f2  mov     ecx, dword ptr [rbp+var_60]
0x1800310f5  test    ecx, ecx
0x1800310f7  js      loc_180031250
0x1800310fd  mov     rbx, [rbp+var_18]
0x180031101  mov     [rbp+var_60], rbx
0x180031105  test    rbx, rbx
0x180031108  jz      loc_1800311D6
0x18003110e  mov     [rbp+var_20], r14
0x180031112  mov     rax, [rbx]
0x180031115  lea     r8, [rbp+var_20]
0x180031119  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180031120  mov     rcx, rbx
0x180031123  mov     rax, [rax]
0x180031126  call    cs:__guard_dispatch_icall_fptr
0x18003112c  mov     rax, [rbp+var_20]
0x180031130  mov     [rbp+var_20], rax
0x180031134  test    rax, rax
0x180031137  jz      loc_1800311D6
0x18003113d  lea     rcx, [rbp+var_20]
0x180031141  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180031146  lea     rax, qword_180086918
0x18003114d  mov     [rbp+var_58], rax
0x180031151  lock inc cs:qword_180086918
0x180031159  mov     rcx, [rbp+var_18]
0x18003115d  xor     eax, eax
0x18003115f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x180031168  jnz     short loc_180031184
0x18003116a  mov     [rbp+var_60], r14
0x18003116e  lea     rdx, stru_180086920; ListEntry
0x180031175  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003117c  call    WINRT_IMPL_InterlockedPushEntrySList
0x180031181  mov     ebx, r14d
0x180031184  mov     [rbp+var_20], r14
0x180031188  mov     dword ptr [rbp+var_18], 31Eh
0x18003118f  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180031196  mov     [rbp+var_10], rax
0x18003119a  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics2@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics2>
0x1800311a1  mov     rdx, [rsi]
0x1800311a4  mov     rax, [rcx]
0x1800311a7  lea     r8, [rbp+var_20]
0x1800311ab  mov     rdx, [rdx]
0x1800311ae  mov     rax, [rax+58h]
0x1800311b2  call    cs:__guard_dispatch_icall_fptr
0x1800311b8  test    eax, eax
0x1800311ba  js      loc_18003125D
0x1800311c0  mov     rcx, [rbp+var_20]
0x1800311c4  mov     [rdi], rcx
0x1800311c7  lock dec cs:qword_180086918
0x1800311cf  test    rbx, rbx
0x1800311d2  jz      short loc_18003121A
0x1800311d4  jmp     short loc_180031211
0x1800311d6  mov     [rbp+var_20], r14
0x1800311da  mov     dword ptr [rbp+var_58], 31Eh
0x1800311e1  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800311e8  mov     [rbp+var_50], rax
0x1800311ec  mov     rdx, [rsi]
0x1800311ef  mov     rax, [rbx]
0x1800311f2  lea     r8, [rbp+var_20]
0x1800311f6  mov     rdx, [rdx]
0x1800311f9  mov     rcx, rbx
0x1800311fc  mov     rax, [rax+58h]
0x180031200  call    cs:__guard_dispatch_icall_fptr
0x180031206  test    eax, eax
0x180031208  js      short loc_180031241
0x18003120a  mov     rax, [rbp+var_20]
0x18003120e  mov     [rdi], rax
0x180031211  lea     rcx, [rbp+var_60]
0x180031215  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003121a  mov     rax, rdi
0x18003121d  mov     rcx, [rbp+var_8]
0x180031221  xor     rcx, rsp; StackCookie
0x180031224  call    __security_check_cookie
0x180031229  lea     r11, [rsp+80h+var_s0]
0x180031231  mov     rbx, [r11+20h]
0x180031235  mov     rsi, [r11+38h]
0x180031239  mov     rsp, r11
0x18003123c  pop     r14
0x18003123e  pop     rdi
0x18003123f  pop     rbp
0x180031240  retn
0x180031241  lfence
0x180031244  lea     rdx, [rbp+var_58]
0x180031248  mov     ecx, eax
0x18003124a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180031250  lfence
0x180031253  lea     rdx, [rbp+var_58]
0x180031257  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003125d  lfence
0x180031260  lea     rdx, [rbp+var_18]
0x180031264  mov     ecx, eax
0x180031266  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
