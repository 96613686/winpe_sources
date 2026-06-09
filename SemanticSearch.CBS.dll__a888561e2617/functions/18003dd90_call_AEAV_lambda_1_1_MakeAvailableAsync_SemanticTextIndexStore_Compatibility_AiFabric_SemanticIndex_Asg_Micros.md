# ??$call@AEAV_lambda_1_@?1??MakeAvailableAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeAvailableAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003dd90`
- end: `0x18003df8c`
- name: `??$call@AEAV_lambda_1_@?1??MakeAvailableAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??MakeAvailableAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180038100`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003dd90`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003deaf`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003df01`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003ddd1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__MakeAvailableAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__MakeAvailableAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
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
  v13[1] = 73;
  v14 = L"Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore";
  v12 = v13;
  v16[0] = 0;
  LODWORD(v10) = 6148;
  v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\base.h";
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v9,
    &v12,
    (__int64)winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
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
    LODWORD(v10) = 1162;
    v11 = "C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generated Files\\winrt\\"
          "Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
    v7 = (*(__int64 (__fastcall **)(signed __int64, _QWORD, _QWORD **))(*(_QWORD *)v5 + 56LL))(v5, **a3, &v15);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v10);
    }
    *a2 = v15;
    goto LABEL_11;
  }
  winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v15);
  v10 = &qword_180086A78;
  _InterlockedIncrement64(&qword_180086A78);
  if ( !_InterlockedCompareExchange64(
          &winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
          v16[0],
          0) )
  {
    v9 = 0;
    WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &stru_180086A80);
    v5 = 0;
  }
  v15 = 0;
  LODWORD(v16[0]) = 1162;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
                                                             + 56LL))(
         winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>,
         **a3,
         &v15);
  if ( v6 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v6, v16);
  }
  *a2 = v15;
  _InterlockedDecrement64(&qword_180086A78);
  if ( v5 )
LABEL_11:
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v9);
  return a2;
}

```

## disassembly

