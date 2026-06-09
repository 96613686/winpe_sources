# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetConsent2(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::Identity::AppIdentityHelper const &,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)

- ea: `0x18004fc74`
- end: `0x180050152`
- name: `?SetConsent2@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBVAppIdentityHelper@Identity@2345@W4CapabilityConsentValue@2345@@Z`
- size: `1246`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x180051198`

## callees

- `0x1800094c0`
- `0x180016490`
- `0x18001649c`
- `0x180016d54`
- `0x18001c3b4`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x18003ce34`
- `0x180043224`
- `0x180046270`
- `0x1800473fc`
- `0x180047d54`
- `0x1800492e8`
- `0x18004e9ec`
- `0x18004fa58`
- `0x18004fc74`
- `0x18005258c`
- `0x180058ef8`
- `0x180058f58`
- `0x180058fb8`
- `0x180059008`
- `0x18009f9d4`
- `0x18009fc34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fe2e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004fe2e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fe12`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005005b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004fe12`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005005b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetConsent2(
        Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  char v9; // r13
  int v10; // edi
  int v11; // eax
  __int64 v12; // rax
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  const WCHAR *v18; // rax
  unsigned int v19; // eax
  __int64 v20; // rax
  Windows::Internal::CapabilityAccess::Private *v21; // rcx
  const unsigned __int16 *SystemTimeAsUInt64; // rax
  unsigned __int64 v23; // r9
  __int64 v24; // rdi
  const wchar_t *v25; // rbx
  __int64 v26; // rax
  const wchar_t *v28; // rdx
  unsigned __int64 v29; // r8
  __int64 v30; // rax
  const WCHAR *v31; // rax
  unsigned int v32; // eax
  unsigned int v33; // r9d
  unsigned int v34; // eax
  int dwOptions; // [rsp+20h] [rbp-B9h]
  int dwOptionsa; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsb; // [rsp+20h] [rbp-B9h]
  unsigned int dwOptionsc; // [rsp+20h] [rbp-B9h]
  HKEY phkResult; // [rsp+50h] [rbp-89h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-81h] BYREF
  RTL_SRWLOCK *v41; // [rsp+60h] [rbp-79h] BYREF
  _QWORD Src[2]; // [rsp+68h] [rbp-71h] BYREF
  unsigned __int64 v43; // [rsp+78h] [rbp-61h]
  unsigned __int64 v44; // [rsp+80h] [rbp-59h]
  _QWORD v45[4]; // [rsp+88h] [rbp-51h] BYREF
  _BYTE v46[32]; // [rsp+A8h] [rbp-31h] BYREF
  _BYTE v47[16]; // [rsp+C8h] [rbp-11h] BYREF
  unsigned __int64 v48; // [rsp+D8h] [rbp-1h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+4Fh]

  v9 = 0;
  LODWORD(phkResult) = 0;
  if ( *(_DWORD *)(a5 + 8) == 1 )
  {
    if ( Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(a1) )
    {
      if ( *(_QWORD *)(a2 + 16) )
      {
        v10 = 2;
        if ( *(_QWORD *)(a5 + 40) )
          v10 = 4;
      }
      else
      {
        v10 = 1;
      }
      v11 = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::PutUint64Setting(
              v10,
              a3,
              a4,
              (int)a5 + 24,
              a2,
              a6);
      if ( v11 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x5DB,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)(unsigned int)v11,
          dwOptionsa);
    }
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, a2);
    std::wstring::wstring(Src, a3);
    if ( *(_QWORD *)(a4 + 16) )
    {
      if ( v43 >= v44 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v43;
        v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v12 + 2 * v13) = 92;
      }
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      std::wstring::_Append<unsigned short>(Src, v14, *(_QWORD *)(a4 + 16));
    }
    if ( *(_QWORD *)(a5 + 40) )
    {
      if ( v43 >= v44 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
      }
      else
      {
        ++v43;
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
        *(_DWORD *)(v15 + 2 * v16) = 92;
      }
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5 + 24);
      std::wstring::_Append<unsigned short>(Src, v17, *(_QWORD *)(a5 + 40));
    }
    phkResult = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    v19 = RegCreateKeyExW(hKey, v18, 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
    if ( v19 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x5FE,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)v19,
        dwOptionsb);
    AcquireSRWLockExclusive(&stru_180168B88);
    v41 = &stru_180168B88;
    v20 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(
            v46,
            a6);
    Windows::Internal::CapabilityAccess::Private::RegSetStringValue(phkResult, L"Value", v20);
    std::wstring::_Tidy_deallocate(v46);
    SystemTimeAsUInt64 = (const unsigned __int16 *)Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(v21);
    Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(
      (Windows::Internal::CapabilityAccess::Private *)phkResult,
      (HKEY)L"LastSetTime",
      SystemTimeAsUInt64,
      v23);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      v25 = L"system";
      if ( *(_QWORD *)(a2 + 16) )
        v25 = (const wchar_t *)L"user";
      v26 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(
              v46,
              a6);
      v9 = 1;
      std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v25, v24);
    }
    if ( (v9 & 1) != 0 )
      std::wstring::_Tidy_deallocate(v46);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v41);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    std::wstring::_Tidy_deallocate(Src);
  }
  else
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, a2);
    phkResult = 0;
    std::wstring::wstring(v45, a3);
    std::wstring::_Append<unsigned short>(v45, (__int64)L"\\", 1u);
    if ( *(_DWORD *)(a5 + 8) == 3 )
    {
      v28 = L"UnsignedBinaries";
      v29 = 16;
    }
    else
    {
      if ( *(_DWORD *)(a5 + 8) != 2 )
      {
        v34 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x628,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)v34,
          dwOptions);
      }
      v28 = L"BinariesWithCertificates";
      v29 = 24;
    }
    std::wstring::_Append<unsigned short>(v45, (__int64)v28, v29);
    std::wstring::_Append<unsigned short>(v45, (__int64)L"\\", 1u);
    std::wstring::wstring(v47, a5 + 88);
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::RemoveBackslashes(v47);
    v30 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v47);
    std::wstring::_Append<unsigned short>(v45, v30, v48);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v31 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v45);
    v32 = RegCreateKeyExW(hKey, v31, 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
    if ( v32 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x63C,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)v32,
        dwOptionsc);
    if ( *(_DWORD *)(a5 + 8) == 2 )
    {
      std::vector<unsigned char>::vector<unsigned char>(Src, a5 + 120);
      std::wstring::wstring(v46, L"HashValue");
      Windows::Internal::CapabilityAccess::Private::RegSetBinaryValue(phkResult, v46, Src);
      std::wstring::_Tidy_deallocate(v46);
      std::vector<unsigned char>::_Tidy(Src);
    }
    Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
      (Windows::Internal::CapabilityAccess::Private *)phkResult,
      (HKEY)L"Value",
      (const unsigned __int16 *)a6,
      v33);
    std::wstring::_Tidy_deallocate(v47);
    std::wstring::_Tidy_deallocate(v45);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  }
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x18004fc74  mov     [rsp-8+arg_0], rbx
0x18004fc79  push    rbp
0x18004fc7a  push    rsi
0x18004fc7b  push    rdi
0x18004fc7c  push    r12
0x18004fc7e  push    r13
0x18004fc80  push    r14
0x18004fc82  push    r15
0x18004fc84  lea     rbp, [rsp-17h]
0x18004fc89  sub     rsp, 0F0h
0x18004fc90  mov     rax, cs:__security_cookie
0x18004fc97  xor     rax, rsp
0x18004fc9a  mov     [rbp+47h+var_38], rax
0x18004fc9e  mov     r14, r9
0x18004fca1  mov     r15, r8
0x18004fca4  mov     rsi, rdx
0x18004fca7  mov     rbx, [rbp+47h+arg_20]
0x18004fcab  mov     r12d, dword ptr [rbp+47h+arg_28]
0x18004fcaf  xor     edi, edi
0x18004fcb1  mov     r13d, edi
0x18004fcb4  mov     dword ptr [rsp+120h+var_D0], edi
0x18004fcb8  cmp     dword ptr [rbx+8], 1
0x18004fcbc  jnz     loc_18004FF59
0x18004fcc2  call    ?IsPresent@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(void)
0x18004fcc7  test    al, al
0x18004fcc9  jz      short loc_18004FD14
0x18004fccb  cmp     [rsi+10h], rdi
0x18004fccf  jnz     short loc_18004FCD8
0x18004fcd1  mov     edi, 1
0x18004fcd6  jmp     short loc_18004FCE8
0x18004fcd8  cmp     [rbx+28h], rdi
0x18004fcdc  mov     edi, 2
0x18004fce1  jz      short loc_18004FCE8
0x18004fce3  mov     edi, 4
0x18004fce8  mov     r9, rbx
0x18004fceb  add     r9, 18h
0x18004fcef  mov     qword ptr [rsp+120h+samDesired], r12
0x18004fcf4  mov     qword ptr [rsp+120h+dwOptions], rsi; int
0x18004fcf9  mov     r8, r14
0x18004fcfc  mov     rdx, r15
0x18004fcff  mov     ecx, edi
0x18004fd01  call    ?PutUint64Setting@CAM@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJW4CAMStorageSettingType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111_K@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::PutUint64Setting(CAMStorageSettingType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,unsigned __int64)
0x18004fd06  mov     rcx, [rbp+4Fh]; this
0x18004fd0a  xor     edi, edi
0x18004fd0c  test    eax, eax
0x18004fd0e  js      loc_180050128
0x18004fd14  mov     r8d, 0F003Fh
0x18004fd1a  mov     rdx, rsi
0x18004fd1d  lea     rcx, [rsp+120h+hKey]
0x18004fd22  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x18004fd27  nop
0x18004fd28  mov     rdx, r15
0x18004fd2b  lea     rcx, [rbp+47h+Src]
0x18004fd2f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004fd34  nop
0x18004fd35  mov     r15d, 5Ch ; '\'
0x18004fd3b  cmp     [r14+10h], rdi
0x18004fd3f  jz      short loc_18004FD82
0x18004fd41  mov     rdx, [rbp+47h+var_A8]
0x18004fd45  lea     rcx, [rbp+47h+Src]; Src
0x18004fd49  cmp     rdx, [rbp+47h+var_A0]
0x18004fd4d  jnb     short loc_18004FD62
0x18004fd4f  lea     rax, [rdx+1]
0x18004fd53  mov     [rbp+47h+var_A8], rax
0x18004fd57  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fd5c  mov     [rax+rdx*2], r15d
0x18004fd60  jmp     short loc_18004FD6A
0x18004fd62  mov     r9d, r15d
0x18004fd65  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004fd6a  mov     rcx, r14
0x18004fd6d  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fd72  mov     r8, [r14+10h]
0x18004fd76  mov     rdx, rax
0x18004fd79  lea     rcx, [rbp+47h+Src]
0x18004fd7d  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004fd82  cmp     [rbx+28h], rdi
0x18004fd86  jz      short loc_18004FDCA
0x18004fd88  mov     rdx, [rbp+47h+var_A8]
0x18004fd8c  lea     rcx, [rbp+47h+Src]; Src
0x18004fd90  cmp     rdx, [rbp+47h+var_A0]
0x18004fd94  jnb     short loc_18004FDA9
0x18004fd96  lea     rax, [rdx+1]
0x18004fd9a  mov     [rbp+47h+var_A8], rax
0x18004fd9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fda3  mov     [rax+rdx*2], r15d
0x18004fda7  jmp     short loc_18004FDB1
0x18004fda9  mov     r9d, r15d
0x18004fdac  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004fdb1  lea     rcx, [rbx+18h]
0x18004fdb5  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fdba  mov     r8, [rbx+28h]
0x18004fdbe  mov     rdx, rax
0x18004fdc1  lea     rcx, [rbp+47h+Src]
0x18004fdc5  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004fdca  mov     [rsp+120h+var_D0], rdi
0x18004fdcf  xor     edx, edx
0x18004fdd1  lea     rcx, [rsp+120h+var_D0]
0x18004fdd6  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004fddb  lea     rcx, [rbp+47h+Src]
0x18004fddf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fde4  mov     rdx, rax; lpSubKey
0x18004fde7  mov     [rsp+120h+lpdwDisposition], rdi; lpdwDisposition
0x18004fdec  lea     rax, [rsp+120h+var_D0]
0x18004fdf1  mov     [rsp+120h+phkResult], rax; phkResult
0x18004fdf6  mov     [rsp+120h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18004fdfb  mov     [rsp+120h+samDesired], 0F013Fh; samDesired
0x18004fe03  mov     [rsp+120h+dwOptions], edi; unsigned int
0x18004fe07  xor     r9d, r9d; lpClass
0x18004fe0a  xor     r8d, r8d; Reserved
0x18004fe0d  mov     rcx, [rsp+120h+hKey]; hKey
0x18004fe12  call    cs:__imp_RegCreateKeyExW
0x18004fe18  mov     rcx, [rbp+4Fh]; this
0x18004fe1c  test    eax, eax
0x18004fe1e  jnz     loc_18005013D
0x18004fe24  lea     rbx, stru_180168B88
0x18004fe2b  mov     rcx, rbx; SRWLock
0x18004fe2e  call    cs:__imp_AcquireSRWLockExclusive
0x18004fe34  mov     [rbp+47h+var_C0], rbx
0x18004fe38  mov     edx, r12d
0x18004fe3b  lea     rcx, [rbp+47h+var_78]
0x18004fe3f  call    ?CapabilityConsentStringFromValue@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CapabilityConsentValue@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x18004fe44  nop
0x18004fe45  mov     r8, rax
0x18004fe48  lea     rdx, ValueName; "Value"
0x18004fe4f  mov     rcx, [rsp+120h+var_D0]
0x18004fe54  call    ?RegSetStringValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::RegSetStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x18004fe59  nop
0x18004fe5a  lea     rcx, [rbp+47h+var_78]
0x18004fe5e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004fe63  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x18004fe68  mov     r8, rax; unsigned __int16 *
0x18004fe6b  lea     rdx, aLastsettime; "LastSetTime"
0x18004fe72  mov     rcx, [rsp+120h+var_D0]; this
0x18004fe77  call    ?RegSetUint64Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBG_K@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(HKEY__ *,ushort const *,unsigned __int64)
0x18004fe7c  lea     rcx, WPP_GLOBAL_Control
0x18004fe83  mov     rax, cs:WPP_GLOBAL_Control
0x18004fe8a  cmp     rax, rcx
0x18004fe8d  jz      short loc_18004FEF9
0x18004fe8f  test    byte ptr [rax+1Ch], 1
0x18004fe93  jz      short loc_18004FEF9
0x18004fe95  cmp     byte ptr [rax+19h], 4
0x18004fe99  jb      short loc_18004FEF9
0x18004fe9b  lea     rcx, [rbp+47h+Src]
0x18004fe9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fea4  mov     rdi, rax
0x18004fea7  lea     rax, aUser; "user"
0x18004feae  lea     rbx, aSystem; "system"
0x18004feb5  cmp     qword ptr [rsi+10h], 0
0x18004feba  cmovnz  rbx, rax
0x18004febe  mov     edx, r12d
0x18004fec1  lea     rcx, [rbp+47h+var_78]
0x18004fec5  call    ?CapabilityConsentStringFromValue@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CapabilityConsentValue@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x18004feca  mov     r13d, 1
0x18004fed0  mov     rcx, rax
0x18004fed3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fed8  lea     edx, [r13+0Ch]
0x18004fedc  mov     qword ptr [rsp+120h+samDesired], rdi; __int64
0x18004fee1  mov     qword ptr [rsp+120h+dwOptions], rbx; __int64
0x18004fee6  mov     r9, rax
0x18004fee9  mov     rcx, cs:WPP_GLOBAL_Control
0x18004fef0  mov     rcx, [rcx+10h]; LoggerHandle
0x18004fef4  call    WPP_SF_SSS
0x18004fef9  test    r13b, 1
0x18004fefd  jz      short loc_18004FF09
0x18004feff  lea     rcx, [rbp+47h+var_78]
0x18004ff03  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff08  nop
0x18004ff09  lea     rcx, [rbp+47h+var_C0]
0x18004ff0d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004ff12  nop
0x18004ff13  lea     rcx, [rsp+120h+var_D0]
0x18004ff18  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004ff1d  nop
0x18004ff1e  lea     rcx, [rbp+47h+Src]
0x18004ff22  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ff27  nop
0x18004ff28  lea     rcx, [rsp+120h+hKey]
0x18004ff2d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004ff32  mov     rcx, [rbp+47h+var_38]
0x18004ff36  xor     rcx, rsp; StackCookie
0x18004ff39  call    __security_check_cookie
0x18004ff3e  mov     rbx, [rsp+120h+arg_0]
0x18004ff46  add     rsp, 0F0h
0x18004ff4d  pop     r15
0x18004ff4f  pop     r14
0x18004ff51  pop     r13
0x18004ff53  pop     r12
0x18004ff55  pop     rdi
0x18004ff56  pop     rsi
0x18004ff57  pop     rbp
0x18004ff58  retn
0x18004ff59  mov     r8d, 20019h
0x18004ff5f  lea     rcx, [rsp+120h+hKey]
0x18004ff64  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x18004ff69  nop
0x18004ff6a  mov     [rsp+120h+var_D0], rdi
0x18004ff6f  mov     rdx, r15
0x18004ff72  lea     rcx, [rbp+47h+var_98]
0x18004ff76  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ff7b  nop
0x18004ff7c  mov     esi, 1
0x18004ff81  mov     r8d, esi
0x18004ff84  lea     rdx, asc_1800D35BC; "\\"
0x18004ff8b  lea     rcx, [rbp+47h+var_98]
0x18004ff8f  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004ff94  lea     edi, [rsi+1]
0x18004ff97  cmp     dword ptr [rbx+8], 3
0x18004ff9b  jnz     short loc_18004FFAA
0x18004ff9d  lea     rdx, aUnsignedbinari; "UnsignedBinaries"
0x18004ffa4  lea     r8d, [rsi+0Fh]
0x18004ffa8  jmp     short loc_18004FFC0
0x18004ffaa  cmp     [rbx+8], edi
0x18004ffad  jnz     loc_180050105
0x18004ffb3  lea     rdx, aBinarieswithce; "BinariesWithCertificates"
0x18004ffba  mov     r8d, 18h
0x18004ffc0  lea     rcx, [rbp+47h+var_98]
0x18004ffc4  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004ffc9  mov     r8, rsi
0x18004ffcc  lea     rdx, asc_1800D35BC; "\\"
0x18004ffd3  lea     rcx, [rbp+47h+var_98]
0x18004ffd7  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004ffdc  lea     rdx, [rbx+58h]
0x18004ffe0  lea     rcx, [rbp+47h+var_58]
0x18004ffe4  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004ffe9  nop
0x18004ffea  lea     rcx, [rbp+47h+var_58]
0x18004ffee  call    ?RemoveBackslashes@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::RemoveBackslashes(std::wstring &)
0x18004fff3  lea     rcx, [rbp+47h+var_58]
0x18004fff7  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004fffc  mov     rdx, rax
0x18004ffff  mov     r8, [rbp+47h+var_48]
0x180050003  lea     rcx, [rbp+47h+var_98]
0x180050007  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005000c  xor     edx, edx
0x18005000e  lea     rcx, [rsp+120h+var_D0]
0x180050013  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180050018  lea     rcx, [rbp+47h+var_98]
0x18005001c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050021  mov     rdx, rax; lpSubKey
0x180050024  mov     [rsp+120h+lpdwDisposition], 0; lpdwDisposition
0x18005002d  lea     rax, [rsp+120h+var_D0]
0x180050032  mov     [rsp+120h+phkResult], rax; phkResult
0x180050037  mov     [rsp+120h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180050040  mov     [rsp+120h+samDesired], 0F013Fh; samDesired
0x180050048  mov     [rsp+120h+dwOptions], 0; unsigned int
0x180050050  xor     r9d, r9d; lpClass
0x180050053  xor     r8d, r8d; Reserved
0x180050056  mov     rcx, [rsp+120h+hKey]; hKey
0x18005005b  call    cs:__imp_RegCreateKeyExW
0x180050061  mov     rcx, [rbp+4Fh]; this
0x180050065  test    eax, eax
0x180050067  jnz     loc_1800500F0
0x18005006d  cmp     [rbx+8], edi
0x180050070  jnz     short loc_1800500B7
0x180050072  lea     rdx, [rbx+78h]
0x180050076  lea     rcx, [rbp+47h+Src]
0x18005007a  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18005007f  nop
0x180050080  lea     rdx, aHashvalue; "HashValue"
0x180050087  lea     rcx, [rbp+47h+var_78]
0x18005008b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180050090  nop
0x180050091  lea     r8, [rbp+47h+Src]
0x180050095  lea     rdx, [rbp+47h+var_78]
0x180050099  mov     rcx, [rsp+120h+var_D0]
0x18005009e  call    ?RegSetBinaryValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@EV?$allocator@E@std@@@7@@Z; Windows::Internal::CapabilityAccess::Private::RegSetBinaryValue(HKEY__ *,std::wstring const &,std::vector<uchar> const &)
0x1800500a3  nop
0x1800500a4  lea     rcx, [rbp+47h+var_78]
0x1800500a8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800500ad  nop
0x1800500ae  lea     rcx, [rbp+47h+Src]
0x1800500b2  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800500b7  mov     r8d, r12d; unsigned __int16 *
0x1800500ba  lea     rdx, ValueName; "Value"
0x1800500c1  mov     rcx, [rsp+120h+var_D0]; this
0x1800500c6  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x1800500cb  nop
0x1800500cc  lea     rcx, [rbp+47h+var_58]
0x1800500d0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800500d5  nop
0x1800500d6  lea     rcx, [rbp+47h+var_98]
0x1800500da  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800500df  nop
0x1800500e0  lea     rcx, [rsp+120h+var_D0]
0x1800500e5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800500ea  nop
0x1800500eb  jmp     loc_18004FF28
0x1800500f0  mov     r9d, eax; char *
0x1800500f3  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x1800500fa  mov     edx, 63Ch; void *
0x1800500ff  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180050105  mov     ecx, 8000FFFFh
0x18005010a  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x18005010f  mov     r9d, eax; char *
0x180050112  mov     rcx, [rbp+4Fh]; this
0x180050116  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18005011d  mov     edx, 628h; void *
0x180050122  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180050128  mov     r9d, eax; char *
0x18005012b  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
  ... truncated ...
```
