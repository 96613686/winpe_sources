# Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(ulong,ushort const *,ushort const *,Windows::Internal::AssignedAccess::AssignedAccessConfiguration::AADGroupMembershipCacheOperation,bool &)

- ea: `0x1800814a4`
- end: `0x180081a96`
- name: `?PerformAADGroupMembershipOperationInCache@AssignedAccessConfiguration@AssignedAccess@Internal@Windows@@CAJKPEBG0W4AADGroupMembershipCacheOperation@1234@AEA_N@Z`
- size: `1522`
- prototype: `static int __high(unsigned int, const unsigned __int16 *, const unsigned __int16 *, enum Windows::Internal::AssignedAccess::AssignedAccessConfiguration::AADGroupMembershipCacheOperation, bool *)`
- caller_count: `1`
- callee_count: `22`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180080a30`

## callees

- `0x180006640`
- `0x18000b6b4`
- `0x180010c98`
- `0x180013fac`
- `0x180014a5c`
- `0x18001f2b0`
- `0x180022930`
- `0x180029c04`
- `0x18004b730`
- `0x1800587dc`
- `0x18005e2e4`
- `0x18007d678`
- `0x18007d750`
- `0x18007d828`
- `0x18007e174`
- `0x18007e20c`
- `0x18007e320`
- `0x18007e37c`
- `0x18007eef0`
- `0x18008144c`
- `0x1800814a4`
- `0x180082668`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180081529`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180081529`

## string_xrefs

- `0x18008178d`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x18008188f`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x1800818ef`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180081972`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x1800819d2`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180081a34`: `onecoreuap\base\embedded\sys\lockdown\runtime\lib\assignedaccessconfiguration.cpp`
- `0x180081562`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration\AADGroupMembershipCache`
- `0x1800815ea`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration\AADGroupMembershipCache`
- `0x18008166c`: `SOFTWARE\Microsoft\Windows\AssignedAccessConfiguration\AADGroupMembershipCache`
- `0x1800814e9`: `AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfiguration::PerformAADGroupMembershipOperationInCache(
        unsigned int a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        char *a5)
{
  int v9; // r9d
  int v10; // r9d
  int *v11; // rcx
  int v12; // r9d
  int v13; // eax
  unsigned int v14; // esi
  __int64 v15; // rax
  __int64 v16; // r8
  int v17; // eax
  unsigned int v18; // esi
  int v20; // [rsp+20h] [rbp-238h]
  int v21; // [rsp+20h] [rbp-238h]
  int v22[2]; // [rsp+30h] [rbp-228h] BYREF
  __int64 v23; // [rsp+38h] [rbp-220h] BYREF
  int v24[2]; // [rsp+40h] [rbp-218h] BYREF
  _BYTE v25[8]; // [rsp+48h] [rbp-210h] BYREF
  __int64 v26; // [rsp+50h] [rbp-208h] BYREF
  __int64 v27; // [rsp+58h] [rbp-200h] BYREF
  unsigned int v28; // [rsp+60h] [rbp-1F8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+68h] [rbp-1F0h] BYREF
  _BYTE v30[32]; // [rsp+78h] [rbp-1E0h] BYREF
  _BYTE v31[40]; // [rsp+98h] [rbp-1C0h] BYREF
  _QWORD v32[42]; // [rsp+C0h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v28 = a1;
  v27 = a2;
  v26 = a3;
  wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v32,
    "AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache");
  v32[0] = &AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::`vftable';
  AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::StartActivity(
    (AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32,
    a4);
  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  std::wstring::wstring(v31, a3);
  Windows::Internal::AssignedAccess::RegistryKey::OpenCurrentUser(v25, 983103);
  if ( a4 == 1 )
  {
    Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
      (unsigned int)v25,
      (unsigned int)v22,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration\\AADGroupMembershipCache",
      v9,
      0);
    Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
      (unsigned int)v22,
      (unsigned int)&v23,
      a2,
      v10,
      0);
    *(struct _FILETIME *)v24 = SystemTimeAsFileTime;
    Windows::Internal::AssignedAccess::RegistryKey::SetQWORD<std::wstring>(&v23, v31, v24);
    AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::Message<unsigned short const * &,unsigned short const * &,unsigned short const (&)[23]>(
      v32,
      &v27,
      &v26);
    *a5 = 1;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
LABEL_3:
    v11 = v22;
