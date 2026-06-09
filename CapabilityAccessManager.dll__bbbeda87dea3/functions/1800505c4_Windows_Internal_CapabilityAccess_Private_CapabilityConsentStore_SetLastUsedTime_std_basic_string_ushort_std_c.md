# Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Windows::Internal::CapabilityAccess::Private::AppIdType,Windows::Internal::CapabilityAccess::Private::CapabilityUsageTimestampType,unsigned __int64,ulong,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800505c4`
- end: `0x180050be8`
- name: `?SetLastUsedTime@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@W4CapabilityUsageTimestampType@2345@_KK0@Z`
- size: `1572`
- prototype: ``
- caller_count: `4`
- callee_count: `31`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18004f7d4`
- `0x180061058`
- `0x180061318`
- `0x1800901e0`

## callees

- `0x1800094c0`
- `0x180016d54`
- `0x18001c3b4`
- `0x18001f4c0`
- `0x180020fcc`
- `0x18002392c`
- `0x1800257a4`
- `0x180025b6c`
- `0x180029408`
- `0x18002949c`
- `0x1800299c4`
- `0x18002f280`
- `0x18002f93c`
- `0x1800382b8`
- `0x180039a1c`
- `0x18003ce34`
- `0x1800401f0`
- `0x1800468b4`
- `0x180047bc0`
- `0x180047e40`
- `0x18004a2cc`
- `0x18004aff8`
- `0x18004b30c`
- `0x18004e9ec`
- `0x1800505c4`
- `0x180056a64`
- `0x180058dfc`
- `0x180058e78`
- `0x180058f58`
- `0x180058fb8`
- `0x180059008`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180050a7b`
- `api-ms-win-core-synch-l1-1-0!TryAcquireSRWLockExclusive` at `0x180050a7b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800506ca`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x1800506ca`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050a32`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180050a32`

## string_xrefs

- `0x180050a51`: `LastAccessGUID`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::SetLastUsedTime(
        __int64 a1,
        std::_Ref_count_base *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int16 *a6,
        unsigned __int16 *a7,
        int a8,
        unsigned __int64 a9)
{
  __int64 v9; // rsi
  __int64 v10; // rdi
  int v11; // r14d
  int v12; // r12d
  const WCHAR *v13; // rax
  unsigned int v14; // eax
  unsigned __int64 v15; // r9
  HKEY v16; // rdx
  Windows::Internal::CapabilityAccess::Private::SQL *v17; // rcx
  unsigned int v18; // r9d
  unsigned __int64 Uint64Value; // r15
  unsigned __int64 v20; // rax
  int v21; // ecx
  char v22; // r13
  __int64 LastAccessGUID; // rax
  int v24; // ecx
  __int64 v25; // rax
  int v26; // r15d
  unsigned int v27; // r9d
  __int64 v28; // rax
  BOOLEAN v29; // al
  __int64 v30; // rdx
  const char *v31; // r9
  int dwOptions; // [rsp+20h] [rbp-228h]
  bool *dwOptionsa; // [rsp+20h] [rbp-228h]
  bool *dwOptionsb; // [rsp+20h] [rbp-228h]
  bool *dwOptionsc; // [rsp+20h] [rbp-228h]
  char dwOptionsd; // [rsp+20h] [rbp-228h]
  unsigned __int16 v38; // [rsp+70h] [rbp-1D8h] BYREF
  HKEY phkResult; // [rsp+78h] [rbp-1D0h] BYREF
  int v40; // [rsp+80h] [rbp-1C8h]
  int LastUserAnnotatedLabel; // [rsp+84h] [rbp-1C4h]
  int v42; // [rsp+88h] [rbp-1C0h] BYREF
  unsigned __int64 v43; // [rsp+90h] [rbp-1B8h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-1B0h] BYREF
  __int64 v45; // [rsp+A0h] [rbp-1A8h] BYREF
  std::_Ref_count_base *v46; // [rsp+A8h] [rbp-1A0h]
  _QWORD v47[2]; // [rsp+B0h] [rbp-198h] BYREF
  unsigned __int64 v48; // [rsp+C0h] [rbp-188h]
  std::_Ref_count_base *v49[2]; // [rsp+C8h] [rbp-180h] BYREF
  __m128i si128; // [rsp+D8h] [rbp-170h]
  GUID pguid; // [rsp+E8h] [rbp-160h] BYREF
  __m128i v52; // [rsp+F8h] [rbp-150h]
  _OWORD v53[2]; // [rsp+108h] [rbp-140h] BYREF
  int v54[8]; // [rsp+128h] [rbp-120h] BYREF
  _BYTE Src[40]; // [rsp+148h] [rbp-100h] BYREF
  _BYTE v56[144]; // [rsp+170h] [rbp-D8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+248h] [rbp+0h]

  v9 = a4;
  v10 = a3;
  v11 = (int)a2;
  v49[0] = a2;
  *(_QWORD *)&pguid.Data1 = a3;
  v45 = a4;
  v12 = a5;
  v42 = a5;
  v43 = a9;
  if ( !*(_QWORD *)(a3 + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67B,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  if ( !*(_QWORD *)(a4 + 16) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x67C,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)0x80070057LL,
      dwOptions);
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(&hKey, a2, 983103);
  Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GenerateSubKeyPathForAppByType(Src);
  phkResult = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &phkResult,
    0);
  v13 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(Src);
  v14 = RegCreateKeyExW(hKey, v13, 0, 0, 0, 0xF013Fu, 0, &phkResult, 0);
  if ( v14 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x692,
      (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
      (const char *)v14,
      (unsigned int)dwOptionsa);
  v16 = (HKEY)L"LastUsedTimeStart";
  if ( (_DWORD)a6 )
    v16 = (HKEY)&stru_1800DA360;
  Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(
    (Windows::Internal::CapabilityAccess::Private *)phkResult,
    v16,
    a7,
    v15);
  if ( Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(v17) )
  {
    if ( (_DWORD)a6 == 1 )
    {
      if ( a7 )
        Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
          (Windows::Internal::CapabilityAccess::Private *)phkResult,
          (HKEY)&stru_1800DB268,
          (const unsigned __int16 *)1,
          v18);
      goto LABEL_31;
    }
    if ( (_DWORD)a6 )
      goto LABEL_31;
    LOBYTE(v38) = 0;
    Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(
      (Windows::Internal::CapabilityAccess::Private *)phkResult,
      0,
      (const unsigned __int16 *)&stru_1800DB268,
      &v38,
      dwOptionsa);
    if ( !(_BYTE)v38 )
    {
      v38 = 0;
      Uint64Value = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(
                      (Windows::Internal::CapabilityAccess::Private *)phkResult,
                      0,
                      L"LastUsedTimeStart",
                      (unsigned __int16 *)((char *)&v38 + 1),
                      dwOptionsb);
      v48 = Uint64Value;
      v20 = Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(
              (Windows::Internal::CapabilityAccess::Private *)phkResult,
              0,
              (const unsigned __int16 *)&stru_1800DA360,
              &v38,
              dwOptionsc);
      v22 = v20;
      v47[0] = v20;
      if ( (_BYTE)v38 )
      {
        if ( HIBYTE(v38) && Uint64Value && v20 )
        {
          v53[0] = 0;
          v53[1] = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v53[0]) = 0;
          v40 = 0;
          try
          {
            LastAccessGUID = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetLastAccessGUID(
                               v21,
                               (unsigned int)v54,
                               v11,
                               v10,
                               v9,
                               a5);
            std::wstring::operator=(v53, LastAccessGUID);
            std::wstring::_Tidy_deallocate(v54);
            LastUserAnnotatedLabel = Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetLastUserAnnotatedLabel(
                                       v24,
                                       v11,
                                       v10,
                                       v9,
                                       a5);
            v40 = LastUserAnnotatedLabel;
          }
          catch ( ... )
          {
            LastUserAnnotatedLabel = v40;
            LOBYTE(Uint64Value) = v48;
            v22 = v47[0];
            v11 = (int)v49[0];
            v10 = *(_QWORD *)&pguid.Data1;
            v9 = v45;
            v12 = v42;
          }
          *(_OWORD *)v49 = 0;
          si128 = _mm_load_si128((const __m128i *)&_xmm);
          LOWORD(v49[0]) = 0;
          pguid = 0;
          v52 = si128;
          LOWORD(pguid.Data1) = 0;
          v25 = std::wstring::wstring(v54, v53);
          dwOptionsd = Uint64Value;
          v26 = a8;
          Windows::Internal::CapabilityAccess::Private::SQL::RecordUsage(
            v11,
            v10,
            a8,
            v9,
            dwOptionsd,
            v22,
            v12,
            v25,
            LastUserAnnotatedLabel,
            v43,
            0,
            (unsigned int)&pguid,
            (unsigned int)v49,
            0);
          std::wstring::_Tidy_deallocate(&pguid);
          std::wstring::_Tidy_deallocate(v49);
          Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
            (Windows::Internal::CapabilityAccess::Private *)phkResult,
            (HKEY)&stru_1800DB268,
            (const unsigned __int16 *)1,
            v27);
          std::wstring::_Tidy_deallocate(v53);
          goto LABEL_20;
        }
      }
    }
  }
  else if ( (_DWORD)a6 )
  {
    goto LABEL_31;
  }
  v26 = a8;
LABEL_20:
  if ( v26 )
  {
    Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(
      (Windows::Internal::CapabilityAccess::Private *)phkResult,
      (HKEY)&stru_1800DB290,
      (const unsigned __int16 *)2,
      v18);
    Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(v49);
    Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(v49[0], &v45, v10);
    if ( v45 && *(_BYTE *)(v45 + 61) )
    {
      pguid = 0;
      CoCreateGuid(&pguid);
      v28 = Windows::Internal::CapabilityAccess::Private::GUIDToString((int)v54, &pguid);
      Windows::Internal::CapabilityAccess::Private::RegSetStringValue(phkResult, L"LastAccessGUID", v28);
      std::wstring::_Tidy_deallocate(v54);
      v29 = TryAcquireSRWLockExclusive(&Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_tryToastLock);
      try
      {
        v43 = (unsigned __int64)&Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_tryToastLock
            & -(__int64)(v29 != 0);
        if ( v43 )
        {
          v30 = lambda_6ac006fb6aed2ed0911b9dc4b09ff962_::_lambda_6ac006fb6aed2ed0911b9dc4b09ff962_(
                  (unsigned int)v56,
                  v11,
                  v10,
                  (unsigned int)&v45,
                  v9,
                  (__int64)&v42,
                  (__int64)&a8,
                  (__int64)&pguid,
                  (__int64)&v43);
          std::thread::thread__lambda_6ac006fb6aed2ed0911b9dc4b09ff962__0_(v47, v30);
          lambda_6ac006fb6aed2ed0911b9dc4b09ff962_::__lambda_6ac006fb6aed2ed0911b9dc4b09ff962_(v56);
          std::thread::detach((std::thread *)v47);
          std::thread::~thread((std::thread *)v47);
        }
        wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v43);
      }
      catch ( ... )
      {
        wil::details::in1diag3::Log_CaughtException(
          retaddr,
          (void *)0x753,
          (unsigned int)"onecore\\base\\devices\\cam\\core\\capabilityconsentstore.cpp",
          v31);
      }
    }
    if ( v46 )
      std::_Ref_count_base::_Decref(v46);
    if ( v49[1] )
      std::_Ref_count_base::_Decref(v49[1]);
  }
LABEL_31:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  std::wstring::_Tidy_deallocate(Src);
  return wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
}

```

