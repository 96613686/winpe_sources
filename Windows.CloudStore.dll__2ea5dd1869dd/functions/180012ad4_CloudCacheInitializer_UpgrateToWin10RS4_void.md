# CloudCacheInitializer::UpgrateToWin10RS4(void)

- ea: `0x180012ad4`
- end: `0x1800131e0`
- name: `?UpgrateToWin10RS4@CloudCacheInitializer@@CAJXZ`
- size: `1804`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `40`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18003c5b8`

## callees

- `0x180010688`
- `0x1800127bc`
- `0x180012ad4`
- `0x180014aac`
- `0x180015dbc`
- `0x180019720`
- `0x1800219e0`
- `0x1800238d0`
- `0x180023e34`
- `0x180023fd4`
- `0x180024fd0`
- `0x18002c020`
- `0x18002e010`
- `0x18002ec7c`
- `0x180031134`
- `0x18003137c`
- `0x1800316d0`
- `0x1800345c8`
- `0x180034794`
- `0x18003727c`
- `0x180038db8`
- `0x18003e670`
- `0x18003e904`
- `0x1800560fc`
- `0x18005d758`
- `0x18005ebb4`
- `0x18005edd0`
- `0x18005f060`
- `0x18009f7ac`
- `0x1800b3c30`
- `0x1800cff10`
- `0x1800d6a5c`
- `0x1800e93e0`
- `0x1800f270c`
- `0x1800f3ee4`
- `0x1800f8598`
- `0x1801201a0`
- `0x180123338`
- `0x1801a6bd4`
- `0x180208010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180012d02`
- `api-ms-win-crt-private-l1-1-0!_o_strcat_s` at `0x180012d02`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180012cd5`
- `api-ms-win-crt-private-l1-1-0!_o_strcpy_s` at `0x180012cd5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e34`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180012e34`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800130d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013145`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800130d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180013145`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001305f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18001305f`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180013124`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180013134`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180013124`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180013134`

## string_xrefs