LABEL_14:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v11);
    wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v32);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
    std::wstring::_Tidy_deallocate(v31);
    AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
    return 0;
  }
  if ( a4 == 2 )
  {
    Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
      (unsigned int)v25,
      (unsigned int)v22,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration\\AADGroupMembershipCache",
      v9,
      0);
    Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
      (unsigned int)v22,
      (unsigned int)&v23,
      a2,
      v12,
      0);
    *(_QWORD *)v24 = 0;
    Windows::Internal::AssignedAccess::RegistryKey::SetQWORD<std::wstring>(&v23, v31, v24);
    AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::Message<unsigned short const * &,unsigned short const * &,unsigned short const (&)[19]>(
      v32,
      &v27,
      &v26);
    *a5 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
    goto LABEL_3;
  }
  if ( a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2B1,
      (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
      (const char *)0x8000FFFFLL,
      v20);
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
    std::wstring::_Tidy_deallocate(v31);
    AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
    return 2147549183LL;
  }
  else
  {
    Windows::Internal::AssignedAccess::RegistryKey::Create<unsigned short const *>(
      (unsigned int)v25,
      (unsigned int)&v23,
      (unsigned int)L"SOFTWARE\\Microsoft\\Windows\\AssignedAccessConfiguration\\AADGroupMembershipCache",
      v9,
      0);
    *(_QWORD *)v22 = 0;
    v13 = Windows::Internal::AssignedAccess::RegistryKey::TryOpen<unsigned short const *>(v23, a2, 983103, 0);
    v14 = v13;
    if ( v13 < 0 )
    {
      if ( v13 == -2147024894 )
      {
        *a5 = 0;
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupNotFoundInCache<unsigned short const * &,unsigned short const * &>(
          (__int64)v32,
          &v27,
          &v26);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A8,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
          (const char *)0x80070002LL,
          (int)v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
        std::wstring::_Tidy_deallocate(v31);
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
        return 2147942402LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2AC,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
          (const char *)(unsigned int)v13,
          (int)v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
        std::wstring::_Tidy_deallocate(v31);
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
        return v14;
      }
    }
    else
    {
      *(_QWORD *)v24 = 0;
      v15 = std::wstring::wstring(v30, v31);
      LOBYTE(v16) = 1;
      v17 = Windows::Internal::AssignedAccess::RegistryKey::TryGetQWORD<std::wstring>(v22, v15, v16, v24);
      v18 = v17;
      if ( v17 >= 0 )
      {
        if ( *(_QWORD *)v24 )
        {
          v24[0] = (*(_QWORD *)&SystemTimeAsFileTime - *(_QWORD *)v24) / 0x2710uLL / 0x3E8 / 0x15180;
          *a5 = v24[0] <= a1;
          AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupAndUserFoundInCache<unsigned short const * &,unsigned short const * &,bool &,unsigned long &,unsigned long const &>(
            (__int64)v32,
            &v27,
            &v26,
            a5,
            v24,
            (int *)&v28);
          if ( !*a5 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x28E,
              (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
              (const char *)0x8007078BLL,
              v21);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
            std::wstring::_Tidy_deallocate(v31);
            AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
            return 2147944331LL;
          }
        }
        else
        {
          *a5 = 0;
          v24[0] = 0;
          AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupAndUserFoundInCache<unsigned short const * &,unsigned short const * &,bool &,int,unsigned long const &>(
            (__int64)v32,
            &v27,
            &v26,
            a5,
            v24,
            (int *)&v28);
        }
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
        v11 = (int *)&v23;
        goto LABEL_14;
      }
      if ( v17 == -2147024894 )
      {
        *a5 = 0;
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::UserNotFoundInCache<unsigned short const * &,unsigned short const * &>(
          v32,
          &v27,
          &v26);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x29C,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
          (const char *)0x80070002LL,
          (int)v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
        std::wstring::_Tidy_deallocate(v31);
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
        return 2147942402LL;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2A0,
          (unsigned int)"onecoreuap\\base\\embedded\\sys\\lockdown\\runtime\\lib\\assignedaccessconfiguration.cpp",
          (const char *)(unsigned int)v17,
          (int)v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v22);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v23);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(v25);
        std::wstring::_Tidy_deallocate(v31);
        AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache((AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache *)v32);
        return v18;
      }
    }
  }
}

