# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetConsent2(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::Identity::AppIdentityHelper const &)

- ea: `0x18004a788`
- end: `0x18004ac81`
- name: `?GetConsent2@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@AEBA?AW4CapabilityConsentValue@2345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEBVAppIdentityHelper@Identity@2345@@Z`
- size: `1273`
- prototype: ``
- caller_count: `1`
- callee_count: `27`
- tags: `registry_config, loader_planting`

## callers

- `0x18004c758`

## callees

- `0x1800094c0`
- `0x18000d829`
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
- `0x18002f93c`
- `0x18003ce34`
- `0x180046270`
- `0x1800473fc`
- `0x180047d54`
- `0x180049358`
- `0x18004941c`
- `0x18004a788`
- `0x18004e9ec`
- `0x18004fa58`
- `0x180058950`
- `0x180058c8c`
- `0x180058dfc`
- `0x18009f8d8`
- `0x18009f9d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a91e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004a91e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ab6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ab8e`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ab6c`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18004ab8e`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aad0`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004aad0`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetConsent2(
        Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  int v8; // edi
  int Uint64Setting; // eax
  __int64 v11; // rax
  __int64 v12; // rdx
  __int64 v13; // rax
  __int64 v14; // rbx
  __int64 v15; // rax
  __int64 v16; // rdx
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 StringValue; // rax
  __int64 v20; // rcx
  unsigned int v21; // edi
  const wchar_t *v22; // rdx
  unsigned __int64 v23; // r8
  __int64 v24; // rax
  const WCHAR *v25; // rax
  unsigned int v26; // eax
  bool v27; // bl
  unsigned int v28; // eax
  unsigned int v29; // eax
  unsigned int Uint32Value; // ebx
  unsigned int v31; // eax
  int dwOptions; // [rsp+20h] [rbp-B1h]
  int dwOptionsa; // [rsp+20h] [rbp-B1h]
  bool *dwOptionsb; // [rsp+20h] [rbp-B1h]
  unsigned __int16 v35; // [rsp+50h] [rbp-81h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-71h] BYREF
  void *Buf2[2]; // [rsp+68h] [rbp-69h] BYREF
  unsigned __int64 v39; // [rsp+78h] [rbp-59h]
  unsigned __int64 v40; // [rsp+80h] [rbp-51h]
  void *Buf1[2]; // [rsp+88h] [rbp-49h] BYREF
  __m128i si128; // [rsp+98h] [rbp-39h]
  _QWORD v43[4]; // [rsp+A8h] [rbp-29h] BYREF
  _BYTE v44[16]; // [rsp+C8h] [rbp-9h] BYREF
  unsigned __int64 v45; // [rsp+D8h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+128h] [rbp+57h]

  v8 = 1;
  if ( *(_DWORD *)(a5 + 8) != 1 )
  {
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, a2);
    phkResult = 0;
    std::wstring::wstring(v43, a3);
    std::wstring::_Append<unsigned short>(v43, (__int64)L"\\", 1u);
    if ( *(_DWORD *)(a5 + 8) == 3 )
    {
      v22 = L"UnsignedBinaries";
      v23 = 16;
    }
    else
    {
      if ( *(_DWORD *)(a5 + 8) != 2 )
      {
        v31 = wil::verify_hresult<long>(2147549183LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2A7,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          (const char *)v31,
          dwOptions);
      }
      v22 = L"BinariesWithCertificates";
      v23 = 24;
    }
    std::wstring::_Append<unsigned short>(v43, (__int64)v22, v23);
    std::wstring::_Append<unsigned short>(v43, (__int64)L"\\", 1u);
    std::wstring::wstring(v44, a5 + 88);
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::RemoveBackslashes(v44);
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44);
    std::wstring::_Append<unsigned short>(v43, v24, v45);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &phkResult,
      0);
    v25 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v43);
    v26 = RegCreateKeyExW(hKey, v25, 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
    if ( v26 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x2BB,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)v26,
        (unsigned int)dwOptionsb);
    LOBYTE(v35) = 0;
    if ( *(_DWORD *)(a5 + 8) == 2 )
    {
      *(_OWORD *)Buf1 = 0;
      si128.m128i_i64[0] = 0;
      std::wstring::wstring(Buf2, L"HashValue");
      Windows::Internal::CapabilityAccess::Private::RegGetBinaryValue(phkResult);
      std::wstring::_Tidy_deallocate(Buf2);
      std::vector<unsigned char>::vector<unsigned char>(Buf2, a5 + 120);
      v27 = memcmp_0(Buf1[0], Buf2[0], (char *)Buf1[1] - (char *)Buf1[0]) != 0;
      std::vector<unsigned char>::_Tidy(Buf2);
      if ( v27 )
      {
        v28 = RegDeleteValueW(phkResult, L"HashValue");
        if ( v28 != 2 && v28 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2D1,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)v28,
            (unsigned int)dwOptionsb);
        v29 = RegDeleteValueW(phkResult, L"Value");
        if ( v29 != 2 && v29 )
          wil::details::in1diag3::Throw_Win32(
            retaddr,
            (void *)0x2D8,
            (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
            (const char *)v29,
            (unsigned int)dwOptionsb);
        std::vector<unsigned char>::_Tidy(Buf1);
        goto LABEL_39;
      }
      std::vector<unsigned char>::_Tidy(Buf1);
    }
    Uint32Value = Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
                    (Windows::Internal::CapabilityAccess::Private *)phkResult,
                    0,
                    L"Value",
                    &v35,
                    dwOptionsb);
    if ( (_BYTE)v35 )
    {
LABEL_40:
      std::wstring::_Tidy_deallocate(v44);
      std::wstring::_Tidy_deallocate(v43);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      return Uint32Value;
    }