## disassembly

```asm
0x1800505c4  push    rbx
0x1800505c6  push    rsi
0x1800505c7  push    rdi
0x1800505c8  push    r12
0x1800505ca  push    r13
0x1800505cc  push    r14
0x1800505ce  push    r15
0x1800505d0  sub     rsp, 210h
0x1800505d7  mov     rax, cs:__security_cookie
0x1800505de  xor     rax, rsp
0x1800505e1  mov     [rsp+248h+var_48], rax
0x1800505e9  mov     rsi, r9
0x1800505ec  mov     rdi, r8
0x1800505ef  mov     r14, rdx
0x1800505f2  mov     [rsp+248h+var_180], rdx
0x1800505fa  mov     qword ptr [rsp+248h+pguid.Data1], r8
0x180050602  mov     [rsp+248h+var_1A8], r9
0x18005060a  mov     r12d, [rsp+248h+arg_20]
0x180050612  mov     [rsp+248h+var_1C0], r12d
0x18005061a  mov     rax, [rsp+248h+arg_40]
0x180050622  mov     [rsp+248h+var_1B8], rax
0x18005062a  mov     rcx, [rsp+248h]; this
0x180050632  xor     ebx, ebx
0x180050634  cmp     [r8+10h], rbx
0x180050638  jz      loc_180050BA3
0x18005063e  mov     rcx, [rsp+248h]; this
0x180050646  cmp     [r9+10h], rbx
0x18005064a  jz      loc_180050BBB
0x180050650  mov     r8d, 0F003Fh
0x180050656  lea     rcx, [rsp+248h+hKey]
0x18005065e  call    ?OpenConsentStoreKeyForUser@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@K@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::OpenConsentStoreKeyForUser(std::wstring const &,ulong)
0x180050663  nop
0x180050664  mov     r9d, r12d
0x180050667  mov     r8, rsi
0x18005066a  mov     rdx, rdi
0x18005066d  lea     rcx, [rsp+248h+Src]; Src
0x180050675  call    ?GenerateSubKeyPathForAppByType@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@0W4AppIdType@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GenerateSubKeyPathForAppByType(std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType)
0x18005067a  nop
0x18005067b  mov     [rsp+248h+var_1D0], rbx
0x180050680  xor     edx, edx
0x180050682  lea     rcx, [rsp+248h+var_1D0]
0x180050687  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18005068c  lea     rcx, [rsp+248h+Src]
0x180050694  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180050699  mov     rdx, rax; lpSubKey
0x18005069c  mov     [rsp+248h+lpdwDisposition], rbx; lpdwDisposition
0x1800506a1  lea     rax, [rsp+248h+var_1D0]
0x1800506a6  mov     [rsp+248h+phkResult], rax; phkResult
0x1800506ab  mov     [rsp+248h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x1800506b0  mov     [rsp+248h+samDesired], 0F013Fh; samDesired
0x1800506b8  mov     [rsp+248h+dwOptions], ebx; unsigned int
0x1800506bc  xor     r9d, r9d; lpClass
0x1800506bf  xor     r8d, r8d; Reserved
0x1800506c2  mov     rcx, [rsp+248h+hKey]; hKey
0x1800506ca  call    cs:__imp_RegCreateKeyExW
0x1800506d0  mov     rcx, [rsp+248h]; this
0x1800506d8  test    eax, eax
0x1800506da  jnz     loc_180050BD3
0x1800506e0  mov     r15d, dword ptr [rsp+248h+arg_28]
0x1800506e8  lea     r13, stru_1800DA360
0x1800506ef  lea     rdx, aLastusedtimest; "LastUsedTimeStart"
0x1800506f6  test    r15d, r15d
0x1800506f9  cmovnz  rdx, r13; HKEY
0x1800506fd  mov     r8, [rsp+248h+arg_30]; unsigned __int16 *
0x180050705  mov     rcx, [rsp+248h+var_1D0]; this
0x18005070a  call    ?RegSetUint64Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBG_K@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint64Value(HKEY__ *,ushort const *,unsigned __int64)
0x18005070f  call    ?ShouldUsageDataBeCollected@SQL@Private@CapabilityAccess@Internal@Windows@@YA_NXZ; Windows::Internal::CapabilityAccess::Private::SQL::ShouldUsageDataBeCollected(void)
0x180050714  test    al, al
0x180050716  jz      loc_1800509AD
0x18005071c  cmp     r15d, 1
0x180050720  jnz     short loc_180050749
0x180050722  cmp     [rsp+248h+arg_30], rbx
0x18005072a  jz      loc_180050B5A
0x180050730  mov     r8d, r15d; unsigned __int16 *
0x180050733  lea     rdx, stru_1800DB268; HKEY
0x18005073a  mov     rcx, [rsp+248h+var_1D0]; this
0x18005073f  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x180050744  jmp     loc_180050B5A
0x180050749  test    r15d, r15d
0x18005074c  jnz     loc_180050B5A
0x180050752  mov     byte ptr [rsp+248h+var_1D8], bl
0x180050756  lea     r9, [rsp+248h+var_1D8]; unsigned __int16 *
0x18005075b  lea     r8, stru_1800DB268; unsigned __int16 *
0x180050762  xor     edx, edx; HKEY
0x180050764  mov     rcx, [rsp+248h+var_1D0]; this
0x180050769  call    ?RegGetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAIPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint32Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x18005076e  cmp     byte ptr [rsp+248h+var_1D8], bl
0x180050772  jnz     loc_1800509B6
0x180050778  mov     byte ptr [rsp+248h+var_1D8+1], bl
0x18005077c  mov     byte ptr [rsp+248h+var_1D8], bl
0x180050780  lea     r9, [rsp+248h+var_1D8+1]; unsigned __int16 *
0x180050785  lea     r8, aLastusedtimest; "LastUsedTimeStart"
0x18005078c  xor     edx, edx; HKEY
0x18005078e  mov     rcx, [rsp+248h+var_1D0]; this
0x180050793  call    ?RegGetUint64Value@Private@CapabilityAccess@Internal@Windows@@YA_KPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x180050798  mov     r15, rax
0x18005079b  mov     [rsp+248h+var_188], rax
0x1800507a3  lea     r9, [rsp+248h+var_1D8]; unsigned __int16 *
0x1800507a8  mov     r8, r13; unsigned __int16 *
0x1800507ab  xor     edx, edx; HKEY
0x1800507ad  mov     rcx, [rsp+248h+var_1D0]; this
0x1800507b2  call    ?RegGetUint64Value@Private@CapabilityAccess@Internal@Windows@@YA_KPEAUHKEY__@@PEBG1PEA_N@Z; Windows::Internal::CapabilityAccess::Private::RegGetUint64Value(HKEY__ *,ushort const *,ushort const *,bool *)
0x1800507b7  mov     r13, rax
0x1800507ba  mov     [rsp+248h+var_198], rax
0x1800507c2  cmp     byte ptr [rsp+248h+var_1D8], bl
0x1800507c6  jz      loc_1800509B6
0x1800507cc  cmp     byte ptr [rsp+248h+var_1D8+1], bl
0x1800507d0  jz      loc_1800509B6
0x1800507d6  test    r15, r15
0x1800507d9  jz      loc_1800509B6
0x1800507df  test    rax, rax
0x1800507e2  jz      loc_1800509B6
0x1800507e8  xorps   xmm0, xmm0
0x1800507eb  movups  [rsp+248h+var_140], xmm0
0x1800507f3  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800507fb  movdqu  [rsp+248h+var_130], xmm1
0x180050804  mov     word ptr [rsp+248h+var_140], bx
0x18005080c  mov     [rsp+248h+var_1C8], ebx
0x180050813  mov     [rsp+248h+samDesired], r12d
0x180050818  mov     qword ptr [rsp+248h+dwOptions], rsi
0x18005081d  mov     r9, rdi
0x180050820  mov     r8, r14
0x180050823  lea     rdx, [rsp+248h+var_120]
0x18005082b  call    ?GetLastAccessGUID@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV67@00W4AppIdType@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetLastAccessGUID(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType)
0x180050830  mov     rdx, rax
0x180050833  lea     rcx, [rsp+248h+var_140]
0x18005083b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x180050840  lea     rcx, [rsp+248h+var_120]
0x180050848  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005084d  mov     [rsp+248h+dwOptions], r12d
0x180050852  mov     r9, rsi
0x180050855  mov     r8, rdi
0x180050858  mov     rdx, r14
0x18005085b  call    ?GetLastUserAnnotatedLabel@CapabilityConsentStore@Private@CapabilityAccess@Internal@Windows@@QEBAIAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00W4AppIdType@2345@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityConsentStore::GetLastUserAnnotatedLabel(std::wstring const &,std::wstring const &,std::wstring const &,Windows::Internal::CapabilityAccess::Private::AppIdType)
0x180050860  mov     [rsp+248h+var_1C4], eax
0x180050867  mov     [rsp+248h+var_1C8], eax
0x18005086e  jmp     short loc_1800508B0
0x180050870  xor     ebx, ebx
0x180050872  mov     eax, [rsp+248h+var_1C8]
0x180050879  mov     [rsp+248h+var_1C4], eax
0x180050880  mov     r15, [rsp+248h+var_188]
0x180050888  mov     r13, [rsp+248h+var_198]
0x180050890  mov     r14, [rsp+248h+var_180]
0x180050898  mov     rdi, qword ptr [rsp+248h+pguid.Data1]
0x1800508a0  mov     rsi, [rsp+248h+var_1A8]
0x1800508a8  mov     r12d, [rsp+248h+var_1C0]
0x1800508b0  xorps   xmm0, xmm0
0x1800508b3  movups  xmmword ptr [rsp+248h+var_180], xmm0
0x1800508bb  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x1800508c3  movdqu  [rsp+248h+var_170], xmm1
0x1800508cc  mov     word ptr [rsp+248h+var_180], bx
0x1800508d4  movups  xmmword ptr [rsp+248h+pguid.Data1], xmm0
0x1800508dc  movdqu  [rsp+248h+var_150], xmm1
0x1800508e5  mov     word ptr [rsp+248h+pguid.Data1], bx
0x1800508ed  lea     rdx, [rsp+248h+var_140]
0x1800508f5  lea     rcx, [rsp+248h+var_120]
0x1800508fd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x180050902  mov     [rsp+248h+var_1E0], ebx
0x180050906  lea     rcx, [rsp+248h+var_180]
0x18005090e  mov     [rsp+248h+var_1E8], rcx
0x180050913  lea     rcx, [rsp+248h+pguid]
0x18005091b  mov     [rsp+248h+var_1F0], rcx
0x180050920  mov     [rsp+248h+var_1F8], rbx
0x180050925  mov     rcx, [rsp+248h+var_1B8]
0x18005092d  mov     [rsp+248h+var_200], rcx
0x180050932  mov     ecx, [rsp+248h+var_1C4]
0x180050939  mov     dword ptr [rsp+248h+lpdwDisposition], ecx
0x18005093d  mov     [rsp+248h+phkResult], rax
0x180050942  mov     dword ptr [rsp+248h+lpSecurityAttributes], r12d
0x180050947  mov     qword ptr [rsp+248h+samDesired], r13
0x18005094c  mov     qword ptr [rsp+248h+dwOptions], r15
0x180050951  mov     r9, rsi
0x180050954  mov     r15d, [rsp+248h+arg_38]
0x18005095c  mov     r8d, r15d
0x18005095f  mov     rdx, rdi
0x180050962  mov     rcx, r14
0x180050965  call    ?RecordUsage@SQL@Private@CapabilityAccess@Internal@Windows@@YAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0K0_K1W4AppIdType@2345@V67@I0100I@Z; Windows::Internal::CapabilityAccess::Private::SQL::RecordUsage(std::wstring const &,std::wstring const &,ulong,std::wstring const &,unsigned __int64,unsigned __int64,Windows::Internal::CapabilityAccess::Private::AppIdType,std::wstring,uint,std::wstring const &,unsigned __int64,std::wstring const &,std::wstring const &,uint)
0x18005096a  nop
0x18005096b  lea     rcx, [rsp+248h+pguid]
0x180050973  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050978  nop
0x180050979  lea     rcx, [rsp+248h+var_180]
0x180050981  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050986  mov     r8d, 1; unsigned __int16 *
0x18005098c  lea     rdx, stru_1800DB268; HKEY
0x180050993  mov     rcx, [rsp+248h+var_1D0]; this
0x180050998  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x18005099d  nop
0x18005099e  lea     rcx, [rsp+248h+var_140]
0x1800509a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800509ab  jmp     short loc_1800509BE
0x1800509ad  test    r15d, r15d
0x1800509b0  jnz     loc_180050B5A
0x1800509b6  mov     r15d, [rsp+248h+arg_38]
0x1800509be  test    r15d, r15d
0x1800509c1  jz      loc_180050B5A
0x1800509c7  mov     r8d, 2; unsigned __int16 *
0x1800509cd  lea     rdx, stru_1800DB290; HKEY
0x1800509d4  mov     rcx, [rsp+248h+var_1D0]; this
0x1800509d9  call    ?RegSetUint32Value@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGI@Z; Windows::Internal::CapabilityAccess::Private::RegSetUint32Value(HKEY__ *,ushort const *,uint)
0x1800509de  lea     rcx, [rsp+248h+var_180]
0x1800509e6  call    ?Instance@?$SingletonWithFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@U?$SingletonInitializeFactory@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@2345@@Private@CapabilityAccess@Internal@Windows@@SA?AV?$shared_ptr@VCapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@@std@@XZ; Windows::Internal::CapabilityAccess::Private::SingletonWithFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore,Windows::Internal::CapabilityAccess::Private::SingletonInitializeFactory<Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore>>::Instance(void)
0x1800509eb  nop
0x1800509ec  mov     r8, rdi
0x1800509ef  lea     rdx, [rsp+248h+var_1A8]
0x1800509f7  mov     rcx, [rsp+248h+var_180]
0x1800509ff  call    ?ReadPolicy@CapabilityPolicyStore@Private@CapabilityAccess@Internal@Windows@@QEBA?AV?$shared_ptr@VCapabilityPolicy@Private@CapabilityAccess@Internal@Windows@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@7@@Z; Windows::Internal::CapabilityAccess::Private::CapabilityPolicyStore::ReadPolicy(std::wstring const &)
0x180050a04  nop
0x180050a05  mov     rax, [rsp+248h+var_1A8]
0x180050a0d  test    rax, rax
0x180050a10  jz      loc_180050B34
0x180050a16  cmp     [rax+3Dh], bl
0x180050a19  jz      loc_180050B34
0x180050a1f  xorps   xmm0, xmm0
0x180050a22  movups  xmmword ptr [rsp+248h+pguid.Data1], xmm0
0x180050a2a  lea     rcx, [rsp+248h+pguid]; pguid
0x180050a32  call    cs:__imp_CoCreateGuid
0x180050a38  lea     rdx, [rsp+248h+pguid]; rguid
0x180050a40  lea     rcx, [rsp+248h+var_120]; int
0x180050a48  call    ?GUIDToString@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBU_GUID@@@Z; Windows::Internal::CapabilityAccess::Private::GUIDToString(_GUID const &)
0x180050a4d  nop
0x180050a4e  mov     r8, rax
0x180050a51  lea     rdx, aLastaccessguid; "LastAccessGUID"
0x180050a58  mov     rcx, [rsp+248h+var_1D0]
0x180050a5d  call    ?RegSetStringValue@Private@CapabilityAccess@Internal@Windows@@YAXPEAUHKEY__@@PEBGAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Windows::Internal::CapabilityAccess::Private::RegSetStringValue(HKEY__ *,ushort const *,std::wstring const &)
0x180050a62  nop
0x180050a63  lea     rcx, [rsp+248h+var_120]
0x180050a6b  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050a70  nop
0x180050a71  lea     r15, ?m_tryToastLock@SrwLockManager@Globals@Private@CapabilityAccess@Internal@Windows@@0Vsrwlock@wil@@A; wil::srwlock Windows::Internal::CapabilityAccess::Private::Globals::SrwLockManager::m_tryToastLock
0x180050a78  mov     rcx, r15; SRWLock
0x180050a7b  call    cs:__imp_TryAcquireSRWLockExclusive
0x180050a81  neg     al
0x180050a83  sbb     rcx, rcx
0x180050a86  and     rcx, r15
0x180050a89  mov     [rsp+248h+var_1B8], rcx
0x180050a91  jz      loc_180050B26
0x180050a97  lea     rax, [rsp+248h+var_1B8]
0x180050a9f  mov     [rsp+248h+lpdwDisposition], rax
0x180050aa4  lea     rax, [rsp+248h+pguid]
0x180050aac  mov     [rsp+248h+phkResult], rax
0x180050ab1  lea     rax, [rsp+248h+arg_38]
0x180050ab9  mov     [rsp+248h+lpSecurityAttributes], rax
0x180050abe  lea     rax, [rsp+248h+var_1C0]
0x180050ac6  mov     qword ptr [rsp+248h+samDesired], rax
0x180050acb  mov     qword ptr [rsp+248h+dwOptions], rsi
0x180050ad0  lea     r9, [rsp+248h+var_1A8]
0x180050ad8  mov     r8, rdi
0x180050adb  mov     rdx, r14
0x180050ade  lea     rcx, [rsp+248h+var_D8]
0x180050ae6  call    _lambda_6ac006fb6aed2ed0911b9dc4b09ff962____lambda_6ac006fb6aed2ed0911b9dc4b09ff962_
0x180050aeb  nop
0x180050aec  mov     rdx, rax
0x180050aef  lea     rcx, [rsp+248h+var_198]
0x180050af7  call    std__thread__thread__lambda_6ac006fb6aed2ed0911b9dc4b09ff962__0_
0x180050afc  nop
0x180050afd  lea     rcx, [rsp+248h+var_D8]
0x180050b05  call    _lambda_6ac006fb6aed2ed0911b9dc4b09ff962_____lambda_6ac006fb6aed2ed0911b9dc4b09ff962_
0x180050b0a  lea     rcx, [rsp+248h+var_198]; this
0x180050b12  call    ?detach@thread@std@@QEAAXXZ; std::thread::detach(void)
0x180050b17  nop
0x180050b18  lea     rcx, [rsp+248h+var_198]; this
0x180050b20  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x180050b25  nop
0x180050b26  lea     rcx, [rsp+248h+var_1B8]
0x180050b2e  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180050b33  nop
0x180050b34  mov     rcx, [rsp+248h+var_1A0]; this
0x180050b3c  test    rcx, rcx
0x180050b3f  jz      short loc_180050B47
0x180050b41  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180050b46  nop
0x180050b47  mov     rcx, [rsp+248h+var_180+8]; this
0x180050b4f  test    rcx, rcx
0x180050b52  jz      short loc_180050B5A
0x180050b54  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180050b59  nop
0x180050b5a  lea     rcx, [rsp+248h+var_1D0]
0x180050b5f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050b64  nop
0x180050b65  lea     rcx, [rsp+248h+Src]
0x180050b6d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180050b72  nop
0x180050b73  lea     rcx, [rsp+248h+hKey]
0x180050b7b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180050b80  mov     rcx, [rsp+248h+var_48]
0x180050b88  xor     rcx, rsp; StackCookie
0x180050b8b  call    __security_check_cookie
0x180050b90  add     rsp, 210h
0x180050b97  pop     r15
0x180050b99  pop     r14
0x180050b9b  pop     r13
0x180050b9d  pop     r12
0x180050b9f  pop     rdi
0x180050ba0  pop     rsi
0x180050ba1  pop     rbx
0x180050ba2  retn
0x180050ba3  mov     r9d, 80070057h; char *
0x180050ba9  lea     r8, aOnecoreBaseDev_54; "onecore\\base\\devices\\cam\\core\\capa"...
0x180050bb0  mov     edx, 67Bh; void *
  ... truncated ...
```
