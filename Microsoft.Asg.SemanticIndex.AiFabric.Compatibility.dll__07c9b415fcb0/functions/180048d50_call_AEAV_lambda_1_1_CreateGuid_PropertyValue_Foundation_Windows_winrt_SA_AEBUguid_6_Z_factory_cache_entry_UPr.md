# ??$call@AEAV_lambda_1_@?1??CreateGuid@PropertyValue@Foundation@Windows@winrt@@SA@AEBUguid@6@@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateGuid@PropertyValue@Foundation@Windows@2@SA@AEBUguid@2@@Z@@Z

- ea: `0x180048d50`
- end: `0x180048f57`
- name: `??$call@AEAV_lambda_1_@?1??CreateGuid@PropertyValue@Foundation@Windows@winrt@@SA@AEBUguid@6@@Z@@?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@QEAA?A_PAEAV_lambda_1_@?1??CreateGuid@PropertyValue@Foundation@Windows@2@SA@AEBUguid@2@@Z@@Z`
- size: `519`
- prototype: `_QWORD *__fastcall(void (__fastcall ***)(_QWORD, _QWORD, _QWORD), _QWORD *, __int128 **)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180048720`

## callees

- `0x180003bd0`
- `0x180010dd0`
- `0x180048910`
- `0x180048d50`
- `0x180229044`
- `0x180242120`

## string_xrefs

- `0x180048da4`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\base.h`
- `0x180048e72`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`
- `0x180048ec7`: `C:\__w\1\s\x64\Release\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\Generated Files\winrt\Windows.Foundation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
_QWORD *__fastcall ___call_AEAV_lambda_1___1__CreateGuid_PropertyValue_Foundation_Windows_winrt__SA_AEBUguid_6__Z____factory_cache_entry_UPropertyValue_Foundation_Windows_winrt__UIPropertyValueStatics_234__impl_winrt__QEAA_A_PAEAV_lambda_1___1__CreateGuid_PropertyValue_Foundation_Windows_2_SA_AEBUguid_2__Z__Z(
        void (__fastcall ***a1)(_QWORD, _QWORD, _QWORD),
        _QWORD *a2,
        __int128 **a3)
{
  void (__fastcall ***v5)(_QWORD, _QWORD, _QWORD); // rbx
  __int128 *v6; // rax
  int v7; // eax
  __int128 *v8; // rax
  int v9; // eax
  __int64 *v11; // [rsp+28h] [rbp-21h] BYREF
  __int128 v12; // [rsp+30h] [rbp-19h] BYREF
  __int64 v13; // [rsp+40h] [rbp-9h]
  int v14; // [rsp+50h] [rbp+7h] BYREF
  const char *v15; // [rsp+58h] [rbp+Fh]
  __int64 v16; // [rsp+60h] [rbp+17h]
  _DWORD *v17; // [rsp+68h] [rbp+1Fh] BYREF
  _DWORD v18[4]; // [rsp+70h] [rbp+27h] BYREF
  const wchar_t *v19; // [rsp+80h] [rbp+37h]
  void (__fastcall ***v20)(_QWORD, _QWORD, _QWORD); // [rsp+B0h] [rbp+67h] BYREF
  void (__fastcall ***v21)(_QWORD, __int64 *, __int64 **); // [rsp+C8h] [rbp+7Fh] BYREF

  v20 = a1;
  v18[0] = 1;
  v18[1] = 32;
  v19 = L"Windows.Foundation.PropertyValue";
  v17 = v18;
  v21 = 0;
  LODWORD(v12) = 6184;
  *((_QWORD *)&v12 + 1) = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Fil"
                          "es\\winrt\\base.h";
  v13 = 0;
  winrt::impl::get_runtime_activation_factory_impl<0>(
    &v20,
    &v17,
    winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValueStatics>,
    &v21);
  if ( (int)v20 < 0 )
  {
    _mm_lfence();
    winrt::throw_hresult((unsigned int)v20, &v12);
  }
  v5 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
  v20 = (void (__fastcall ***)(_QWORD, _QWORD, _QWORD))v21;
  if ( v21 && (v11 = 0, (**v21)(v21, &winrt::impl::guid_v<winrt::impl::IAgileObject>, &v11), v11) )
  {
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v11);
    v11 = &qword_1803E2B18;
    _InterlockedIncrement64(&qword_1803E2B18);
    if ( !_InterlockedCompareExchange64(
            &winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
            (signed __int64)v21,
            0) )
    {
      v20 = 0;
      WINRT_IMPL_InterlockedPushEntrySList(&`winrt::impl::get_factory_cache'::`2'::cache, &ListEntry);
      v5 = 0;
    }
    v6 = *a3;
    v21 = 0;
    v14 = 1515;
    v15 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
    v16 = 0;
    v12 = *v6;
    v7 = (*(__int64 (__fastcall **)(__int64, __int128 *, _QWORD))(*(_QWORD *)winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
                                                                + 160LL))(
           winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>,
           &v12,
           &v21);
    if ( v7 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v7, &v14);
    }
    *a2 = v21;
    _InterlockedDecrement64(&qword_1803E2B18);
  }
  else
  {
    v8 = *a3;
    v21 = 0;
    v14 = 1515;
    v15 = "C:\\__w\\1\\s\\x64\\Release\\Microsoft.Asg.SemanticIndex.AiFabric.Compatibility\\Generated Files\\winrt\\Windows.Foundation.h";
    v16 = 0;
    v12 = *v8;
    v9 = ((__int64 (__fastcall *)(_QWORD, __int128 *, _QWORD))(*v5)[20])(v5, &v12, &v21);
    if ( v9 < 0 )
    {
      _mm_lfence();
      winrt::throw_hresult((unsigned int)v9, &v14);
    }
    *a2 = v21;
  }
  if ( v5 )
    winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(&v20);
  return a2;
}

