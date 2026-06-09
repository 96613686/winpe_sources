# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::EraseAppConsent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004a07c`
- end: `0x18004a2c3`
- name: `?EraseAppConsent@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting`

## callers

- `0x180075d14`

## callees

- `0x1800094c0`
- `0x180016490`
- `0x180016d54`
- `0x18001c3b4`
- `0x18001fd3c`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x1800473fc`
- `0x18004a07c`
- `0x18004e9ec`
- `0x1800588a4`
- `0x18009f3f8`
- `0x18009f9d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a1b8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a1b8`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a1e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a207`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a1e5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004a207`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::EraseAppConsent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v8; // rdx
  __int64 v9; // rax
  __int64 v10; // rdx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *v15; // rcx
  int v16; // eax
  unsigned int v17; // eax
  unsigned int v18; // eax
  unsigned int v20; // eax
  unsigned int v21; // [rsp+20h] [rbp-50h]
  HKEY hKey; // [rsp+30h] [rbp-40h] BYREF
  HKEY v23; // [rsp+38h] [rbp-38h] BYREF
  RTL_SRWLOCK *v24; // [rsp+40h] [rbp-30h] BYREF
  _QWORD Src[2]; // [rsp+48h] [rbp-28h] BYREF
  unsigned __int64 v26; // [rsp+58h] [rbp-18h]
  unsigned __int64 v27; // [rsp+60h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  if ( !*(_QWORD *)(a5 + 16) || !*(_QWORD *)(a2 + 16) )
  {
    v20 = wil::verify_hresult<long>(2147942487LL);
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x80B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v20,
      v21);
  }
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&v23, a2);
  std::wstring::wstring(Src, a3);
  if ( *(_QWORD *)(a4 + 16) )
  {
    if ( v26 >= v27 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v26;
      v9 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v9 + 2 * v10) = 92;
    }
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    std::wstring::_Append<unsigned short>(Src, v11, *(_QWORD *)(a4 + 16));
  }
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( v26 >= v27 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v26;
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v12 + 2 * v13) = 92;
    }
    v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    std::wstring::_Append<unsigned short>(Src, v14, *(_QWORD *)(a5 + 16));
  }
  LOBYTE(v8) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl'::`2'::impl,
    v8);
  if ( Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(v15) )
  {
    v16 = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::EraseUint64Setting(
            4,
            a3,
            a4,
            a5,
            a2);
    if ( v16 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x821,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v16,
        v21);
  }
  AcquireSRWLockExclusive(&stru_180168B88);
  v24 = &stru_180168B88;
  Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(&hKey);
  v17 = RegDeleteValueW(hKey, L"Value");
  if ( v17 != 2 && v17 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x831,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v17,
      v21);
  v18 = RegDeleteValueW(hKey, L"LastSetTime");
  if ( v18 != 2 && v18 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x838,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v18,
      v21);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v24);
  std::wstring::_Tidy_deallocate(Src);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
}

