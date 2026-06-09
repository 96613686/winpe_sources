# ??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z

- ea: `0x1800301b0`
- end: `0x18003037e`
- name: `??$call@AEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUhstring@param@9@@Z@@?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??DeleteIndex@SemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUhstring@param@2@@Z@@Z`
- size: `462`
- prototype: `__int64 __fastcall(__int64, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180021320`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x1800301b0`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x1800302c2`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x180030329`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x1800301e1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
__int64 __fastcall ___call_AEAV_lambda_1___1__DeleteIndex_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUhstring_param_9__Z____factory_cache_entry_USemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticImageIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__DeleteIndex_SemanticImageIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUhstring_param_2__Z__Z(
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
  v7[1] = 74;
  v8 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticImageIndexStore";
  v6 = v7;
  v10 = 0;
  LODWORD(v5[0]) = 6148;
  v5[1] = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v6,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
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
    v9 = &qword_180086938;
    _InterlockedIncrement64(&qword_180086938);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
            (signed __int64)v10,
            0) )
    {
      v3 = 0;
      v5[0] = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086940);
    }
    LODWORD(v10) = 763;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
                                                        + 168LL))(
               winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>,
               **a2);
    if ( (int)result < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)result, &v10);
    }
    _InterlockedDecrement64(&qword_180086938);
  }
  else
  {
    LODWORD(v10) = 763;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    result = ((__int64 (__fastcall *)(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD))(*v3)[21])(v3, **a2);
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
0x1800301b0  mov     [rsp-8+arg_0], rbx
0x1800301b5  mov     [rsp-8+arg_10], rdi
0x1800301ba  push    rbp
0x1800301bb  mov     rbp, rsp
0x1800301be  sub     rsp, 70h
0x1800301c2  mov     rax, cs:__security_cookie
0x1800301c9  xor     rax, rsp
0x1800301cc  mov     [rbp+var_8], rax
0x1800301d0  mov     rdi, rdx
0x1800301d3  mov     [rbp+var_38], 1
0x1800301da  mov     [rbp+var_34], 4Ah ; 'J'
0x1800301e1  lea     rax, aMicrosoftAsgSe_12; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x1800301e8  mov     [rbp+var_28], rax
0x1800301ec  lea     rax, [rbp+var_38]
0x1800301f0  mov     [rbp+var_40], rax
0x1800301f4  mov     [rbp+var_18], 0
0x1800301fc  mov     dword ptr [rbp+var_50], 1804h
0x180030203  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003020a  mov     [rbp+var_48], rax
0x18003020e  lea     r9, [rbp+var_18]
0x180030212  lea     r8, ??$guid_v@UISemanticImageIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x180030219  lea     rdx, [rbp+var_40]
0x18003021d  lea     rcx, [rbp+var_20]
0x180030221  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180030226  mov     ecx, dword ptr [rbp+var_20]
0x180030229  test    ecx, ecx
0x18003022b  js      loc_180030371
0x180030231  mov     rbx, [rbp+var_18]
0x180030235  mov     [rbp+var_50], rbx
0x180030239  test    rbx, rbx
0x18003023c  jz      loc_180030322
0x180030242  mov     [rbp+var_20], 0
0x18003024a  mov     rax, [rbx]
0x18003024d  lea     r8, [rbp+var_20]
0x180030251  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180030258  mov     rcx, rbx
0x18003025b  mov     rax, [rax]
0x18003025e  call    cs:__guard_dispatch_icall_fptr
0x180030264  mov     rax, [rbp+var_20]
0x180030268  mov     [rbp+var_20], rax
0x18003026c  test    rax, rax
0x18003026f  jz      loc_180030322
0x180030275  lea     rcx, [rbp+var_20]
0x180030279  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003027e  lea     rax, qword_180086938
0x180030285  mov     [rbp+var_20], rax
0x180030289  lock inc cs:qword_180086938
0x180030291  mov     rcx, [rbp+var_18]
0x180030295  xor     eax, eax
0x180030297  lock cmpxchg cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800302a0  jnz     short loc_1800302BB
0x1800302a2  xor     ebx, ebx
0x1800302a4  mov     [rbp+var_50], rbx
0x1800302a8  lea     rdx, stru_180086940; ListEntry
0x1800302af  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x1800302b6  call    WINRT_IMPL_InterlockedPushEntrySList
0x1800302bb  mov     dword ptr [rbp+var_18], 2FBh
0x1800302c2  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x1800302c9  mov     [rbp+var_10], rax
0x1800302cd  mov     rcx, cs:??$factory_cache_entry_v@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticImageIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticImageIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticImageIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticImageIndexStoreStatics>
0x1800302d4  mov     rdx, [rdi]
0x1800302d7  mov     rax, [rcx]
0x1800302da  mov     rdx, [rdx]
0x1800302dd  mov     rax, [rax+0A8h]
0x1800302e4  call    cs:__guard_dispatch_icall_fptr
0x1800302ea  test    eax, eax
0x1800302ec  js      short loc_180030353
0x1800302ee  lock dec cs:qword_180086938
0x1800302f6  test    rbx, rbx
0x1800302f9  jz      short loc_180030304
0x1800302fb  lea     rcx, [rbp+var_50]
0x1800302ff  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180030304  mov     rcx, [rbp+var_8]
0x180030308  xor     rcx, rsp; StackCookie
0x18003030b  call    __security_check_cookie
0x180030310  lea     r11, [rsp+70h+var_s0]
0x180030315  mov     rbx, [r11+10h]
0x180030319  mov     rdi, [r11+20h]
0x18003031d  mov     rsp, r11
0x180030320  pop     rbp
0x180030321  retn
0x180030322  mov     dword ptr [rbp+var_18], 2FBh
0x180030329  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x180030330  mov     [rbp+var_10], rax
0x180030334  mov     rdx, [rdi]
0x180030337  mov     rax, [rbx]
0x18003033a  mov     rdx, [rdx]
0x18003033d  mov     rcx, rbx
0x180030340  mov     rax, [rax+0A8h]
0x180030347  call    cs:__guard_dispatch_icall_fptr
0x18003034d  test    eax, eax
0x18003034f  js      short loc_180030362
0x180030351  jmp     short loc_1800302F6
0x180030353  lfence
0x180030356  lea     rdx, [rbp+var_18]
0x18003035a  mov     ecx, eax
0x18003035c  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030362  lfence
0x180030365  lea     rdx, [rbp+var_18]
0x180030369  mov     ecx, eax
0x18003036b  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180030371  lfence
0x180030374  lea     rdx, [rbp+var_50]
0x180030378  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