```

## disassembly

```asm
0x1800814a4  push    rbx
0x1800814a6  push    rsi
0x1800814a7  push    rdi
0x1800814a8  push    r12
0x1800814aa  push    r14
0x1800814ac  push    r15
0x1800814ae  sub     rsp, 228h
0x1800814b5  mov     rax, cs:__security_cookie
0x1800814bc  xor     rax, rsp
0x1800814bf  mov     [rsp+258h+var_48], rax
0x1800814c7  mov     ebx, r9d
0x1800814ca  mov     r14, r8
0x1800814cd  mov     rsi, rdx
0x1800814d0  mov     r15d, ecx
0x1800814d3  mov     [rsp+258h+var_1F8], ecx
0x1800814d7  mov     [rsp+258h+var_200], rdx
0x1800814dc  mov     [rsp+258h+var_208], r8
0x1800814e1  mov     rdi, [rsp+258h+arg_20]
0x1800814e9  lea     rdx, aAssignedaccess_10; "AssignedAccessConfiguration_PerformAADG"...
0x1800814f0  lea     rcx, [rsp+258h+var_198]
0x1800814f8  call    ??0?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800814fd  lea     rax, ??_7AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@6B@; const AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::`vftable'
0x180081504  mov     [rsp+258h+var_198], rax
0x18008150c  mov     edx, ebx; unsigned int
0x18008150e  lea     rcx, [rsp+258h+var_198]; this
0x180081516  call    ?StartActivity@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXK@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::StartActivity(ulong)
0x18008151b  nop
0x18008151c  xor     r12d, r12d
0x18008151f  mov     qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime], r12
0x180081524  lea     rcx, [rsp+258h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180081529  call    cs:__imp_GetSystemTimeAsFileTime
0x18008152f  mov     rdx, r14
0x180081532  lea     rcx, [rsp+258h+var_1C0]
0x18008153a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18008153f  nop
0x180081540  mov     r14d, 0F003Fh
0x180081546  mov     edx, r14d
0x180081549  lea     rcx, [rsp+258h+var_210]
0x18008154e  call    ?OpenCurrentUser@RegistryKey@AssignedAccess@Internal@Windows@@SA?AV1234@K@Z; Windows::Internal::AssignedAccess::RegistryKey::OpenCurrentUser(ulong)
0x180081553  nop
0x180081554  cmp     ebx, 1
0x180081557  jnz     loc_1800815E0
0x18008155d  mov     [rsp+258h+var_238], r12d
0x180081562  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x180081569  lea     rdx, [rsp+258h+var_228]
0x18008156e  lea     rcx, [rsp+258h+var_210]
0x180081573  call    ??$Create@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@PEBGKK@Z; Windows::Internal::AssignedAccess::RegistryKey::Create<ushort const *>(ushort const *,ulong,ulong)
0x180081578  nop
0x180081579  mov     [rsp+258h+var_238], r12d
0x18008157e  mov     r8, rsi
0x180081581  lea     rdx, [rsp+258h+var_220]
0x180081586  lea     rcx, [rsp+258h+var_228]
0x18008158b  call    ??$Create@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@PEBGKK@Z; Windows::Internal::AssignedAccess::RegistryKey::Create<ushort const *>(ushort const *,ulong,ulong)
0x180081590  nop
0x180081591  mov     rax, qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime]
0x180081596  mov     qword ptr [rsp+258h+var_218], rax
0x18008159b  lea     r8, [rsp+258h+var_218]
0x1800815a0  lea     rdx, [rsp+258h+var_1C0]
0x1800815a8  lea     rcx, [rsp+258h+var_220]
0x1800815ad  call    ??$SetQWORD@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_K@Z; Windows::Internal::AssignedAccess::RegistryKey::SetQWORD<std::wstring>(std::wstring &,unsigned __int64 const &)
0x1800815b2  lea     r8, [rsp+258h+var_208]
0x1800815b7  lea     rdx, [rsp+258h+var_200]
0x1800815bc  lea     rcx, [rsp+258h+var_198]
0x1800815c4  call    ??$Message@AEAPEBGAEAPEBGAEAY0BH@$$CBG@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0AEAY0BH@$$CBG@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::Message<ushort const * &,ushort const * &,ushort const (&)[23]>(ushort const * &,ushort const * &,ushort const (&)[23])
0x1800815c9  mov     [rdi], bl
0x1800815cb  lea     rcx, [rsp+258h+var_220]
0x1800815d0  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800815d5  nop
0x1800815d6  lea     rcx, [rsp+258h+var_228]
0x1800815db  jmp     loc_180081821
0x1800815e0  cmp     ebx, 2
0x1800815e3  jnz     short loc_18008165F
0x1800815e5  mov     [rsp+258h+var_238], r12d
0x1800815ea  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x1800815f1  lea     rdx, [rsp+258h+var_228]
0x1800815f6  lea     rcx, [rsp+258h+var_210]
0x1800815fb  call    ??$Create@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@PEBGKK@Z; Windows::Internal::AssignedAccess::RegistryKey::Create<ushort const *>(ushort const *,ulong,ulong)
0x180081600  nop
0x180081601  mov     [rsp+258h+var_238], r12d
0x180081606  mov     r8, rsi
0x180081609  lea     rdx, [rsp+258h+var_220]
0x18008160e  lea     rcx, [rsp+258h+var_228]
0x180081613  call    ??$Create@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@PEBGKK@Z; Windows::Internal::AssignedAccess::RegistryKey::Create<ushort const *>(ushort const *,ulong,ulong)
0x180081618  nop
0x180081619  mov     qword ptr [rsp+258h+var_218], r12
0x18008161e  lea     r8, [rsp+258h+var_218]
0x180081623  lea     rdx, [rsp+258h+var_1C0]
0x18008162b  lea     rcx, [rsp+258h+var_220]
0x180081630  call    ??$SetQWORD@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RegistryKey@AssignedAccess@Internal@Windows@@QEBAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEB_K@Z; Windows::Internal::AssignedAccess::RegistryKey::SetQWORD<std::wstring>(std::wstring &,unsigned __int64 const &)
0x180081635  lea     r8, [rsp+258h+var_208]
0x18008163a  lea     rdx, [rsp+258h+var_200]
0x18008163f  lea     rcx, [rsp+258h+var_198]
0x180081647  call    ??$Message@AEAPEBGAEAPEBGAEAY0BD@$$CBG@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0AEAY0BD@$$CBG@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::Message<ushort const * &,ushort const * &,ushort const (&)[19]>(ushort const * &,ushort const * &,ushort const (&)[19])
0x18008164c  mov     [rdi], r12b
0x18008164f  lea     rcx, [rsp+258h+var_220]
0x180081654  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081659  nop
0x18008165a  jmp     loc_1800815D6
0x18008165f  test    ebx, ebx
0x180081661  jnz     loc_180081A24
0x180081667  mov     [rsp+258h+var_238], r12d
0x18008166c  lea     r8, aSoftwareMicros_3; "SOFTWARE\\Microsoft\\Windows\\AssignedA"...
0x180081673  lea     rdx, [rsp+258h+var_220]
0x180081678  lea     rcx, [rsp+258h+var_210]
0x18008167d  call    ??$Create@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@QEAA?AV0123@PEBGKK@Z; Windows::Internal::AssignedAccess::RegistryKey::Create<ushort const *>(ushort const *,ulong,ulong)
0x180081682  nop
0x180081683  mov     qword ptr [rsp+258h+var_228], r12
0x180081688  lea     rax, [rsp+258h+var_228]
0x18008168d  mov     qword ptr [rsp+258h+var_238], rax; int
0x180081692  xor     r9d, r9d
0x180081695  mov     r8d, r14d
0x180081698  mov     rdx, rsi
0x18008169b  mov     rcx, [rsp+258h+var_220]
0x1800816a0  call    ??$TryOpen@PEBG@RegistryKey@AssignedAccess@Internal@Windows@@SAJPEAUHKEY__@@PEBGKKAEAV0123@@Z; Windows::Internal::AssignedAccess::RegistryKey::TryOpen<ushort const *>(HKEY__ *,ushort const *,ulong,ulong,Windows::Internal::AssignedAccess::RegistryKey &)
0x1800816a5  mov     esi, eax
0x1800816a7  test    eax, eax
0x1800816a9  js      loc_180081944
0x1800816af  mov     qword ptr [rsp+258h+var_218], r12
0x1800816b4  lea     rdx, [rsp+258h+var_1C0]
0x1800816bc  lea     rcx, [rsp+258h+var_1E0]
0x1800816c1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800816c6  lea     r9, [rsp+258h+var_218]
0x1800816cb  mov     r8b, 1
0x1800816ce  mov     rdx, rax
0x1800816d1  lea     rcx, [rsp+258h+var_228]
0x1800816d6  call    ??$TryGetQWORD@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@RegistryKey@AssignedAccess@Internal@Windows@@QEBAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_NAEA_K@Z; Windows::Internal::AssignedAccess::RegistryKey::TryGetQWORD<std::wstring>(std::wstring,bool,unsigned __int64 &)
0x1800816db  mov     esi, eax
0x1800816dd  test    eax, eax
0x1800816df  js      loc_180081861
0x1800816e5  mov     rax, qword ptr [rsp+258h+var_218]
0x1800816ea  mov     r9, rdi
0x1800816ed  lea     r8, [rsp+258h+var_208]
0x1800816f2  test    rax, rax
0x1800816f5  jz      loc_1800817E2
0x1800816fb  mov     rcx, qword ptr [rsp+258h+SystemTimeAsFileTime.dwLowDateTime]
0x180081700  sub     rcx, rax
0x180081703  mov     rax, 346DC5D63886594Bh
0x18008170d  mul     rcx
0x180081710  mov     rcx, rdx
0x180081713  shr     rcx, 0Bh
0x180081717  mov     rax, 624DD2F1A9FBE77h
0x180081721  mul     rcx
0x180081724  sub     rcx, rdx
0x180081727  shr     rcx, 1
0x18008172a  add     rcx, rdx
0x18008172d  shr     rcx, 9
0x180081731  mov     rax, 0C22E450672894AB7h
0x18008173b  mul     rcx
0x18008173e  shr     rdx, 10h
0x180081742  mov     [rsp+258h+var_218], edx
0x180081746  cmp     edx, r15d
0x180081749  setbe   al
0x18008174c  mov     [rdi], al
0x18008174e  lea     rax, [rsp+258h+var_1F8]
0x180081753  mov     [rsp+258h+var_230], rax
0x180081758  lea     rax, [rsp+258h+var_218]
0x18008175d  mov     qword ptr [rsp+258h+var_238], rax; int
0x180081762  lea     rdx, [rsp+258h+var_200]
0x180081767  lea     rcx, [rsp+258h+var_198]
0x18008176f  call    ??$AADGroupAndUserFoundInCache@AEAPEBGAEAPEBGAEA_NAEAKAEBK@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0AEA_NAEAKAEBK@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupAndUserFoundInCache<ushort const * &,ushort const * &,bool &,ulong &,ulong const &>(ushort const * &,ushort const * &,bool &,ulong &,ulong const &)
0x180081774  cmp     [rdi], r12b
0x180081777  jnz     loc_180081811
0x18008177d  mov     rcx, [rsp+258h]; this
0x180081785  mov     ebx, 8007078Bh
0x18008178a  mov     r9d, ebx; char *
0x18008178d  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180081794  mov     edx, 28Eh; void *
0x180081799  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008179e  nop
0x18008179f  lea     rcx, [rsp+258h+var_228]
0x1800817a4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800817a9  nop
0x1800817aa  lea     rcx, [rsp+258h+var_220]
0x1800817af  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800817b4  nop
0x1800817b5  lea     rcx, [rsp+258h+var_210]
0x1800817ba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800817bf  nop
0x1800817c0  lea     rcx, [rsp+258h+var_1C0]
0x1800817c8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800817cd  nop
0x1800817ce  lea     rcx, [rsp+258h+var_198]; this
0x1800817d6  call    ??1AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache(void)
0x1800817db  mov     eax, ebx
0x1800817dd  jmp     loc_180081A74
0x1800817e2  mov     [rdi], r12b
0x1800817e5  mov     [rsp+258h+var_218], r12d
0x1800817ea  lea     rax, [rsp+258h+var_1F8]
0x1800817ef  mov     [rsp+258h+var_230], rax
0x1800817f4  lea     rax, [rsp+258h+var_218]
0x1800817f9  mov     qword ptr [rsp+258h+var_238], rax
0x1800817fe  lea     rdx, [rsp+258h+var_200]
0x180081803  lea     rcx, [rsp+258h+var_198]
0x18008180b  call    ??$AADGroupAndUserFoundInCache@AEAPEBGAEAPEBGAEA_NHAEBK@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0AEA_N$$QEAHAEBK@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupAndUserFoundInCache<ushort const * &,ushort const * &,bool &,int,ulong const &>(ushort const * &,ushort const * &,bool &,int &&,ulong const &)
0x180081810  nop
0x180081811  lea     rcx, [rsp+258h+var_228]
0x180081816  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008181b  nop
0x18008181c  lea     rcx, [rsp+258h+var_220]
0x180081821  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081826  lea     rcx, [rsp+258h+var_198]
0x18008182e  call    ?Stop@?$ActivityBase@VAssignedAccessTelemetry@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<AssignedAccessTelemetry,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180081833  nop
0x180081834  lea     rcx, [rsp+258h+var_210]
0x180081839  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008183e  nop
0x18008183f  lea     rcx, [rsp+258h+var_1C0]
0x180081847  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008184c  nop
0x18008184d  lea     rcx, [rsp+258h+var_198]; this
0x180081855  call    ??1AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache(void)
0x18008185a  xor     eax, eax
0x18008185c  jmp     loc_180081A74
0x180081861  mov     ebx, 80070002h
0x180081866  cmp     esi, ebx
0x180081868  jnz     short loc_1800818E4
0x18008186a  mov     [rdi], r12b
0x18008186d  lea     r8, [rsp+258h+var_208]
0x180081872  lea     rdx, [rsp+258h+var_200]
0x180081877  lea     rcx, [rsp+258h+var_198]
0x18008187f  call    ??$UserNotFoundInCache@AEAPEBGAEAPEBG@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::UserNotFoundInCache<ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x180081884  mov     rcx, [rsp+258h]; this
0x18008188c  mov     r9d, ebx; char *
0x18008188f  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180081896  mov     edx, 29Ch; void *
0x18008189b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800818a0  nop
0x1800818a1  lea     rcx, [rsp+258h+var_228]
0x1800818a6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818ab  nop
0x1800818ac  lea     rcx, [rsp+258h+var_220]
0x1800818b1  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818b6  nop
0x1800818b7  lea     rcx, [rsp+258h+var_210]
0x1800818bc  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800818c1  nop
0x1800818c2  lea     rcx, [rsp+258h+var_1C0]
0x1800818ca  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800818cf  nop
0x1800818d0  lea     rcx, [rsp+258h+var_198]; this
0x1800818d8  call    ??1AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache(void)
0x1800818dd  mov     eax, ebx
0x1800818df  jmp     loc_180081A74
0x1800818e4  mov     rcx, [rsp+258h]; this
0x1800818ec  mov     r9d, esi; char *
0x1800818ef  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800818f6  mov     edx, 2A0h; void *
0x1800818fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081900  nop
0x180081901  lea     rcx, [rsp+258h+var_228]
0x180081906  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008190b  nop
0x18008190c  lea     rcx, [rsp+258h+var_220]
0x180081911  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081916  nop
0x180081917  lea     rcx, [rsp+258h+var_210]
0x18008191c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081921  nop
0x180081922  lea     rcx, [rsp+258h+var_1C0]
0x18008192a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18008192f  nop
0x180081930  lea     rcx, [rsp+258h+var_198]; this
0x180081938  call    ??1AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache(void)
0x18008193d  mov     eax, esi
0x18008193f  jmp     loc_180081A74
0x180081944  mov     ebx, 80070002h
0x180081949  cmp     esi, ebx
0x18008194b  jnz     short loc_1800819C7
0x18008194d  mov     [rdi], r12b
0x180081950  lea     r8, [rsp+258h+var_208]
0x180081955  lea     rdx, [rsp+258h+var_200]
0x18008195a  lea     rcx, [rsp+258h+var_198]
0x180081962  call    ??$AADGroupNotFoundInCache@AEAPEBGAEAPEBG@AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAAXAEAPEBG0@Z; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::AADGroupNotFoundInCache<ushort const * &,ushort const * &>(ushort const * &,ushort const * &)
0x180081967  mov     rcx, [rsp+258h]; this
0x18008196f  mov     r9d, ebx; char *
0x180081972  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x180081979  mov     edx, 2A8h; void *
0x18008197e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180081983  nop
0x180081984  lea     rcx, [rsp+258h+var_228]
0x180081989  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008198e  nop
0x18008198f  lea     rcx, [rsp+258h+var_220]
0x180081994  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180081999  nop
0x18008199a  lea     rcx, [rsp+258h+var_210]
0x18008199f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800819a4  nop
0x1800819a5  lea     rcx, [rsp+258h+var_1C0]
0x1800819ad  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800819b2  nop
0x1800819b3  lea     rcx, [rsp+258h+var_198]; this
0x1800819bb  call    ??1AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache@AssignedAccessTelemetry@@QEAA@XZ; AssignedAccessTelemetry::AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache::~AssignedAccessConfiguration_PerformAADGroupMembershipOperationInCache(void)
0x1800819c0  mov     eax, ebx
0x1800819c2  jmp     loc_180081A74
0x1800819c7  mov     rcx, [rsp+258h]; this
0x1800819cf  mov     r9d, esi; char *
0x1800819d2  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\embedded\\sys\\lockdo"...
0x1800819d9  mov     edx, 2ACh; void *
0x1800819de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
  ... truncated ...
```
