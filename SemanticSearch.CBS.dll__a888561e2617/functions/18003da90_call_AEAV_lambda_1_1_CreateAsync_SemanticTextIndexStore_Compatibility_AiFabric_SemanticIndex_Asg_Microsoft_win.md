# ??$call@AEAV_lambda_1_@?1??CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z

- ea: `0x18003da90`
- end: `0x18003dc8c`
- name: `??$call@AEAV_lambda_1_@?1??CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@SA@AEBUSemanticTextIndexStoreOptions@456789@@Z@@?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateAsync@SemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@2@SA@AEBUSemanticTextIndexStoreOptions@6789Microsoft@2@@Z@@Z`
- size: `508`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD **)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18003dc90`

## callees

- `0x180002bb0`
- `0x180008ac0`
- `0x180009580`
- `0x18003da90`
- `0x18004c070`
- `0x1800513a3`
- `0x18005e260`

## string_xrefs

- `0x18003dbaf`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003dc01`: `C:\__w\1\s\product\APIs\Client\Microsoft.Windows.SemanticSearch\x64\Release\Generated Files\winrt\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h`
- `0x18003dad1`: `Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.SemanticTextIndexStore`

## pseudocode

```c
// Hidden C++ exception states: #wind=27
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__SA_AEBUSemanticTextIndexStoreOptions_456789__Z____factory_cache_entry_USemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_winrt__UISemanticTextIndexStoreStatics_234567__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateAsync_SemanticTextIndexStore_Compatibility_AiFabric_SemanticIndex_Asg_Microsoft_2_SA_AEBUSemanticTextIndexStoreOptions_6789Microsoft_2__Z__Z(
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
    LODWORD(v10) = 1168;
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
  LODWORD(v16[0]) = 1168;
  v16[1] = (signed __int64)"C:\\__w\\1\\s\\product\\APIs\\Client\\Microsoft.Windows.SemanticSearch\\x64\\Release\\Generat"
                           "ed Files\\winrt\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility.h";
  v6 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD **))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
                                                             + 64LL))(
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
0x18003da90  mov     [rsp-18h+arg_0], rbx
0x18003da95  mov     [rsp-18h+arg_18], rsi
0x18003da9a  push    rbp
0x18003da9b  push    rdi
0x18003da9c  push    r14
0x18003da9e  mov     rbp, rsp
0x18003daa1  sub     rsp, 80h
0x18003daa8  mov     rax, cs:__security_cookie
0x18003daaf  xor     rax, rsp
0x18003dab2  mov     [rbp+var_8], rax
0x18003dab6  mov     rsi, r8
0x18003dab9  mov     rdi, rdx
0x18003dabc  mov     [rbp+var_20], rdx
0x18003dac0  xor     r14d, r14d
0x18003dac3  mov     [rbp+var_38], 1
0x18003daca  mov     [rbp+var_34], 49h ; 'I'
0x18003dad1  lea     rax, aMicrosoftAsgSe_0; "Microsoft.Asg.SemanticIndex.AiFabric.Co"...
0x18003dad8  mov     [rbp+var_28], rax
0x18003dadc  lea     rax, [rbp+var_38]
0x18003dae0  mov     [rbp+var_40], rax
0x18003dae4  mov     [rbp+var_18], r14
0x18003dae8  mov     dword ptr [rbp+var_58], 1804h
0x18003daef  lea     rax, aCW1SProductApi_4; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003daf6  mov     [rbp+var_50], rax
0x18003dafa  lea     r9, [rbp+var_18]
0x18003dafe  lea     r8, ??$guid_v@UISemanticTextIndexStoreStatics@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003db05  lea     rdx, [rbp+var_40]
0x18003db09  lea     rcx, [rbp+var_60]
0x18003db0d  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x18003db12  mov     ecx, dword ptr [rbp+var_60]
0x18003db15  test    ecx, ecx
0x18003db17  js      loc_18003DC70
0x18003db1d  mov     rbx, [rbp+var_18]
0x18003db21  mov     [rbp+var_60], rbx
0x18003db25  test    rbx, rbx
0x18003db28  jz      loc_18003DBF6
0x18003db2e  mov     [rbp+var_20], r14
0x18003db32  mov     rax, [rbx]
0x18003db35  lea     r8, [rbp+var_20]
0x18003db39  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x18003db40  mov     rcx, rbx
0x18003db43  mov     rax, [rax]
0x18003db46  call    cs:__guard_dispatch_icall_fptr
0x18003db4c  mov     rax, [rbp+var_20]
0x18003db50  mov     [rbp+var_20], rax
0x18003db54  test    rax, rax
0x18003db57  jz      loc_18003DBF6
0x18003db5d  lea     rcx, [rbp+var_20]
0x18003db61  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003db66  lea     rax, qword_180086A78
0x18003db6d  mov     [rbp+var_58], rax
0x18003db71  lock inc cs:qword_180086A78
0x18003db79  mov     rcx, [rbp+var_18]
0x18003db7d  xor     eax, eax
0x18003db7f  lock cmpxchg cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A, rcx; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003db88  jnz     short loc_18003DBA4
0x18003db8a  mov     [rbp+var_60], r14
0x18003db8e  lea     rdx, stru_180086A80; ListEntry
0x18003db95  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x18003db9c  call    WINRT_IMPL_InterlockedPushEntrySList
0x18003dba1  mov     ebx, r14d
0x18003dba4  mov     [rbp+var_20], r14
0x18003dba8  mov     dword ptr [rbp+var_18], 490h
0x18003dbaf  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003dbb6  mov     [rbp+var_10], rax
0x18003dbba  mov     rcx, cs:??$factory_cache_entry_v@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@impl@winrt@@3U?$factory_cache_entry@USemanticTextIndexStore@Compatibility@AiFabric@SemanticIndex@Asg@Microsoft@winrt@@UISemanticTextIndexStoreStatics@234567@@12@A; factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>::winrt::factory_cache_entry<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics> winrt::impl::factory_cache_entry_v<winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::SemanticTextIndexStore,winrt::Microsoft::Asg::SemanticIndex::AiFabric::Compatibility::ISemanticTextIndexStoreStatics>
0x18003dbc1  mov     rdx, [rsi]
0x18003dbc4  mov     rax, [rcx]
0x18003dbc7  lea     r8, [rbp+var_20]
0x18003dbcb  mov     rdx, [rdx]
0x18003dbce  mov     rax, [rax+40h]
0x18003dbd2  call    cs:__guard_dispatch_icall_fptr
0x18003dbd8  test    eax, eax
0x18003dbda  js      loc_18003DC7D
0x18003dbe0  mov     rcx, [rbp+var_20]
0x18003dbe4  mov     [rdi], rcx
0x18003dbe7  lock dec cs:qword_180086A78
0x18003dbef  test    rbx, rbx
0x18003dbf2  jz      short loc_18003DC3A
0x18003dbf4  jmp     short loc_18003DC31
0x18003dbf6  mov     [rbp+var_20], r14
0x18003dbfa  mov     dword ptr [rbp+var_58], 490h
0x18003dc01  lea     rax, aCW1SProductApi_29; "C:\\__w\\1\\s\\product\\APIs\\Client\\M"...
0x18003dc08  mov     [rbp+var_50], rax
0x18003dc0c  mov     rdx, [rsi]
0x18003dc0f  mov     rax, [rbx]
0x18003dc12  lea     r8, [rbp+var_20]
0x18003dc16  mov     rdx, [rdx]
0x18003dc19  mov     rcx, rbx
0x18003dc1c  mov     rax, [rax+40h]
0x18003dc20  call    cs:__guard_dispatch_icall_fptr
0x18003dc26  test    eax, eax
0x18003dc28  js      short loc_18003DC61
0x18003dc2a  mov     rax, [rbp+var_20]
0x18003dc2e  mov     [rdi], rax
0x18003dc31  lea     rcx, [rbp+var_60]
0x18003dc35  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x18003dc3a  mov     rax, rdi
0x18003dc3d  mov     rcx, [rbp+var_8]
0x18003dc41  xor     rcx, rsp; StackCookie
0x18003dc44  call    __security_check_cookie
0x18003dc49  lea     r11, [rsp+80h+var_s0]
0x18003dc51  mov     rbx, [r11+20h]
0x18003dc55  mov     rsi, [r11+38h]
0x18003dc59  mov     rsp, r11
0x18003dc5c  pop     r14
0x18003dc5e  pop     rdi
0x18003dc5f  pop     rbp
0x18003dc60  retn
0x18003dc61  lfence
0x18003dc64  lea     rdx, [rbp+var_58]
0x18003dc68  mov     ecx, eax
0x18003dc6a  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003dc70  lfence
0x18003dc73  lea     rdx, [rbp+var_58]
0x18003dc77  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x18003dc7d  lfence
0x18003dc80  lea     rdx, [rbp+var_18]
0x18003dc84  mov     ecx, eax
0x18003dc86  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