- `0x180012d41`: `Store\Cache\DefaultAccount`
- `0x18001312a`: `Software\Microsoft\Windows\CurrentVersion\CloudStore\Store\Cache`
- `0x180013113`: `Software\Microsoft\Windows\CurrentVersion\CloudStore\Store\Cache\DefaultAccount`
- `0x180012d5e`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x180012e49`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x180013074`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=26 #try_helpers=1
__int64 CloudCacheInitializer::UpgrateToWin10RS4(void)
{
  __int64 v0; // rax
  volatile signed __int32 *v1; // rsi
  __int64 v2; // rbx
  __int64 v3; // r14
  int v4; // ebx
  char *v5; // rdx
  __int64 *v6; // rbx
  unsigned int v7; // eax
  int v8; // edx
  char (*v9)[12]; // rdx
  unsigned int v10; // eax
  int v11; // edx
  HKEY *v12; // r9
  int RegistryRootKey; // eax
  char v14; // r14
  LPCWSTR v15; // r14
  const WCHAR *v16; // r13
  const WCHAR *v17; // rdx
  unsigned int v18; // eax
  char v19; // r15
  __int64 v20; // r15
  void (__fastcall *v21)(__int64, _BYTE *, char *); // r12
  const char *v22; // rdx
  __int64 v23; // rax
  __int64 v24; // rax
  const WCHAR *v25; // rdx
  unsigned int v26; // eax
  const char *v27; // r9
  HKEY v28; // rcx
  int phkResult; // [rsp+20h] [rbp-4D8h]
  unsigned int *phkResulta; // [rsp+20h] [rbp-4D8h]
  HKEY hKey; // [rsp+48h] [rbp-4B0h] BYREF
  const WCHAR *v33; // [rsp+50h] [rbp-4A8h]
  HKEY v34; // [rsp+58h] [rbp-4A0h] BYREF
  _QWORD v35[2]; // [rsp+60h] [rbp-498h] BYREF
  HKEY *v36; // [rsp+70h] [rbp-488h] BYREF
  HKEY v37; // [rsp+78h] [rbp-480h] BYREF
  int v38; // [rsp+80h] [rbp-478h]
  __int64 v39; // [rsp+88h] [rbp-470h]
  char v40[8]; // [rsp+90h] [rbp-468h] BYREF
  int v41[2]; // [rsp+98h] [rbp-460h] BYREF
  std::_Ref_count_base *v42; // [rsp+A0h] [rbp-458h]
  __int64 v43; // [rsp+A8h] [rbp-450h]
  volatile signed __int32 *v44; // [rsp+B0h] [rbp-448h]
  _BYTE v45[16]; // [rsp+B8h] [rbp-440h] BYREF
  RTL_SRWLOCK *v46; // [rsp+C8h] [rbp-430h]
  LPCWSTR v47; // [rsp+D8h] [rbp-420h] BYREF
  const WCHAR *v48; // [rsp+E0h] [rbp-418h]
  _BYTE v49[24]; // [rsp+F0h] [rbp-408h] BYREF
  char v50[8]; // [rsp+108h] [rbp-3F0h] BYREF
  unsigned int v51[20]; // [rsp+110h] [rbp-3E8h] BYREF
  LPCWSTR lpSubKey[3]; // [rsp+160h] [rbp-398h] BYREF
  unsigned __int64 v53; // [rsp+178h] [rbp-380h]
  _BYTE v54[32]; // [rsp+180h] [rbp-378h] BYREF
  _BYTE v55[32]; // [rsp+1A0h] [rbp-358h] BYREF
  PSRWLOCK SRWLock; // [rsp+1C0h] [rbp-338h] BYREF
  std::_Ref_count_base *v57; // [rsp+1C8h] [rbp-330h]
  char v58[32]; // [rsp+1D0h] [rbp-328h] BYREF
  char Destination[132]; // [rsp+1F0h] [rbp-308h] BYREF
  int v60; // [rsp+274h] [rbp-284h]
  _BYTE v61[128]; // [rsp+280h] [rbp-278h] BYREF
  _QWORD v62[12]; // [rsp+300h] [rbp-1F8h] BYREF
  _BYTE v63[16]; // [rsp+360h] [rbp-198h] BYREF
  char v64[144]; // [rsp+370h] [rbp-188h] BYREF
  char v65[16]; // [rsp+400h] [rbp-F8h] BYREF
  char v66[144]; // [rsp+410h] [rbp-E8h] BYREF
  char Source[8]; // [rsp+4A0h] [rbp-58h] BYREF
  struct _SECURITY_ATTRIBUTES v68[3]; // [rsp+4A8h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4F8h] [rbp+0h]

  EffectiveUserContext::CreateForCurrentUser(v45);
  *(_QWORD *)Source = operator new(0x70u);
  v0 = std::_Ref_count_obj2<WindowsPersistenceContext>::_Ref_count_obj2<WindowsPersistenceContext>(
         *(_QWORD *)Source,
         v45,
         &LocaleName);
  v1 = (volatile signed __int32 *)v0;
  v2 = v0 + 16;
  v43 = v0 + 16;
  v44 = (volatile signed __int32 *)v0;
  if ( v0 )
    _InterlockedIncrement((volatile signed __int32 *)(v0 + 8));
  *(_QWORD *)Source = v0 + 16;
  *(_QWORD *)&v68[0].nLength = v0;
  Windows::Internal::Storage::Cloud::Core::SchemaRegistry_CreateInstance(v41, Source);
  if ( v1 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v1);
  EffectiveUserContext::EffectiveUserContext(v54, v45);
  std::wstring::wstring(v55);
  std::make_shared<EffectiveWebAccountContext::State,>(&SRWLock);
  HIDWORD(SRWLock[6].Ptr) = 1;
  v33 = (const WCHAR *)v54;
  v3 = EnsureMemberWithReturnType_std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount__const___std::shared_ptr_Windows::Internal::Storage::Cloud::Core::CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___(SRWLock);
  if ( v1 )
    _InterlockedIncrement(v1 + 2);
  v35[0] = v2;
  v35[1] = v1;
  v33 = (const WCHAR *)v45;
  v4 = EnsureMemberWithReturnType_std::shared_ptr_Windows::Internal::Storage::Cloud::Core::UserObjectFactory__const___std::shared_ptr_Windows::Internal::Storage::Cloud::Core::UserObjectFactory___lambda_56df11823bcbcfc6bc294d9066c0c738___(v46 + 1);
  *(_QWORD *)Source = operator new(0x158u);
  v6 = (__int64 *)Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::CloudStoreCoreImpl(
                    *(_DWORD *)Source,
                    v4,
                    3,
                    (unsigned int)v35,
                    (__int64)v41,
                    v3);
  v35[0] = v6;
  if ( v1 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v1);
  v60 = 0;
  Windows::Internal::Storage::Cloud::Core::GetRandomNumberInBase64(
    (Windows::Internal::Storage::Cloud::Core *)Source,
    (char (*)[12])v5);
  v7 = strcpy_s(Destination, 0x81u, Source);
  CloudStoreUtilities::ThrowIfCError((CloudStoreUtilities *)v7, v8);
  Windows::Internal::Storage::Cloud::Core::GetRandomNumberInBase64(
    (Windows::Internal::Storage::Cloud::Core *)Source,
    v9);
  v10 = _o_strcat_s(Destination, 129, Source);
  CloudStoreUtilities::ThrowIfCError((CloudStoreUtilities *)v10, v11);
  hKey = 0;
  *(_QWORD *)Source = &hKey;
  *(_QWORD *)&v68[0].nLength = 0;
  LOBYTE(v68[0].lpSecurityDescriptor) = 1;
  RegistryRootKey = CloudStoreUtilities::GetRegistryRootKey(0, L"Store\\Cache\\DefaultAccount", v68, v12);
  if ( RegistryRootKey >= 0 )
  {
    v14 = 1;
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2D4,
      (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
      (const char *)(unsigned int)RegistryRootKey,
      phkResult);
    v14 = 0;
  }
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(Source);
  if ( v14 )
  {
    CloudCacheInitializer::GetSubkeys(&v47, hKey);
    v15 = v47;
    v16 = v48;
    *(_QWORD *)Source = v48;
    while ( 1 )
    {
      v33 = v15;
      if ( v15 == v16 )
        break;
      std::operator+<unsigned short>(lpSubKey, v15, L"\\Current");
      v34 = 0;
      v36 = &v34;
      v37 = 0;
      LOBYTE(v38) = 1;
      v17 = (const WCHAR *)lpSubKey;
      if ( v53 > 7 )
        v17 = lpSubKey[0];
      v18 = RegOpenKeyExW(hKey, v17, 0, 0xF003Fu, &v37);
      if ( v18 )
      {
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x2DB,
          (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
          (const char *)v18,
          (unsigned int)phkResulta);
        v19 = 0;
      }
      else
      {
        v19 = 1;
      }
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v36);
      if ( v19 )
      {
        try
        {
          CloudCacheInitializer::ConvertRS3DataStoreIdToItemId(v61);
          v20 = *(_QWORD *)v41;
          v21 = *(void (__fastcall **)(__int64, _BYTE *, char *))(**(_QWORD **)v41 + 8LL);
          v22 = (const char *)v62;
          if ( v62[3] > 0xFu )
            v22 = (const char *)v62[0];
          std::string::string(v58, v22);
          v21(v20, v49, v58);
          std::string::_Tidy_deallocate(v58);
          if ( GetEnableSyncOnActivityFeed((const struct bond::RuntimeSchema *)v49) )
          {
            CloudCacheInitializer::LoadRS3CacheBlob((unsigned __int8 *)&v36, (__int64)v34);
            if ( v38 )
            {
              Windows::Internal::Storage::Cloud::Core::MakeVersionedTombstonedData(
                v51,
                v49,
                &v36,
                (v39 - 116444736000000000LL) / 10000000 + v39 - 116444736000000000LL);
              wil::run_as_self(v40);
              v23 = *v6;
              ++v60;
              (*(void (__fastcall **)(__int64 *, _BYTE *, _BYTE *, __int64, char *))(v23 + 24))(
                v6,
                v63,
                v61,
                1,
                Destination);
              v24 = *v6;
              ++v60;
              phkResulta = v51;
              (*(void (__fastcall **)(__int64 *, char *, _BYTE *, _BYTE *))(v24 + 48))(v6, v65, v61, v63);
              Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v66);
              Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry((Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry *)v64);
              wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v40);
              schematized_data::~schematized_data((schematized_data *)v51);
            }
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
              &v34,
              0);
            if ( *((_QWORD *)v15 + 3) <= 7u )
              v25 = v15;
            else
              v25 = *(const WCHAR **)v15;
            v26 = RegDeleteTreeW(hKey, v25);
            if ( v26 )
              wil::details::in1diag3::_Log_Win32(
                retaddr,
                (void *)0x2FD,
                (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
                (const char *)v26,
                (unsigned int)phkResulta);
            boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&v37);
          }
          boost::detail::shared_count::~shared_count((boost::detail::shared_count *)v50);
          Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId((Windows::Internal::Storage::Cloud::Core::CloudStoreItemId *)v61);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x300,
            (unsigned int)"onecoreuap\\shell\\cloudstore\\store\\cache\\src\\cloudcacheinitializer.cpp",
            v27);
          v1 = v44;
          v6 = (__int64 *)v35[0];
          v15 = v33;
          v16 = *(const WCHAR **)Source;
        }
      }
      if ( v34 )
        RegCloseKey(v34);
      if ( v53 > 7 )
        std::_Deallocate<16>((void *)lpSubKey[0], (const struct std::nothrow_t *)(2 * v53 + 2));
      v15 += 16;
    }
    std::vector<std::wstring>::_Tidy(&v47);
  }
  RegDeleteKeyW(
    HKEY_CURRENT_USER,
    L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\Store\\Cache\\DefaultAccount");
  RegDeleteKeyW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudStore\\Store\\Cache");
  v28 = hKey;
  if ( hKey )
    RegCloseKey(hKey);
  if ( v6 )
    std::default_delete<Windows::Internal::Storage::Cloud::Core::CloudStoreCore>::operator()(v28, v6);
  if ( v57 )
    std::_Ref_count_base::_Decref(v57);
  std::wstring::~wstring(v55);
  EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v54);
  if ( v42 )
    std::_Ref_count_base::_Decref(v42);
  if ( v1 )
    std::_Ref_count_base::_Decref((std::_Ref_count_base *)v1);
  EffectiveUserContext::~EffectiveUserContext((EffectiveUserContext *)v45);
  return 0;
}