LABEL_39:
    Uint32Value = 0;
    goto LABEL_40;
  }
  if ( Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(a1) )
  {
    if ( *(_QWORD *)(a2 + 16) )
    {
      v8 = 2;
      if ( *(_QWORD *)(a5 + 40) )
        v8 = 4;
    }
    hKey = 0;
    Uint64Setting = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::GetUint64Setting(
                      v8,
                      a3,
                      a4,
                      (int)a5 + 24,
                      a2,
                      (__int64)&hKey);
    if ( Uint64Setting == -2147024894 )
      return 0;
    if ( Uint64Setting < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x25B,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)Uint64Setting,
        dwOptionsa);
    return (unsigned int)hKey;
  }
  else
  {
    LOBYTE(v35) = 0;
    Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&phkResult, a2);
    std::wstring::wstring(Buf2, a3);
    if ( *(_QWORD *)(a4 + 16) )
    {
      if ( v39 >= v40 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Buf2);
      }
      else
      {
        ++v39;
        v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Buf2);
        *(_DWORD *)(v11 + 2 * v12) = 92;
      }
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
      std::wstring::_Append<unsigned short>(Buf2, v13, *(_QWORD *)(a4 + 16));
    }
    v14 = a5 + 24;
    if ( *(_QWORD *)(a5 + 40) )
    {
      if ( v39 >= v40 )
      {
        std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Buf2);
      }
      else
      {
        ++v39;
        v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Buf2);
        *(_DWORD *)(v15 + 2 * v16) = 92;
      }
      v17 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v14);
      std::wstring::_Append<unsigned short>(Buf2, v17, *(_QWORD *)(a5 + 40));
    }
    *(_OWORD *)Buf1 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(Buf1[0]) = 0;
    AcquireSRWLockExclusive(&stru_180168B88);
    hKey = (HKEY)&stru_180168B88;
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Buf2);
    StringValue = Windows::Internal::CapabilityAccess::Private::RegGetStringValue(v44, phkResult, v18, L"Value", &v35);
    std::wstring::operator=(Buf1, StringValue);
    std::wstring::_Tidy_deallocate(v44);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&hKey);
    if ( !(_BYTE)v35 )
    {
      std::wstring::_Tidy_deallocate(Buf1);
      std::wstring::_Tidy_deallocate(Buf2);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
      return 0;
    }
    v21 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentValueFromString(Buf1);
    if ( !v21 )
    {
      Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DeleteConsent(v20, a2, a3, a4, v14);
      v21 = 0;
    }
    std::wstring::_Tidy_deallocate(Buf1);
    std::wstring::_Tidy_deallocate(Buf2);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    return v21;
  }
}

