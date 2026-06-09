# ??$call@AEAV_lambda_1_@?1??IsAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x180032620`
- end: `0x1800327d0`
- name: `??$call@AEAV_lambda_1_@?1??IsAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??IsAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticImageIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `432`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x18001f7d0`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800325a0`
- `0x180032620`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x180032750`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003265b`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
__int64 __fastcall ___call_AEAV_lambda_1___1__IsAvailable_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticImageIndexStoreOptions_456789__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__IsAvailable_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticImageIndexStoreOptions_6789Microsoft_2__Z__Z(
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
  v9[1] = 74;
  v10 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v8 = v9;
  v12[0] = 0;
  LODWORD(v7[0]) = 6148;
  v7[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v11,
    &v8,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
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
    v11 = &qword_180086938;
    _InterlockedIncrement64(&qword_180086938);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
            v12[0],
            0) )
    {
      v7[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
      v3 = 0;
    }
    v4 = `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsAvailable'::`2'::_lambda_1_::operator()(
           a2,
           &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>);
    _InterlockedDecrement64(&qword_180086938);
  }
  else
  {
    v13[0] = 0;
    LODWORD(v12[0]) = 674;
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
0x180032620  mov     [rsp-8+arg_0], rbx
0x180032625  mov     [rsp-8+arg_10], rsi
0x18003262a  mov     [rsp-8+arg_18], rdi
0x18003262f  push    rbp
0x180032630  mov     rbp, rsp
0x180032633  sub     rsp, 80h
0x18003263a  mov     rax, cs:__security_cookie
0x180032641  xor     rax, rsp
0x180032644  mov     [rbp+var_10], rax
0x180032648  mov     rdi, rdx
0x18003264b  xor     esi, esi
0x18003264d  mov     [rbp+var_48], 1
0x180032654  mov     [rbp+var_44], 4Ah ; 'J'
0x18003265b  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x180032662  mov     [rbp+var_38], rax
0x180032666  lea     rax, [rbp+var_48]
0x18003266a  mov     [rbp+var_50], rax
0x18003266e  mov     [rbp+var_28], rsi
0x180032672  mov     dword ptr [rbp+var_60], 1804h
0x180032679  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032680  mov     [rbp+var_58], rax
0x180032684  lea     r9, [rbp+var_28]
0x180032688  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x18003268f  lea     rdx, [rbp+var_50]
0x180032693  lea     rcx, [rbp+var_30]
0x180032697  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003269c  mov     ecx, dword ptr [rbp+var_30]
0x18003269f  test    ecx, ecx
0x1800326a1  js      loc_1800327C3
0x1800326a7  mov     rbx, [rbp+var_28]
0x1800326ab  mov     [rbp+var_60], rbx
0x1800326af  test    rbx, rbx
0x1800326b2  jz      loc_180032745
0x1800326b8  mov     [rbp+var_30], rsi
0x1800326bc  mov     rax, [rbx]
0x1800326bf  lea     r8, [rbp+var_30]
0x1800326c3  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x1800326ca  mov     rcx, rbx
0x1800326cd  mov     rax, [rax]
0x1800326d0  call    cs:__guard_dispatch_icall_fptr
0x1800326d6  mov     rax, [rbp+var_30]
0x1800326da  mov     [rbp+var_30], rax
0x1800326de  test    rax, rax
0x1800326e1  jz      short loc_180032745
0x1800326e3  lea     rcx, [rbp+var_30]
0x1800326e7  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x1800326ec  lea     rax, qword_180086938
0x1800326f3  mov     [rbp+var_30], rax
0x1800326f7  lock inc cs:qword_180086938
0x1800326ff  mov     rdx, [rbp+var_28]
0x180032703  xor     eax, eax
0x180032705  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rdx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x18003270e  jnz     short loc_180032729
0x180032710  mov     [rbp+var_60], rsi
0x180032714  lea     rdx, stru_180086940; ListEntry
0x18003271b  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180032722  call    WINRT_IMPL_InterlockedPushEntrySList
0x180032727  mov     ebx, esi
0x180032729  lea     rdx, ??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180032730  mov     rcx, rdi
0x180032733  call    ??R_lambda_1_@?1??IsAvailable@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticImageIndexStoreOptions@345678@@Z@QEBA@AEBUISemanticImageIndexStoreStatics@345678@@Z; `winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore::IsAvailable(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStoreOptions const &)'::`2'::_lambda_1_::operator()(winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics const &)
0x180032738  movzx   edi, al
0x18003273b  lock dec cs:qword_180086938
0x180032743  jmp     short loc_18003277D
0x180032745  mov     [rbp+var_18], 0
0x180032749  mov     dword ptr [rbp+var_28], 2A2h
0x180032750  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180032757  mov     [rbp+var_20], rax
0x18003275b  mov     rdx, [rdi]
0x18003275e  mov     rax, [rbx]
0x180032761  lea     r8, [rbp+var_18]
0x180032765  mov     rdx, [rdx]
0x180032768  mov     rcx, rbx
0x18003276b  mov     rax, [rax+30h]
0x18003276f  call    cs:__guard_dispatch_icall_fptr
0x180032775  test    eax, eax
0x180032777  js      short loc_1800327B4
0x180032779  movzx   edi, [rbp+var_18]
0x18003277d  test    rbx, rbx
0x180032780  jz      short loc_18003278B
0x180032782  lea     rcx, [rbp+var_60]
0x180032786  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003278b  movzx   eax, dil
0x18003278f  mov     rcx, [rbp+var_10]
0x180032793  xor     rcx, rsp; StackCookie
0x180032796  call    __security_check_cookie
0x18003279b  lea     r11, [rsp+80h+var_s0]
0x1800327a3  mov     rbx, [r11+10h]
0x1800327a7  mov     rsi, [r11+20h]
0x1800327ab  mov     rdi, [r11+28h]
0x1800327af  mov     rsp, r11
0x1800327b2  pop     rbp
0x1800327b3  retn
0x1800327b4  lfence
0x1800327b7  lea     rdx, [rbp+var_28]
0x1800327bb  mov     ecx, eax
0x1800327bd  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1800327c3  lfence
0x1800327c6  lea     rdx, [rbp+var_60]
0x1800327ca  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