```

## disassembly

```asm
0x180048d50  mov     [rsp-8+arg_8], rbx
0x180048d55  mov     [rsp-8+arg_10], rsi
0x180048d5a  mov     [rsp-8+arg_0], rcx
0x180048d5f  push    rbp
0x180048d60  push    rdi
0x180048d61  push    r14
0x180048d63  lea     rbp, [rsp-47h]
0x180048d68  sub     rsp, 90h
0x180048d6f  mov     rsi, r8
0x180048d72  mov     rdi, rdx
0x180048d75  xor     r14d, r14d
0x180048d78  mov     [rbp+57h+var_30], 1
0x180048d7f  mov     [rbp+57h+var_2C], 20h ; ' '
0x180048d86  lea     rax, aWindowsFoundat; "Windows.Foundation.PropertyValue"
0x180048d8d  mov     [rbp+57h+var_20], rax
0x180048d91  lea     rax, [rbp+57h+var_30]
0x180048d95  mov     [rbp+57h+var_38], rax
0x180048d99  mov     [rbp+57h+arg_18], r14
0x180048d9d  mov     dword ptr [rbp+57h+var_70], 1828h
0x180048da4  lea     rax, aCW1SX64Release_13; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180048dab  mov     qword ptr [rbp+57h+var_70+8], rax
0x180048daf  mov     [rbp+57h+var_60], r14
0x180048db3  lea     r9, [rbp+57h+arg_18]
0x180048db7  lea     r8, ??$guid_v@UIPropertyValueStatics@Foundation@Windows@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::Windows::Foundation::IPropertyValueStatics>
0x180048dbe  lea     rdx, [rbp+57h+var_38]
0x180048dc2  lea     rcx, [rbp+57h+arg_0]
0x180048dc6  call    ??$get_runtime_activation_factory_impl@$0A@@impl@winrt@@YA?AUhresult@1@AEBUhstring@param@1@AEBUguid@1@PEAPEAX@Z; winrt::impl::get_runtime_activation_factory_impl<0>(winrt::param::hstring const &,winrt::guid const &,void * *)
0x180048dcb  mov     ecx, dword ptr [rbp+57h+arg_0]
0x180048dce  test    ecx, ecx
0x180048dd0  js      loc_180048F3B
0x180048dd6  mov     rbx, [rbp+57h+arg_18]
0x180048dda  mov     [rbp+57h+arg_0], rbx
0x180048dde  test    rbx, rbx
0x180048de1  jz      loc_180048EB9
0x180048de7  mov     [rbp+57h+var_78], r14
0x180048deb  mov     rax, [rbx]
0x180048dee  lea     r8, [rbp+57h+var_78]
0x180048df2  lea     rdx, ??$guid_v@UIAgileObject@impl@winrt@@@impl@winrt@@3Uguid@2@B; guid::guid const winrt::impl::guid_v<winrt::impl::IAgileObject>
0x180048df9  mov     rcx, rbx
0x180048dfc  mov     rax, [rax]
0x180048dff  call    cs:__guard_dispatch_icall_fptr
0x180048e05  mov     rax, [rbp+57h+var_78]
0x180048e09  mov     [rbp+57h+var_78], rax
0x180048e0d  test    rax, rax
0x180048e10  jz      loc_180048EB9
0x180048e16  lea     rcx, [rbp+57h+var_78]
0x180048e1a  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180048e1f  lea     rax, qword_1803E2B18
0x180048e26  mov     [rbp+57h+var_78], rax
0x180048e2a  lock inc cs:qword_1803E2B18
0x180048e32  mov     rcx, [rbp+57h+arg_18]
0x180048e36  xor     eax, eax
0x180048e38  lock cmpxchg cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A, rcx; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x180048e41  jnz     short loc_180048E5D
0x180048e43  mov     [rbp+57h+arg_0], r14
0x180048e47  lea     rdx, ListEntry; ListEntry
0x180048e4e  lea     rcx, ?cache@?1??get_factory_cache@impl@winrt@@YAAEAUfactory_cache@23@XZ@4U423@A; ListHead
0x180048e55  call    WINRT_IMPL_InterlockedPushEntrySList
0x180048e5a  mov     ebx, r14d
0x180048e5d  mov     rax, [rsi]
0x180048e60  mov     [rbp+57h+arg_18], r14
0x180048e64  mov     rcx, cs:??$factory_cache_entry_v@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@impl@winrt@@3U?$factory_cache_entry@UPropertyValue@Foundation@Windows@winrt@@UIPropertyValueStatics@234@@12@A; factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>::winrt::factory_cache_entry<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics> winrt::impl::factory_cache_entry_v<winrt::Windows::Foundation::PropertyValue,winrt::Windows::Foundation::IPropertyValueStatics>
0x180048e6b  mov     [rbp+57h+var_50], 5EBh
0x180048e72  lea     rdx, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180048e79  mov     [rbp+57h+var_48], rdx
0x180048e7d  mov     [rbp+57h+var_40], r14
0x180048e81  movups  xmm0, xmmword ptr [rax]
0x180048e84  movaps  [rbp+57h+var_70], xmm0
0x180048e88  mov     rax, [rcx]
0x180048e8b  lea     r8, [rbp+57h+arg_18]
0x180048e8f  lea     rdx, [rbp+57h+var_70]
0x180048e93  mov     rax, [rax+0A0h]
0x180048e9a  call    cs:__guard_dispatch_icall_fptr
0x180048ea0  test    eax, eax
0x180048ea2  js      loc_180048F48
0x180048ea8  mov     rax, [rbp+57h+arg_18]
0x180048eac  mov     [rdi], rax
0x180048eaf  lock dec cs:qword_1803E2B18
0x180048eb7  jmp     short loc_180048F03
0x180048eb9  mov     rax, [rsi]
0x180048ebc  mov     [rbp+57h+arg_18], r14
0x180048ec0  mov     [rbp+57h+var_50], 5EBh
0x180048ec7  lea     rdx, aCW1SX64Release_12; "C:\\__w\\1\\s\\x64\\Release\\Microsoft."...
0x180048ece  mov     [rbp+57h+var_48], rdx
0x180048ed2  mov     [rbp+57h+var_40], r14
0x180048ed6  movups  xmm0, xmmword ptr [rax]
0x180048ed9  movaps  [rbp+57h+var_70], xmm0
0x180048edd  mov     rax, [rbx]
0x180048ee0  lea     r8, [rbp+57h+arg_18]
0x180048ee4  lea     rdx, [rbp+57h+var_70]
0x180048ee8  mov     rcx, rbx
0x180048eeb  mov     rax, [rax+0A0h]
0x180048ef2  call    cs:__guard_dispatch_icall_fptr
0x180048ef8  test    eax, eax
0x180048efa  js      short loc_180048F2C
0x180048efc  mov     rax, [rbp+57h+arg_18]
0x180048f00  mov     [rdi], rax
0x180048f03  test    rbx, rbx
0x180048f06  jz      short loc_180048F11
0x180048f08  lea     rcx, [rbp+57h+arg_0]
0x180048f0c  call    ?unconditional_release_ref@?$com_ptr@UIMemoryBufferByteAccess@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::IMemoryBufferByteAccess>::unconditional_release_ref(void)
0x180048f11  mov     rax, rdi
0x180048f14  lea     r11, [rsp+0A0h+var_10]
0x180048f1c  mov     rbx, [r11+28h]
0x180048f20  mov     rsi, [r11+30h]
0x180048f24  mov     rsp, r11
0x180048f27  pop     r14
0x180048f29  pop     rdi
0x180048f2a  pop     rbp
0x180048f2b  retn
0x180048f2c  lfence
0x180048f2f  lea     rdx, [rbp+57h+var_50]
0x180048f33  mov     ecx, eax
0x180048f35  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180048f3b  lfence
0x180048f3e  lea     rdx, [rbp+57h+var_70]
0x180048f42  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x180048f48  lfence
0x180048f4b  lea     rdx, [rbp+57h+var_50]
0x180048f4f  mov     ecx, eax
0x180048f51  call    ?throw_hresult@winrt@@YAXUhresult@1@AEBUslim_source_location@impl@1@@Z; winrt::throw_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
```