```

## disassembly

```asm
0x18004a788  push    rbp
0x18004a78a  push    rbx
0x18004a78b  push    rsi
0x18004a78c  push    rdi
0x18004a78d  push    r12
0x18004a78f  push    r14
0x18004a791  push    r15
0x18004a793  lea     rbp, [rsp-1Fh]
0x18004a798  sub     rsp, 0F0h
0x18004a79f  mov     rax, cs:__security_cookie
0x18004a7a6  xor     rax, rsp
0x18004a7a9  mov     [rbp+4Fh+var_38], rax
0x18004a7ad  mov     rsi, r9
0x18004a7b0  mov     r15, r8
0x18004a7b3  mov     r14, rdx
0x18004a7b6  mov     rbx, [rbp+4Fh+arg_20]
0x18004a7ba  xor     r12d, r12d
0x18004a7bd  lea     edi, [r12+1]
0x18004a7c2  cmp     [rbx+8], edi
0x18004a7c5  jnz     loc_18004A9E3
0x18004a7cb  call    ?IsPresent@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(void)
0x18004a7d0  test    al, al
0x18004a7d2  jz      short loc_18004A841
0x18004a7d4  cmp     [r14+10h], r12
0x18004a7d8  jz      short loc_18004A7EA
0x18004a7da  cmp     [rbx+28h], r12
0x18004a7de  lea     edi, [r12+2]
0x18004a7e3  jz      short loc_18004A7EA
0x18004a7e5  lea     edi, [r12+4]
0x18004a7ea  mov     [rbp+4Fh+hKey], r12
0x18004a7ee  lea     r9, [rbx+18h]
0x18004a7f2  lea     rax, [rbp+4Fh+hKey]
0x18004a7f6  mov     qword ptr [rsp+120h+samDesired], rax
0x18004a7fb  mov     qword ptr [rsp+120h+dwOptions], r14; int
0x18004a800  mov     r8, rsi
0x18004a803  mov     rdx, r15
0x18004a806  mov     ecx, edi
0x18004a808  call    ?GetUint64Setting@CAM@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJW4CAMStorageSettingType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111AEA_K@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::GetUint64Setting(CAMStorageSettingType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,unsigned __int64 &)
0x18004a80d  cmp     eax, 80070002h
0x18004a812  jnz     short loc_18004A834
0x18004a814  xor     eax, eax
0x18004a816  mov     rcx, [rbp+4Fh+var_38]
0x18004a81a  xor     rcx, rsp; StackCookie
0x18004a81d  call    __security_check_cookie
0x18004a822  add     rsp, 0F0h
0x18004a829  pop     r15
0x18004a82b  pop     r14
0x18004a82d  pop     r12
0x18004a82f  pop     rdi
0x18004a830  pop     rsi
0x18004a831  pop     rbx
0x18004a832  pop     rbp
0x18004a833  retn
0x18004a834  test    eax, eax
0x18004a836  js      loc_18004AC3E
0x18004a83c  mov     eax, dword ptr [rbp+4Fh+hKey]
0x18004a83f  jmp     short loc_18004A816
0x18004a841  mov     byte ptr [rsp+120h+var_D0], r12b
0x18004a846  mov     r8d, 20019h
0x18004a84c  mov     rdx, r14
0x18004a84f  lea     rcx, [rbp+4Fh+var_C8]
0x18004a853  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x18004a858  nop
0x18004a859  mov     rdx, r15
0x18004a85c  lea     rcx, [rbp+4Fh+Buf2]
0x18004a860  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004a865  nop
0x18004a866  mov     edi, 5Ch ; '\'
0x18004a86b  cmp     [rsi+10h], r12
0x18004a86f  jz      short loc_18004A8B1
0x18004a871  mov     rdx, [rbp+4Fh+var_A8]
0x18004a875  lea     rcx, [rbp+4Fh+Buf2]; Src
0x18004a879  cmp     rdx, [rbp+4Fh+var_A0]
0x18004a87d  jnb     short loc_18004A891
0x18004a87f  lea     rax, [rdx+1]
0x18004a883  mov     [rbp+4Fh+var_A8], rax
0x18004a887  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a88c  mov     [rax+rdx*2], edi
0x18004a88f  jmp     short loc_18004A899
0x18004a891  mov     r9d, edi
0x18004a894  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004a899  mov     rcx, rsi
0x18004a89c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a8a1  mov     r8, [rsi+10h]
0x18004a8a5  mov     rdx, rax
0x18004a8a8  lea     rcx, [rbp+4Fh+Buf2]
0x18004a8ac  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004a8b1  add     rbx, 18h
0x18004a8b5  cmp     [rbx+10h], r12
0x18004a8b9  jz      short loc_18004A8FB
0x18004a8bb  mov     rdx, [rbp+4Fh+var_A8]
0x18004a8bf  lea     rcx, [rbp+4Fh+Buf2]; Src
0x18004a8c3  cmp     rdx, [rbp+4Fh+var_A0]
0x18004a8c7  jnb     short loc_18004A8DB
0x18004a8c9  lea     rax, [rdx+1]
0x18004a8cd  mov     [rbp+4Fh+var_A8], rax
0x18004a8d1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a8d6  mov     [rax+rdx*2], edi
0x18004a8d9  jmp     short loc_18004A8E3
0x18004a8db  mov     r9d, edi
0x18004a8de  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18004a8e3  mov     rcx, rbx
0x18004a8e6  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a8eb  mov     r8, [rbx+10h]
0x18004a8ef  mov     rdx, rax
0x18004a8f2  lea     rcx, [rbp+4Fh+Buf2]
0x18004a8f6  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004a8fb  xorps   xmm0, xmm0
0x18004a8fe  movups  xmmword ptr [rbp+4Fh+Buf1], xmm0
0x18004a902  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18004a90a  movdqu  [rbp+4Fh+var_88], xmm1
0x18004a90f  mov     word ptr [rbp+4Fh+Buf1], r12w
0x18004a914  lea     rdi, stru_180168B88
0x18004a91b  mov     rcx, rdi; SRWLock
0x18004a91e  call    cs:__imp_AcquireSRWLockExclusive
0x18004a924  mov     [rbp+4Fh+hKey], rdi
0x18004a928  lea     rcx, [rbp+4Fh+Buf2]
0x18004a92c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004a931  mov     r8, rax
0x18004a934  lea     rax, [rsp+120h+var_D0]
0x18004a939  mov     qword ptr [rsp+120h+dwOptions], rax
0x18004a93e  lea     r9, ValueName; "Value"
0x18004a945  mov     rdx, [rbp+4Fh+var_C8]
0x18004a949  lea     rcx, [rbp+4Fh+var_58]
0x18004a94d  call    ?RegGetStringValue@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetStringValue(HKEY__ *,ushort const *,ushort const *,bool *)
0x18004a952  mov     rdx, rax
0x18004a955  lea     rcx, [rbp+4Fh+Buf1]
0x18004a959  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004a95e  lea     rcx, [rbp+4Fh+var_58]
0x18004a962  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a967  nop
0x18004a968  lea     rcx, [rbp+4Fh+hKey]
0x18004a96c  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18004a971  cmp     byte ptr [rsp+120h+var_D0], r12b
0x18004a976  jnz     short loc_18004A99A
0x18004a978  lea     rcx, [rbp+4Fh+Buf1]
0x18004a97c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a981  nop
0x18004a982  lea     rcx, [rbp+4Fh+Buf2]
0x18004a986  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a98b  nop
0x18004a98c  lea     rcx, [rbp+4Fh+var_C8]
0x18004a990  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a995  jmp     loc_18004A814
0x18004a99a  lea     rcx, [rbp+4Fh+Buf1]
0x18004a99e  call    ?CapabilityConsentValueFromString@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AW4CapabilityConsentValue@2345@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentValueFromString(std::wstring const &)
0x18004a9a3  mov     edi, eax
0x18004a9a5  test    eax, eax
0x18004a9a7  jnz     short loc_18004A9BF
0x18004a9a9  mov     qword ptr [rsp+120h+dwOptions], rbx
0x18004a9ae  mov     r9, rsi
0x18004a9b1  mov     r8, r15
0x18004a9b4  mov     rdx, r14
0x18004a9b7  call    ?DeleteConsent@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::DeleteConsent(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &)
0x18004a9bc  mov     edi, r12d
0x18004a9bf  lea     rcx, [rbp+4Fh+Buf1]
0x18004a9c3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a9c8  nop
0x18004a9c9  lea     rcx, [rbp+4Fh+Buf2]
0x18004a9cd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004a9d2  nop
0x18004a9d3  lea     rcx, [rbp+4Fh+var_C8]
0x18004a9d7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004a9dc  mov     eax, edi
0x18004a9de  jmp     loc_18004A816
0x18004a9e3  mov     r8d, 20019h
0x18004a9e9  lea     rcx, [rbp+4Fh+hKey]
0x18004a9ed  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x18004a9f2  nop
0x18004a9f3  mov     [rbp+4Fh+var_C8], r12
0x18004a9f7  mov     rdx, r15
0x18004a9fa  lea     rcx, [rbp+4Fh+var_78]
0x18004a9fe  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004aa03  nop
0x18004aa04  mov     r8, rdi
0x18004aa07  lea     rdx, asc_1800D35BC; "\\"
0x18004aa0e  lea     rcx, [rbp+4Fh+var_78]
0x18004aa12  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004aa17  cmp     dword ptr [rbx+8], 3
0x18004aa1b  jnz     short loc_18004AA2C
0x18004aa1d  lea     rdx, aUnsignedbinari; "UnsignedBinaries"
0x18004aa24  mov     r8d, 10h
0x18004aa2a  jmp     short loc_18004AA43
0x18004aa2c  cmp     dword ptr [rbx+8], 2
0x18004aa30  jnz     loc_18004AC1B
0x18004aa36  lea     rdx, aBinarieswithce; "BinariesWithCertificates"
0x18004aa3d  mov     r8d, 18h
0x18004aa43  lea     rcx, [rbp+4Fh+var_78]
0x18004aa47  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004aa4c  mov     r8, rdi
0x18004aa4f  lea     rdx, asc_1800D35BC; "\\"
0x18004aa56  lea     rcx, [rbp+4Fh+var_78]
0x18004aa5a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004aa5f  lea     rdx, [rbx+58h]
0x18004aa63  lea     rcx, [rbp+4Fh+var_58]
0x18004aa67  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004aa6c  nop
0x18004aa6d  lea     rcx, [rbp+4Fh+var_58]
0x18004aa71  call    ?RemoveBackslashes@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@CAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::RemoveBackslashes(std::wstring &)
0x18004aa76  lea     rcx, [rbp+4Fh+var_58]
0x18004aa7a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004aa7f  mov     rdx, rax
0x18004aa82  mov     r8, [rbp+4Fh+var_48]
0x18004aa86  lea     rcx, [rbp+4Fh+var_78]
0x18004aa8a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18004aa8f  xor     edx, edx
0x18004aa91  lea     rcx, [rbp+4Fh+var_C8]
0x18004aa95  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004aa9a  lea     rcx, [rbp+4Fh+var_78]
0x18004aa9e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004aaa3  mov     rdx, rax; lpSubKey
0x18004aaa6  mov     [rsp+120h+lpdwDisposition], r12; lpdwDisposition
0x18004aaab  lea     rax, [rbp+4Fh+var_C8]
0x18004aaaf  mov     [rsp+120h+phkResult], rax; phkResult
0x18004aab4  mov     [rsp+120h+lpSecurityAttributes], r12; lpSecurityAttributes
0x18004aab9  mov     [rsp+120h+samDesired], 0F013Fh; samDesired
0x18004aac1  mov     [rsp+120h+dwOptions], r12d; unsigned int
0x18004aac6  xor     r9d, r9d; lpClass
0x18004aac9  xor     r8d, r8d; Reserved
0x18004aacc  mov     rcx, [rbp+4Fh+hKey]; hKey
0x18004aad0  call    cs:__imp_RegCreateKeyExW
0x18004aad6  mov     rcx, [rbp+57h]; this
0x18004aada  test    eax, eax
0x18004aadc  jnz     loc_18004AC57
0x18004aae2  mov     byte ptr [rsp+120h+var_D0], r12b
0x18004aae7  cmp     dword ptr [rbx+8], 2
0x18004aaeb  jnz     loc_18004ABB5
0x18004aaf1  xorps   xmm0, xmm0
0x18004aaf4  movdqu  xmmword ptr [rbp+4Fh+Buf1], xmm0
0x18004aaf9  mov     qword ptr [rbp+4Fh+var_88], r12
0x18004aafd  lea     rdx, aHashvalue; "HashValue"
0x18004ab04  lea     rcx, [rbp+4Fh+Buf2]
0x18004ab08  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004ab0d  nop
0x18004ab0e  lea     r9, [rsp+120h+var_D0]
0x18004ab13  lea     r8, [rbp+4Fh+Buf1]
0x18004ab17  lea     rdx, [rbp+4Fh+Buf2]
0x18004ab1b  mov     rcx, [rbp+4Fh+var_C8]; hKey
0x18004ab1f  call    ?RegGetBinaryValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$vector@EV?$allocator@E@std@@@7@AEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetBinaryValue(HKEY__ *,std::wstring const &,std::vector<uchar> &,bool &)
0x18004ab24  nop
0x18004ab25  lea     rcx, [rbp+4Fh+Buf2]
0x18004ab29  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004ab2e  lea     rdx, [rbx+78h]
0x18004ab32  lea     rcx, [rbp+4Fh+Buf2]
0x18004ab36  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@AEBV01@@Z; std::vector<uchar>::vector<uchar>(std::vector<uchar> const &)
0x18004ab3b  mov     rcx, [rbp+4Fh+Buf1]; Buf1
0x18004ab3f  mov     r8, [rbp+4Fh+Buf1+8]
0x18004ab43  sub     r8, rcx; Size
0x18004ab46  mov     rdx, [rbp+4Fh+Buf2]; Buf2
0x18004ab4a  call    memcmp_0
0x18004ab4f  test    eax, eax
0x18004ab51  setnz   bl
0x18004ab54  lea     rcx, [rbp+4Fh+Buf2]
0x18004ab58  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004ab5d  test    bl, bl
0x18004ab5f  jz      short loc_18004ABAC
0x18004ab61  lea     rdx, aHashvalue; "HashValue"
0x18004ab68  mov     rcx, [rbp+4Fh+var_C8]; hKey
0x18004ab6c  call    cs:__imp_RegDeleteValueW
0x18004ab72  cmp     eax, 2
0x18004ab75  jz      short loc_18004AB83
0x18004ab77  mov     rcx, [rbp+57h]; this
0x18004ab7b  test    eax, eax
0x18004ab7d  jnz     loc_18004AC6C
0x18004ab83  lea     rdx, ValueName; "Value"
0x18004ab8a  mov     rcx, [rbp+4Fh+var_C8]; hKey
0x18004ab8e  call    cs:__imp_RegDeleteValueW
0x18004ab94  cmp     eax, 2
0x18004ab97  jz      short loc_18004ABA1
0x18004ab99  mov     rcx, [rbp+57h]; this
0x18004ab9d  test    eax, eax
0x18004ab9f  jnz     short loc_18004AC06
0x18004aba1  lea     rcx, [rbp+4Fh+Buf1]
0x18004aba5  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004abaa  jmp     short loc_18004ABD5
0x18004abac  lea     rcx, [rbp+4Fh+Buf1]
0x18004abb0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18004abb5  lea     r9, [rsp+120h+var_D0]; unsigned __int16 *
0x18004abba  lea     r8, ValueName; "Value"
0x18004abc1  xor     edx, edx; HKEY
0x18004abc3  mov     rcx, [rbp+4Fh+var_C8]; this
0x18004abc7  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18004abcc  mov     ebx, eax
0x18004abce  cmp     byte ptr [rsp+120h+var_D0], r12b
0x18004abd3  jnz     short loc_18004ABD8
0x18004abd5  mov     ebx, r12d
0x18004abd8  lea     rcx, [rbp+4Fh+var_58]
0x18004abdc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004abe1  nop
0x18004abe2  lea     rcx, [rbp+4Fh+var_78]
0x18004abe6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004abeb  nop
0x18004abec  lea     rcx, [rbp+4Fh+var_C8]
0x18004abf0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004abf5  nop
0x18004abf6  lea     rcx, [rbp+4Fh+hKey]
0x18004abfa  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18004abff  mov     eax, ebx
0x18004ac01  jmp     loc_18004A816
0x18004ac06  mov     r9d, eax; char *
  ... truncated ...
```
