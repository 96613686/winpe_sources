# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetConsent(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)

- ea: `0x180050158`
- end: `0x18005046f`
- name: `?SetConsent@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@AEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@000W4CapabilityConsentValue@2345@@Z`
- size: `791`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180050fc4`
- `0x180051240`
- `0x1800513bc`

## callees

- `0x1800094c0`
- `0x180016d54`
- `0x18001c3b4`
- `0x18001fd3c`
- `0x18002392c`
- `0x1800257a4`
- `0x180029408`
- `0x1800299c4`
- `0x18002a564`
- `0x18002f280`
- `0x18003b54c`
- `0x18003ce34`
- `0x180043224`
- `0x1800473fc`
- `0x1800492e8`
- `0x18004e9ec`
- `0x180050158`
- `0x18005258c`
- `0x180058f58`
- `0x180059008`
- `0x18009f9d4`
- `0x18009fc34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050327`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180050327`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005030b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18005030b`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetConsent(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 v8; // rsi
  char v9; // r15
  Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers *v10; // rcx
  int v11; // ecx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  __int64 v21; // rax
  Windows::Internal::CapabilityAccess::Private *v22; // rcx
  const unsigned __int16 *SystemTimeAsUInt64; // rax
  __int64 v24; // rdi
  const wchar_t *v25; // rbx
  __int64 v26; // rax
  int dwOptions; // [rsp+20h] [rbp-79h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-79h]
  HKEY phkResult; // [rsp+50h] [rbp-49h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-41h] BYREF
  RTL_SRWLOCK *v32; // [rsp+60h] [rbp-39h] BYREF
  _BYTE Src[16]; // [rsp+68h] [rbp-31h] BYREF
  unsigned __int64 v34; // [rsp+78h] [rbp-21h]
  unsigned __int64 v35; // [rsp+80h] [rbp-19h]
  _BYTE v36[32]; // [rsp+88h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v8 = a2;
  v9 = 0;
  LODWORD(phkResult) = 0;
  LOBYTE(a2) = 1;
  wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(
    `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl'::`2'::impl,
    a2);
  if ( Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(v10) )
  {
    if ( *(_QWORD *)(v8 + 16) )
      v11 = *(_QWORD *)(a5 + 16) ? ((unsigned int)std::wstring::compare(a5, L"NonPackaged") != 0) + 3 : 2;
    else
      v11 = 1;
    v12 = Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::PutUint64Setting(
            v11,
            a3,
            a4,
            a5,
            v8,
            a6);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x580,
        (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
        (const char *)(unsigned int)v12,
        dwOptions);
  }
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, v8, 983103);
  std::wstring::wstring(Src, a3);
  if ( *(_QWORD *)(a4 + 16) )
  {
    if ( v34 >= v35 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v34;
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v13 + 2 * v14) = 92;
    }
    v15 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a4);
    std::wstring::_Append<unsigned short>(Src, v15);
  }
  if ( *(_QWORD *)(a5 + 16) )
  {
    if ( v34 >= v35 )
    {
      std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,unsigned short>(Src);
    }
    else
    {
      ++v34;
      v16 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
      *(_DWORD *)(v16 + 2 * v17) = 92;
    }
    v18 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a5);
    std::wstring::_Append<unsigned short>(Src, v18);
  }
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v20 = RegCreateKeyExW(hKey, v19, 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
  if ( v20 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x5A4,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v20,
      dwOptionsa);
  AcquireSRWLockExclusive(&stru_180168B88);
  v32 = &stru_180168B88;
  v21 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(v36, a6);
  Windows::Internal::CapabilityAccess::Private::RegSetStringValue((__int64)phkResult, (__int64)L"Value", v21);
  std::wstring::_Tidy_deallocate(v36);
  SystemTimeAsUInt64 = (const unsigned __int16 *)Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(v22);
  Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(
    (Windows::Internal::CapabilityAccess::Private *)phkResult,
    L"LastSetTime",
    SystemTimeAsUInt64);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
    v25 = L"system";
    if ( *(_QWORD *)(v8 + 16) )
      v25 = (const wchar_t *)L"user";
    v26 = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(
            v36,
            a6);
    v9 = 1;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    WPP_SF_SSS(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v25, v24);
  }
  if ( (v9 & 1) != 0 )
    std::wstring::_Tidy_deallocate(v36);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v32);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  std::wstring::_Tidy_deallocate(Src);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x180050158  push    rbp