```

## disassembly

```asm
0x18004a07c  mov     [rsp-28h+arg_0], rbx
0x18004a081  push    rbp
0x18004a082  push    rsi
0x18004a083  push    rdi
0x18004a084  push    r12
0x18004a086  push    r14
0x18004a088  mov     rbp, rsp
0x18004a08b  sub     rsp, 70h
0x18004a08f  mov     rax, cs:__security_cookie
0x18004a096  xor     rax, rsp
0x18004a099  mov     [rbp+var_8], rax
0x18004a09d  mov     rsi, r9
0x18004a0a0  mov     r14, r8
0x18004a0a3  mov     rdi, rdx
0x18004a0a6  mov     rbx, [rbp+arg_20]
0x18004a0aa  cmp     qword ptr [rbx+10h], 0
0x18004a0af  jz      loc_18004A276
0x18004a0b5  cmp     qword ptr [rdx+10h], 0
0x18004a0ba  jz      loc_18004A276
0x18004a0c0  mov     r8d, 0F003Fh
0x18004a0c6  lea     rcx, [rbp+var_38]
0x18004a0ca  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x18004a0cf  nop
0x18004a0d0  mov     rdx, r14
0x18004a0d3  lea     rcx, [rbp+Src]
0x18004a0d7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004a0dc  nop
0x18004a0dd  mov     r12d, 5Ch ; '\'
0x18004a0e3  cmp     qword ptr [rsi+10h], 0
0x18004a0e8  jz      short loc_18004A12B
0x18004a0ea  mov     rdx, [rbp+var_18]
0x18004a0ee  lea     rcx, [rbp+Src]; Src
0x18004a0f2  cmp     rdx, [rbp+var_10]
0x18004a0f6  jnb     short loc_18004A10B
0x18004a0f8  lea     rax, [rdx+1]
0x18004a0fc  mov     [rbp+var_18], rax
0x18004a100  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a105  mov     [rax+rdx*2], r12d
0x18004a109  jmp     short loc_18004A113
0x18004a10b  mov     r9d, r12d
0x18004a10e  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004a113  mov     rcx, rsi
0x18004a116  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a11b  mov     r8, [rsi+10h]
0x18004a11f  mov     rdx, rax
0x18004a122  lea     rcx, [rbp+Src]
0x18004a126  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004a12b  cmp     qword ptr [rbx+10h], 0
0x18004a130  jz      short loc_18004A173
0x18004a132  mov     rdx, [rbp+var_18]
0x18004a136  lea     rcx, [rbp+Src]; Src
0x18004a13a  cmp     rdx, [rbp+var_10]
0x18004a13e  jnb     short loc_18004A153
0x18004a140  lea     rax, [rdx+1]
0x18004a144  mov     [rbp+var_18], rax
0x18004a148  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a14d  mov     [rax+rdx*2], r12d
0x18004a151  jmp     short loc_18004A15B
0x18004a153  mov     r9d, r12d
0x18004a156  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004a15b  mov     rcx, rbx
0x18004a15e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a163  mov     r8, [rbx+10h]
0x18004a167  mov     rdx, rax
0x18004a16a  lea     rcx, [rbp+Src]
0x18004a16e  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004a173  mov     dl, 1
0x18004a175  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase> `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl(void)'::`2'::impl
0x18004a17c  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x18004a181  call    ?IsPresent@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(void)
0x18004a186  test    al, al
0x18004a188  jz      short loc_18004A1AE
0x18004a18a  mov     qword ptr [rsp+70h+var_50], rdi; unsigned int
0x18004a18f  mov     r9, rbx
0x18004a192  mov     r8, rsi
0x18004a195  mov     rdx, r14
0x18004a198  mov     ecx, 4
0x18004a19d  call    ?EraseUint64Setting@CAM@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJW4CAMStorageSettingType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::EraseUint64Setting(CAMStorageSettingType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x18004a1a2  mov     rcx, [rbp+28h]; this
0x18004a1a6  test    eax, eax
0x18004a1a8  js      loc_18004A299
0x18004a1ae  lea     rbx, stru_180168B88
0x18004a1b5  mov     rcx, rbx; SRWLock
0x18004a1b8  call    cs:__imp_AcquireSRWLockExclusive
0x18004a1be  mov     [rbp+var_30], rbx
0x18004a1c2  mov     r9d, 0F003Fh
0x18004a1c8  lea     r8, [rbp+Src]
0x18004a1cc  lea     rdx, [rbp+var_38]
0x18004a1d0  lea     rcx, [rbp+hKey]; phkResult
0x18004a1d4  call    ?FullKeyByKeyAndSubPath@Private@CapabilityAccess@Internal@Windows@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV56@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::FullKeyByKeyAndSubPath(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>> const &,std::wstring const &,ulong)
0x18004a1d9  nop
0x18004a1da  lea     rdx, ValueName; "Value"
0x18004a1e1  mov     rcx, [rbp+hKey]; hKey
0x18004a1e5  call    cs:__imp_RegDeleteValueW
0x18004a1eb  cmp     eax, 2
0x18004a1ee  jz      short loc_18004A1FC
0x18004a1f0  mov     rcx, [rbp+28h]; this
0x18004a1f4  test    eax, eax
0x18004a1f6  jnz     loc_18004A2AE
0x18004a1fc  lea     rdx, aLastsettime; "LastSetTime"
0x18004a203  mov     rcx, [rbp+hKey]; hKey
0x18004a207  call    cs:__imp_RegDeleteValueW
0x18004a20d  cmp     eax, 2
0x18004a210  jz      short loc_18004A21A
0x18004a212  mov     rcx, [rbp+28h]; this
0x18004a216  test    eax, eax
0x18004a218  jnz     short loc_18004A261
0x18004a21a  lea     rcx, [rbp+hKey]
0x18004a21e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a223  nop
0x18004a224  lea     rcx, [rbp+var_30]
0x18004a228  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004a22d  nop
0x18004a22e  lea     rcx, [rbp+Src]
0x18004a232  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a237  nop
0x18004a238  lea     rcx, [rbp+var_38]
0x18004a23c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a241  mov     rcx, [rbp+var_8]
0x18004a245  xor     rcx, rsp; StackCookie
0x18004a248  call    __security_check_cookie
0x18004a24d  mov     rbx, [rsp+70h+arg_0]
0x18004a255  add     rsp, 70h
0x18004a259  pop     r14
0x18004a25b  pop     r12
0x18004a25d  pop     rdi
0x18004a25e  pop     rsi
0x18004a25f  pop     rbp
0x18004a260  retn
0x18004a261  mov     r9d, eax; char *
0x18004a264  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004a26b  mov     edx, 838h; void *
0x18004a270  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18004a276  mov     ecx, 80070057h
0x18004a27b  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18004a280  mov     r9d, eax; char *
0x18004a283  mov     rcx, [rbp+28h]; this
0x18004a287  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004a28e  mov     edx, 80Bh; void *
0x18004a293  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a299  mov     r9d, eax; char *
0x18004a29c  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004a2a3  mov     edx, 821h; void *
0x18004a2a8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004a2ae  mov     r9d, eax; char *
0x18004a2b1  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18004a2b8  mov     edx, 831h; void *
0x18004a2bd  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