```

## disassembly

```asm
0x180012ad4  push    rbx
0x180012ad6  push    rsi
0x180012ad7  push    r12
0x180012ad9  push    r13
0x180012adb  push    r14
0x180012add  push    r15
0x180012adf  sub     rsp, 4C8h
0x180012ae6  mov     rax, cs:__security_cookie
0x180012aed  xor     rax, rsp
0x180012af0  mov     [rsp+4F8h+var_40], rax
0x180012af8  lea     rcx, [rsp+4F8h+var_440]
0x180012b00  call    ?CreateForCurrentUser@EffectiveUserContext@@SA?AV1@_N@Z; EffectiveUserContext::CreateForCurrentUser(bool)
0x180012b05  nop
0x180012b06  mov     ecx, 70h ; 'p'; Size
0x180012b0b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012b10  mov     qword ptr [rsp+4F8h+Source], rax
0x180012b18  lea     r14, LocaleName
0x180012b1f  mov     r8, r14
0x180012b22  lea     rdx, [rsp+4F8h+var_440]
0x180012b2a  mov     rcx, rax
0x180012b2d  call    ??$?0AEBVEffectiveUserContext@@AEAY00$$CBG@?$_Ref_count_obj2@VWindowsPersistenceContext@@@std@@QEAA@AEBVEffectiveUserContext@@AEAY00$$CBG@Z; std::_Ref_count_obj2<WindowsPersistenceContext>::_Ref_count_obj2<WindowsPersistenceContext>(EffectiveUserContext const &,ushort const (&)[1])
0x180012b32  mov     rsi, rax
0x180012b35  lea     rbx, [rax+10h]
0x180012b39  mov     [rsp+4F8h+var_450], rbx
0x180012b41  mov     [rsp+4F8h+var_448], rax
0x180012b49  test    rax, rax
0x180012b4c  jz      short loc_180012B52
0x180012b4e  lock inc dword ptr [rax+8]
0x180012b52  mov     qword ptr [rsp+4F8h+Source], rbx
0x180012b5a  mov     qword ptr [rsp+4F8h+var_50], rsi
0x180012b62  lea     rdx, [rsp+4F8h+Source]
0x180012b6a  lea     rcx, [rsp+4F8h+var_460]
0x180012b72  call    ?SchemaRegistry_CreateInstance@Core@Cloud@Storage@Internal@Windows@@YA?AV?$shared_ptr@VSchemaRegistry@Core@Cloud@Storage@Internal@Windows@@@std@@AEBV?$shared_ptr@VPersistenceContext@Core@Cloud@Storage@Internal@Windows@@@7@@Z; Windows::Internal::Storage::Cloud::Core::SchemaRegistry_CreateInstance(std::shared_ptr<Windows::Internal::Storage::Cloud::Core::PersistenceContext> const &)
0x180012b77  nop
0x180012b78  test    rsi, rsi
0x180012b7b  jz      short loc_180012B85
0x180012b7d  mov     rcx, rsi; this
0x180012b80  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012b85  lea     r9, [rbx+28h]
0x180012b89  cmp     qword ptr [r9+18h], 7
0x180012b8e  jbe     short loc_180012B93
0x180012b90  mov     r9, [r9]
0x180012b93  lea     rdx, [rsp+4F8h+var_440]
0x180012b9b  lea     rcx, [rsp+4F8h+var_378]
0x180012ba3  call    ??0EffectiveUserContext@@QEAA@$$QEAV0@@Z; EffectiveUserContext::EffectiveUserContext(EffectiveUserContext &&)
0x180012ba8  nop
0x180012ba9  test    r9, r9
0x180012bac  cmovnz  r14, r9
0x180012bb0  mov     rdx, r14
0x180012bb3  lea     rcx, [rsp+4F8h+var_358]
0x180012bbb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180012bc0  nop
0x180012bc1  lea     rcx, [rsp+4F8h+SRWLock]
0x180012bc9  call    ??$make_shared@UState@EffectiveWebAccountContext@@$$V@std@@YA?AV?$shared_ptr@UState@EffectiveWebAccountContext@@@0@XZ; std::make_shared<EffectiveWebAccountContext::State,>(void)
0x180012bce  nop
0x180012bcf  mov     rax, [rsp+4F8h+SRWLock]
0x180012bd7  mov     dword ptr [rax+34h], 1
0x180012bde  lea     rax, [rsp+4F8h+var_378]
0x180012be6  mov     [rsp+4F8h+var_4A8], rax
0x180012beb  mov     rcx, [rsp+4F8h+SRWLock]; SRWLock
0x180012bf3  mov     [rsp+4F8h+var_4B8], 0
0x180012bf8  lea     rdx, [rcx+10h]
0x180012bfc  lea     r9, [rsp+4F8h+var_4A8]
0x180012c01  lea     r8, [rsp+4F8h+var_4B8]
0x180012c06  call    EnsureMemberWithReturnType_std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount__const___std__shared_ptr_Windows__Internal__Storage__Cloud__Core__CloudStoreAccount___lambda_023b433145e571973f82c66908a08866___
0x180012c0b  mov     r14, rax
0x180012c0e  test    rsi, rsi
0x180012c11  jz      short loc_180012C17
0x180012c13  lock inc dword ptr [rsi+8]
0x180012c17  mov     [rsp+4F8h+var_498], rbx
0x180012c1c  mov     [rsp+4F8h+var_490], rsi
0x180012c21  lea     rax, [rsp+4F8h+var_440]
0x180012c29  mov     [rsp+4F8h+var_4A8], rax
0x180012c2e  mov     [rsp+4F8h+var_4B8], 0
0x180012c33  mov     rcx, [rsp+4F8h+var_430]
0x180012c3b  lea     rdx, [rcx+20h]
0x180012c3f  add     rcx, 8; SRWLock
0x180012c43  lea     r9, [rsp+4F8h+var_4A8]
0x180012c48  lea     r8, [rsp+4F8h+var_4B8]
0x180012c4d  call    EnsureMemberWithReturnType_std__shared_ptr_Windows__Internal__Storage__Cloud__Core__UserObjectFactory__const___std__shared_ptr_Windows__Internal__Storage__Cloud__Core__UserObjectFactory___lambda_56df11823bcbcfc6bc294d9066c0c738___
0x180012c52  mov     rbx, rax
0x180012c55  mov     ecx, 158h; Size
0x180012c5a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180012c5f  mov     qword ptr [rsp+4F8h+Source], rax
0x180012c67  mov     [rsp+4F8h+var_4D0], r14
0x180012c6c  lea     rcx, [rsp+4F8h+var_460]
0x180012c74  mov     [rsp+4F8h+phkResult], rcx; int
0x180012c79  lea     r9, [rsp+4F8h+var_498]
0x180012c7e  mov     r8d, 3
0x180012c84  mov     rdx, rbx
0x180012c87  mov     rcx, rax
0x180012c8a  call    ??0CloudStoreCoreImpl@Core@Cloud@Storage@Internal@Windows@@QEAA@AEBV?$shared_ptr@VUserObjectFactory@Core@Cloud@Storage@Internal@Windows@@@std@@W4CloudStoreCoreOptions@12345@AEBV?$shared_ptr@VPersistenceContext@Core@Cloud@Storage@Internal@Windows@@@7@AEBV?$shared_ptr@VSchemaRegistry@Core@Cloud@Storage@Internal@Windows@@@7@AEBV?$shared_ptr@VCloudStoreAccount@Core@Cloud@Storage@Internal@Windows@@@7@@Z; Windows::Internal::Storage::Cloud::Core::CloudStoreCoreImpl::CloudStoreCoreImpl(std::shared_ptr<Windows::Internal::Storage::Cloud::Core::UserObjectFactory> const &,Windows::Internal::Storage::Cloud::Core::CloudStoreCoreOptions,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::PersistenceContext> const &,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::SchemaRegistry> const &,std::shared_ptr<Windows::Internal::Storage::Cloud::Core::CloudStoreAccount> const &)
0x180012c8f  mov     rbx, rax
0x180012c92  mov     [rsp+4F8h+var_498], rax
0x180012c97  test    rsi, rsi
0x180012c9a  jz      short loc_180012CA4
0x180012c9c  mov     rcx, rsi; this
0x180012c9f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180012ca4  mov     [rsp+4F8h+var_284], 0
0x180012caf  lea     rcx, [rsp+4F8h+Source]; this
0x180012cb7  call    ?GetRandomNumberInBase64@Core@Cloud@Storage@Internal@Windows@@YAXAEAY0M@D@Z; Windows::Internal::Storage::Cloud::Core::GetRandomNumberInBase64(char (&)[12])
0x180012cbc  lea     r8, [rsp+4F8h+Source]; Source
0x180012cc4  mov     r14d, 81h
0x180012cca  mov     edx, r14d; SizeInBytes
0x180012ccd  lea     rcx, [rsp+4F8h+Destination]; Destination
0x180012cd5  call    cs:__imp_strcpy_s
0x180012cdb  mov     ecx, eax; this
0x180012cdd  call    ?ThrowIfCError@CloudStoreUtilities@@YAXH@Z; CloudStoreUtilities::ThrowIfCError(int)
0x180012ce2  lea     rcx, [rsp+4F8h+Source]; this
0x180012cea  call    ?GetRandomNumberInBase64@Core@Cloud@Storage@Internal@Windows@@YAXAEAY0M@D@Z; Windows::Internal::Storage::Cloud::Core::GetRandomNumberInBase64(char (&)[12])
0x180012cef  lea     r8, [rsp+4F8h+Source]
0x180012cf7  mov     edx, r14d
0x180012cfa  lea     rcx, [rsp+4F8h+Destination]
0x180012d02  call    cs:__imp__o_strcat_s
0x180012d08  mov     ecx, eax; this
0x180012d0a  call    ?ThrowIfCError@CloudStoreUtilities@@YAXH@Z; CloudStoreUtilities::ThrowIfCError(int)
0x180012d0f  mov     [rsp+4F8h+hKey], 0
0x180012d18  lea     rax, [rsp+4F8h+hKey]
0x180012d1d  mov     qword ptr [rsp+4F8h+Source], rax
0x180012d25  mov     qword ptr [rsp+4F8h+var_50], 0
0x180012d31  mov     [rsp+4F8h+var_48], 1
0x180012d39  lea     r8, [rsp+4F8h+var_50]; unsigned __int16 *
0x180012d41  lea     rdx, aStoreCacheDefa; "Store\\Cache\\DefaultAccount"
0x180012d48  xor     ecx, ecx; this
0x180012d4a  call    ?GetRegistryRootKey@CloudStoreUtilities@@YAJPEBG0PEAPEAUHKEY__@@@Z; CloudStoreUtilities::GetRegistryRootKey(ushort const *,ushort const *,HKEY__ * *)
0x180012d4f  mov     rcx, [rsp+4F8h]; this
0x180012d57  test    eax, eax
0x180012d59  jns     short loc_180012D74
0x180012d5b  mov     r9d, eax; char *
0x180012d5e  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180012d65  mov     edx, 2D4h; void *
0x180012d6a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180012d6f  xor     r14b, r14b
0x180012d72  jmp     short loc_180012D77
0x180012d74  mov     r14b, 1
0x180012d77  lea     rcx, [rsp+4F8h+Source]
0x180012d7f  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180012d84  test    r14b, r14b
0x180012d87  jz      loc_180013113
0x180012d8d  mov     rdx, [rsp+4F8h+hKey]
0x180012d92  lea     rcx, [rsp+4F8h+var_420]
0x180012d9a  call    ?GetSubkeys@CloudCacheInitializer@@CA?AV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@PEAUHKEY__@@@Z; CloudCacheInitializer::GetSubkeys(HKEY__ *)
0x180012d9f  nop
0x180012da0  mov     r14, [rsp+4F8h+var_420]
0x180012da8  mov     r13, [rsp+4F8h+var_418]
0x180012db0  mov     qword ptr [rsp+4F8h+Source], r13
0x180012db8  mov     [rsp+4F8h+var_4A8], r14
0x180012dbd  cmp     r14, r13
0x180012dc0  jz      loc_180013106
0x180012dc6  lea     r8, aCurrent; "\\Current"
0x180012dcd  mov     rdx, r14
0x180012dd0  lea     rcx, [rsp+4F8h+lpSubKey]
0x180012dd8  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180012ddd  nop
0x180012dde  mov     [rsp+4F8h+var_4A0], 0
0x180012de7  lea     rax, [rsp+4F8h+var_4A0]
0x180012dec  mov     [rsp+4F8h+var_488], rax
0x180012df1  mov     [rsp+4F8h+var_480], 0
0x180012dfa  mov     byte ptr [rsp+4F8h+var_478], 1
0x180012e02  lea     rdx, [rsp+4F8h+lpSubKey]
0x180012e0a  cmp     [rsp+4F8h+var_380], 7
0x180012e13  cmova   rdx, [rsp+4F8h+lpSubKey]; lpSubKey
0x180012e1c  lea     rax, [rsp+4F8h+var_480]
0x180012e21  mov     [rsp+4F8h+phkResult], rax; unsigned int
0x180012e26  mov     r9d, 0F003Fh; samDesired
0x180012e2c  xor     r8d, r8d; ulOptions
0x180012e2f  mov     rcx, [rsp+4F8h+hKey]; hKey
0x180012e34  call    cs:__imp_RegOpenKeyExW
0x180012e3a  mov     rcx, [rsp+4F8h]; this
0x180012e42  test    eax, eax
0x180012e44  jz      short loc_180012E5F
0x180012e46  mov     r9d, eax; char *
0x180012e49  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x180012e50  mov     edx, 2DBh; void *
0x180012e55  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180012e5a  xor     r15b, r15b
0x180012e5d  jmp     short loc_180012E62
0x180012e5f  mov     r15b, 1
0x180012e62  lea     rcx, [rsp+4F8h+var_488]
0x180012e67  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x180012e6c  test    r15b, r15b
0x180012e6f  jz      loc_1800130C9
0x180012e75  cmp     qword ptr [r14+18h], 7
0x180012e7a  jbe     short loc_180012E81
0x180012e7c  mov     rdx, [r14]
0x180012e7f  jmp     short loc_180012E84
0x180012e81  mov     rdx, r14
0x180012e84  lea     rcx, [rsp+4F8h+var_278]
0x180012e8c  call    ?ConvertRS3DataStoreIdToItemId@CloudCacheInitializer@@CA?AVCloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@PEBG@Z; CloudCacheInitializer::ConvertRS3DataStoreIdToItemId(ushort const *)
0x180012e91  nop
0x180012e92  mov     r15, qword ptr [rsp+4F8h+var_460]
0x180012e9a  mov     rax, [r15]
0x180012e9d  mov     r12, [rax+8]
0x180012ea1  lea     rdx, [rsp+4F8h+var_1F8]
0x180012ea9  cmp     [rsp+4F8h+var_1E0], 0Fh
0x180012eb2  cmova   rdx, [rsp+4F8h+var_1F8]
0x180012ebb  lea     rcx, [rsp+4F8h+var_328]
0x180012ec3  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x180012ec8  nop
0x180012ec9  lea     r8, [rsp+4F8h+var_328]
0x180012ed1  lea     rdx, [rsp+4F8h+var_408]
0x180012ed9  mov     rcx, r15
0x180012edc  mov     rax, r12
0x180012edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ee4  nop
0x180012ee5  lea     rcx, [rsp+4F8h+var_328]; void *
0x180012eed  call    ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
0x180012ef2  lea     rcx, [rsp+4F8h+var_408]; struct bond::RuntimeSchema *
0x180012efa  call    ?GetEnableSyncOnActivityFeed@@YAEAEBVRuntimeSchema@bond@@@Z; GetEnableSyncOnActivityFeed(bond::RuntimeSchema const &)
0x180012eff  test    al, al
0x180012f01  jz      loc_180013091
0x180012f07  mov     rdx, [rsp+4F8h+var_4A0]
0x180012f0c  lea     rcx, [rsp+4F8h+var_488]
0x180012f11  call    ?LoadRS3CacheBlob@CloudCacheInitializer@@CA?AV?$versioned@Vblob@bond@@@@PEAUHKEY__@@@Z; CloudCacheInitializer::LoadRS3CacheBlob(HKEY__ *)
0x180012f16  nop
0x180012f17  cmp     [rsp+4F8h+var_478], 0
0x180012f1f  jbe     loc_18001303F
0x180012f25  mov     rcx, 0FE624E212AC18000h
0x180012f2f  add     rcx, [rsp+4F8h+var_470]
0x180012f37  mov     rax, 0D6BF94D5E57A42BDh
0x180012f41  imul    rcx
0x180012f44  add     rdx, rcx
0x180012f47  sar     rdx, 17h
0x180012f4b  mov     r9, rdx
0x180012f4e  shr     r9, 3Fh
0x180012f52  add     r9, rdx
0x180012f55  lea     r8, [rsp+4F8h+var_488]
0x180012f5a  lea     rdx, [rsp+4F8h+var_408]
0x180012f62  lea     rcx, [rsp+4F8h+var_3E8]
0x180012f6a  call    ?MakeVersionedTombstonedData@Core@Cloud@Storage@Internal@Windows@@YA?AV?$versioned@V?$tombstoned@Vschematized_data@@@@@@AEBVRuntimeSchema@bond@@AEBVblob@8@_K@Z; Windows::Internal::Storage::Cloud::Core::MakeVersionedTombstonedData(bond::RuntimeSchema const &,bond::blob const &,unsigned __int64)
0x180012f6f  nop
0x180012f70  lea     rcx, [rsp+4F8h+var_468]
0x180012f78  call    ?run_as_self@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@XZ; wil::run_as_self(void)
0x180012f7d  nop
0x180012f7e  mov     rax, [rbx]
0x180012f81  inc     [rsp+4F8h+var_284]
0x180012f88  lea     rcx, [rsp+4F8h+Destination]
0x180012f90  mov     [rsp+4F8h+phkResult], rcx
0x180012f95  mov     r9d, 1
0x180012f9b  lea     r8, [rsp+4F8h+var_278]
0x180012fa3  lea     rdx, [rsp+4F8h+var_198]
0x180012fab  mov     rcx, rbx
0x180012fae  mov     rax, [rax+18h]
0x180012fb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fb7  nop
0x180012fb8  mov     rax, [rbx]
0x180012fbb  inc     [rsp+4F8h+var_284]
0x180012fc2  lea     rcx, [rsp+4F8h+Destination]
0x180012fca  mov     [rsp+4F8h+var_4C8], rcx
0x180012fcf  mov     dword ptr [rsp+4F8h+var_4D0], 8
0x180012fd7  lea     rcx, [rsp+4F8h+var_3E8]
0x180012fdf  mov     [rsp+4F8h+phkResult], rcx; unsigned int
0x180012fe4  lea     r9, [rsp+4F8h+var_198]
0x180012fec  lea     r8, [rsp+4F8h+var_278]
0x180012ff4  lea     rdx, [rsp+4F8h+var_F8]
0x180012ffc  mov     rcx, rbx
0x180012fff  mov     rax, [rax+30h]
0x180013003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013008  lea     rcx, [rsp+4F8h+var_E8]; this
0x180013010  call    ??1Entry@CurrentCache@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry(void)
0x180013015  nop
0x180013016  lea     rcx, [rsp+4F8h+var_188]; this
0x18001301e  call    ??1Entry@CurrentCache@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CurrentCache::Entry::~Entry(void)
0x180013023  nop
0x180013024  lea     rcx, [rsp+4F8h+var_468]
0x18001302c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180013031  nop
0x180013032  lea     rcx, [rsp+4F8h+var_3E8]; this
0x18001303a  call    ??1schematized_data@@QEAA@XZ; schematized_data::~schematized_data(void)
0x18001303f  xor     edx, edx
0x180013041  lea     rcx, [rsp+4F8h+var_4A0]
0x180013046  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18001304b  cmp     qword ptr [r14+18h], 7
0x180013050  jbe     short loc_180013057
0x180013052  mov     rdx, [r14]
0x180013055  jmp     short loc_18001305A
0x180013057  mov     rdx, r14; lpSubKey
0x18001305a  mov     rcx, [rsp+4F8h+hKey]; hKey
0x18001305f  call    cs:__imp_RegDeleteTreeW
0x180013065  mov     rcx, [rsp+4F8h]; this
0x18001306d  test    eax, eax
0x18001306f  jz      short loc_180013086
0x180013071  mov     r9d, eax; char *
0x180013074  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x18001307b  mov     edx, 2FDh; void *
0x180013080  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x180013085  nop
0x180013086  lea     rcx, [rsp+4F8h+var_480]; this
0x18001308b  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x180013090  nop
0x180013091  lea     rcx, [rsp+4F8h+var_3F0]; this
0x180013099  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x18001309e  nop
0x18001309f  lea     rcx, [rsp+4F8h+var_278]; this
0x1800130a7  call    ??1CloudStoreItemId@Core@Cloud@Storage@Internal@Windows@@QEAA@XZ; Windows::Internal::Storage::Cloud::Core::CloudStoreItemId::~CloudStoreItemId(void)
0x1800130ac  nop
0x1800130ad  jmp     short loc_1800130C9
0x1800130af  mov     rsi, [rsp+4F8h+var_448]
0x1800130b7  mov     rbx, [rsp+4F8h+var_498]
0x1800130bc  mov     r14, [rsp+4F8h+var_4A8]
  ... truncated ...
```