0x18005015a  push    rbx
0x18005015b  push    rsi
0x18005015c  push    rdi
0x18005015d  push    r12
0x18005015f  push    r14
0x180050161  push    r15
0x180050163  lea     rbp, [rsp-17h]
0x180050168  sub     rsp, 0B0h
0x18005016f  mov     rax, cs:__security_cookie
0x180050176  xor     rax, rsp
0x180050179  mov     [rbp+47h+var_38], rax
0x18005017d  mov     rdi, r9
0x180050180  mov     r14, r8
0x180050183  mov     rsi, rdx
0x180050186  mov     rbx, [rbp+47h+arg_20]
0x18005018a  mov     r12d, [rbp+47h+arg_28]
0x18005018e  xor     r15d, r15d
0x180050191  mov     dword ptr [rbp+47h+var_90], r15d
0x180050195  mov     dl, 1
0x180050197  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase> `wil::Feature<__WilFeatureTraits_Feature_CAMStorageDatabase>::GetImpl(void)'::`2'::impl
0x18005019e  call    ?ReportUsage@?$FeatureImpl@U__WilFeatureTraits_Feature_CAMStorageDatabase@@@details@wil@@QEAAX_NW4ReportingKind@3@_K@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CAMStorageDatabase>::ReportUsage(bool,wil::ReportingKind,unsigned __int64)
0x1800501a3  call    ?IsPresent@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::IsPresent(void)
0x1800501a8  test    al, al
0x1800501aa  jz      short loc_180050201
0x1800501ac  cmp     [rsi+10h], r15
0x1800501b0  jnz     short loc_1800501B8
0x1800501b2  lea     ecx, [r15+1]
0x1800501b6  jmp     short loc_1800501DD
0x1800501b8  cmp     [rbx+10h], r15
0x1800501bc  jnz     short loc_1800501C5
0x1800501be  mov     ecx, 2
0x1800501c3  jmp     short loc_1800501DD
0x1800501c5  lea     rdx, aNonpackaged; "NonPackaged"
0x1800501cc  mov     rcx, rbx
0x1800501cf  call    ?compare@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAHQEBG@Z; std::wstring::compare(ushort const * const)
0x1800501d4  neg     eax
0x1800501d6  sbb     ecx, ecx
0x1800501d8  neg     ecx
0x1800501da  add     ecx, 3
0x1800501dd  mov     qword ptr [rsp+0E0h+samDesired], r12
0x1800501e2  mov     qword ptr [rsp+0E0h+dwOptions], rsi; int
0x1800501e7  mov     r9, rbx
0x1800501ea  mov     r8, rdi
0x1800501ed  mov     rdx, r14
0x1800501f0  call    ?PutUint64Setting@CAM@APIWrappers@Storage@Extensions@CapabilityAccess@Internal@Windows@@YAJW4CAMStorageSettingType@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@111_K@Z; Windows::Internal::CapabilityAccess::Extensions::Storage::APIWrappers::CAM::PutUint64Setting(CAMStorageSettingType,std::wstring const &,std::wstring const &,std::wstring const &,std::wstring const &,unsigned __int64)
0x1800501f5  mov     rcx, [rbp+4Fh]; this
0x1800501f9  test    eax, eax
0x1800501fb  js      loc_18005045A
0x180050201  mov     r8d, 0F003Fh
0x180050207  mov     rdx, rsi
0x18005020a  lea     rcx, [rbp+47h+hKey]
0x18005020e  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x180050213  nop
0x180050214  mov     rdx, r14
0x180050217  lea     rcx, [rbp+47h+Src]
0x18005021b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180050220  nop
0x180050221  mov     r14d, 5Ch ; '\'
0x180050227  cmp     qword ptr [rdi+10h], 0
0x18005022c  jz      short loc_18005026F
0x18005022e  mov     rdx, [rbp+47h+var_68]
0x180050232  lea     rcx, [rbp+47h+Src]; Src
0x180050236  cmp     rdx, [rbp+47h+var_60]
0x18005023a  jnb     short loc_18005024F
0x18005023c  lea     rax, [rdx+1]
0x180050240  mov     [rbp+47h+var_68], rax
0x180050244  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050249  mov     [rax+rdx*2], r14d
0x18005024d  jmp     short loc_180050257
0x18005024f  mov     r9d, r14d
0x180050252  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x180050257  mov     rcx, rdi
0x18005025a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005025f  mov     r8, [rdi+10h]
0x180050263  mov     rdx, rax
0x180050266  lea     rcx, [rbp+47h+Src]
0x18005026a  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18005026f  cmp     qword ptr [rbx+10h], 0
0x180050274  jz      short loc_1800502B7
0x180050276  mov     rdx, [rbp+47h+var_68]
0x18005027a  lea     rcx, [rbp+47h+Src]; Src
0x18005027e  cmp     rdx, [rbp+47h+var_60]
0x180050282  jnb     short loc_180050297
0x180050284  lea     rax, [rdx+1]
0x180050288  mov     [rbp+47h+var_68], rax
0x18005028c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050291  mov     [rax+rdx*2], r14d
0x180050295  jmp     short loc_18005029F
0x180050297  mov     r9d, r14d
0x18005029a  call    ??$_Reallocate_grow_by@V_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3fdb14453883e86a37ebade6a7a0ebb0_@@G@Z; std::wstring::_Reallocate_grow_by<_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort>(unsigned __int64,_lambda_3fdb14453883e86a37ebade6a7a0ebb0_,ushort)
0x18005029f  mov     rcx, rbx
0x1800502a2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800502a7  mov     r8, [rbx+10h]
0x1800502ab  mov     rdx, rax
0x1800502ae  lea     rcx, [rbp+47h+Src]
0x1800502b2  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x1800502b7  mov     [rbp+47h+var_90], 0
0x1800502bf  xor     edx, edx
0x1800502c1  lea     rcx, [rbp+47h+var_90]
0x1800502c5  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800502ca  lea     rcx, [rbp+47h+Src]
0x1800502ce  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800502d3  mov     rdx, rax; lpSubKey
0x1800502d6  mov     [rsp+0E0h+lpdwDisposition], 0; lpdwDisposition
0x1800502df  lea     rax, [rbp+47h+var_90]
0x1800502e3  mov     [rsp+0E0h+phkResult], rax; phkResult
0x1800502e8  mov     [rsp+0E0h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800502f1  mov     [rsp+0E0h+samDesired], 0F013Fh; samDesired
0x1800502f9  mov     [rsp+0E0h+dwOptions], 0; unsigned int
0x180050301  xor     r9d, r9d; lpClass
0x180050304  xor     r8d, r8d; Reserved
0x180050307  mov     rcx, [rbp+47h+hKey]; hKey
0x18005030b  call    cs:__imp_RegCreateKeyExW
0x180050311  mov     rcx, [rbp+4Fh]; this
0x180050315  test    eax, eax
0x180050317  jnz     loc_180050445
0x18005031d  lea     rbx, stru_180168B88
0x180050324  mov     rcx, rbx; SRWLock
0x180050327  call    cs:__imp_AcquireSRWLockExclusive
0x18005032d  mov     [rbp+47h+var_80], rbx
0x180050331  mov     edx, r12d
0x180050334  lea     rcx, [rbp+47h+var_58]
0x180050338  call    ?CapabilityConsentStringFromValue@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CapabilityConsentValue@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x18005033d  nop
0x18005033e  mov     r8, rax
0x180050341  lea     rdx, ValueName; "Value"
0x180050348  mov     rcx, [rbp+47h+var_90]
0x18005034c  call    ?RegSetStringValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::RegSetStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x180050351  nop
0x180050352  lea     rcx, [rbp+47h+var_58]
0x180050356  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005035b  call    ?GetSystemTimeAsUInt64@Private@CapabilityAccess@Internal@Windows@@YA_KXZ; Windows::Internal::CapabilityAccess::Private::GetSystemTimeAsUInt64(void)
0x180050360  mov     r8, rax; unsigned __int16 *
0x180050363  lea     rdx, aLastsettime; "LastSetTime"
0x18005036a  mov     rcx, [rbp+47h+var_90]; this
0x18005036e  call    ?RegSetUint64Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBG_K@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(HKEY__ *,ushort const *,unsigned __int64)
0x180050373  lea     rcx, WPP_GLOBAL_Control
0x18005037a  mov     rax, cs:WPP_GLOBAL_Control
0x180050381  cmp     rax, rcx
0x180050384  jz      short loc_1800503F0
0x180050386  test    byte ptr [rax+1Ch], 1
0x18005038a  jz      short loc_1800503F0
0x18005038c  cmp     byte ptr [rax+19h], 4
0x180050390  jb      short loc_1800503F0
0x180050392  lea     rcx, [rbp+47h+Src]
0x180050396  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005039b  mov     rdi, rax
0x18005039e  lea     rax, aUser; "user"
0x1800503a5  lea     rbx, aSystem; "system"
0x1800503ac  cmp     qword ptr [rsi+10h], 0
0x1800503b1  cmovnz  rbx, rax
0x1800503b5  mov     edx, r12d
0x1800503b8  lea     rcx, [rbp+47h+var_58]
0x1800503bc  call    ?CapabilityConsentStringFromValue@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4CapabilityConsentValue@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::CapabilityConsentStringFromValue(Windows::Internal::CapabilityAccess::Private::CapabilityConsentValue)
0x1800503c1  mov     r15d, 1
0x1800503c7  mov     rcx, rax
0x1800503ca  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800503cf  lea     edx, [r15+0Bh]
0x1800503d3  mov     qword ptr [rsp+0E0h+samDesired], rdi; __int64
0x1800503d8  mov     qword ptr [rsp+0E0h+dwOptions], rbx; __int64
0x1800503dd  mov     r9, rax
0x1800503e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800503e7  mov     rcx, [rcx+10h]; LoggerHandle
0x1800503eb  call    WPP_SF_SSS
0x1800503f0  test    r15b, 1
0x1800503f4  jz      short loc_180050400
0x1800503f6  lea     rcx, [rbp+47h+var_58]
0x1800503fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800503ff  nop
0x180050400  lea     rcx, [rbp+47h+var_80]
0x180050404  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180050409  nop
0x18005040a  lea     rcx, [rbp+47h+var_90]
0x18005040e  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050413  nop
0x180050414  lea     rcx, [rbp+47h+Src]
0x180050418  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005041d  nop
0x18005041e  lea     rcx, [rbp+47h+hKey]
0x180050422  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050427  mov     rcx, [rbp+47h+var_38]
0x18005042b  xor     rcx, rsp; StackCookie
0x18005042e  call    __security_check_cookie
0x180050433  add     rsp, 0B0h
0x18005043a  pop     r15
0x18005043c  pop     r14
0x18005043e  pop     r12
0x180050440  pop     rdi
0x180050441  pop     rsi
0x180050442  pop     rbx
0x180050443  pop     rbp
0x180050444  retn
0x180050445  mov     r9d, eax; char *
0x180050448  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x18005044f  mov     edx, 5A4h; void *
0x180050454  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18005045a  mov     r9d, eax; char *
0x18005045d  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180050464  mov     edx, 580h; void *
0x180050469  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