```asm
0x18003dd90  mov     [rsp-18h+arg_0], rbx
0x18003dd95  mov     [rsp-18h+arg_18], rsi
0x18003dd9a  push    rbp
0x18003dd9b  push    rdi
0x18003dd9c  push    r14
0x18003dd9e  mov     rbp, rsp
0x18003dda1  sub     rsp, 80h
0x18003dda8  mov     rax, cs:__security_cookie
0x18003ddaf  xor     rax, rsp
0x18003ddb2  mov     [rbp+var_8], rax
0x18003ddb6  mov     rsi, r8
0x18003ddb9  mov     rdi, rdx
0x18003ddbc  mov     [rbp+var_20], rdx
0x18003ddc0  xor     r14d, r14d
0x18003ddc3  mov     [rbp+var_38], 1
0x18003ddca  mov     [rbp+var_34], 49h ; 'I'
0x18003ddd1  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003ddd8  mov     [rbp+var_28], rax
0x18003dddc  lea     rax, [rbp+var_38]
0x18003dde0  mov     [rbp+var_40], rax
0x18003dde4  mov     [rbp+var_18], r14
0x18003dde8  mov     dword ptr [rbp+var_58], 1804h
0x18003ddef  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003ddf6  mov     [rbp+var_50], rax
0x18003ddfa  lea     r9, [rbp+var_18]
0x18003ddfe  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003de05  lea     rdx, [rbp+var_40]
0x18003de09  lea     rcx, [rbp+var_60]
0x18003de0d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003de12  mov     ecx, dword ptr [rbp+var_60]
0x18003de15  test    ecx, ecx
0x18003de17  js      loc_18003DF70
0x18003de1d  mov     rbx, [rbp+var_18]
0x18003de21  mov     [rbp+var_60], rbx
0x18003de25  test    rbx, rbx
0x18003de28  jz      loc_18003DEF6
0x18003de2e  mov     [rbp+var_20], r14
0x18003de32  mov     rax, [rbx]
0x18003de35  lea     r8, [rbp+var_20]
0x18003de39  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003de40  mov     rcx, rbx
0x18003de43  mov     rax, [rax]
0x18003de46  call    cs:__guard_dispatch_icall_fptr
0x18003de4c  mov     rax, [rbp+var_20]
0x18003de50  mov     [rbp+var_20], rax
0x18003de54  test    rax, rax
0x18003de57  jz      loc_18003DEF6
0x18003de5d  lea     rcx, [rbp+var_20]
0x18003de61  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003de66  lea     rax, qword_180086A78
0x18003de6d  mov     [rbp+var_58], rax
0x18003de71  lock inc cs:qword_180086A78
0x18003de79  mov     rcx, [rbp+var_18]
0x18003de7d  xor     eax, eax
0x18003de7f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003de88  jnz     short loc_18003DEA4
0x18003de8a  mov     [rbp+var_60], r14
0x18003de8e  lea     rdx, stru_180086A80; ListEntry
0x18003de95  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003de9c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003dea1  mov     ebx, r14d
0x18003dea4  mov     [rbp+var_20], r14
0x18003dea8  mov     dword ptr [rbp+var_18], 48Ah
0x18003deaf  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003deb6  mov     [rbp+var_10], rax
0x18003deba  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003dec1  mov     rdx, [rsi]
0x18003dec4  mov     rax, [rcx]
0x18003dec7  lea     r8, [rbp+var_20]
0x18003decb  mov     rdx, [rdx]
0x18003dece  mov     rax, [rax+38h]
0x18003ded2  call    cs:__guard_dispatch_icall_fptr
0x18003ded8  test    eax, eax
0x18003deda  js      loc_18003DF7D
0x18003dee0  mov     rcx, [rbp+var_20]
0x18003dee4  mov     [rdi], rcx
0x18003dee7  lock dec cs:qword_180086A78
0x18003deef  test    rbx, rbx
0x18003def2  jz      short loc_18003DF3A
0x18003def4  jmp     short loc_18003DF31
0x18003def6  mov     [rbp+var_20], r14
0x18003defa  mov     dword ptr [rbp+var_58], 48Ah
0x18003df01  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003df08  mov     [rbp+var_50], rax
0x18003df0c  mov     rdx, [rsi]
0x18003df0f  mov     rax, [rbx]
0x18003df12  lea     r8, [rbp+var_20]
0x18003df16  mov     rdx, [rdx]
0x18003df19  mov     rcx, rbx
0x18003df1c  mov     rax, [rax+38h]
0x18003df20  call    cs:__guard_dispatch_icall_fptr
0x18003df26  test    eax, eax
0x18003df28  js      short loc_18003DF61
0x18003df2a  mov     rax, [rbp+var_20]
0x18003df2e  mov     [rdi], rax
0x18003df31  lea     rcx, [rbp+var_60]
0x18003df35  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003df3a  mov     rax, rdi
0x18003df3d  mov     rcx, [rbp+var_8]
0x18003df41  xor     rcx, rsp; StackCookie
0x18003df44  call    __security_check_cookie
0x18003df49  lea     r11, [rsp+80h+var_s0]
0x18003df51  mov     rbx, [r11+20h]
0x18003df55  mov     rsi, [r11+38h]
0x18003df59  mov     rsp, r11
0x18003df5c  pop     r14
0x18003df5e  pop     rdi
0x18003df5f  pop     rbp
0x18003df60  retn
0x18003df61  lfence
0x18003df64  lea     rdx, [rbp+var_58]
0x18003df68  mov     ecx, eax
0x18003df6a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003df70  lfence
0x18003df73  lea     rdx, [rbp+var_58]
0x18003df77  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003df7d  lfence
0x18003df80  lea     rdx, [rbp+var_18]
0x18003df84  mov     ecx, eax
0x18003df86  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
