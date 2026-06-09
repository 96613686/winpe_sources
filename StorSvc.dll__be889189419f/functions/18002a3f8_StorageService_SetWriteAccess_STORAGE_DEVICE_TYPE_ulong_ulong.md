# StorageService::SetWriteAccess(_STORAGE_DEVICE_TYPE,ulong,ulong)

- ea: `0x18002a3f8`
- end: `0x18002ab68`
- name: `?SetWriteAccess@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KK@Z`
- size: `1904`
- prototype: `__int64 __fastcall(__int64, int, unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `22`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180022640`
- `0x18002a048`

## callees

- `0x180001d84`
- `0x18000d030`
- `0x180012c9c`
- `0x180012ce0`
- `0x180019db4`
- `0x18001bb98`
- `0x18001fc18`
- `0x18001fcf8`
- `0x18001fdd8`
- `0x18001feb8`
- `0x180020450`
- `0x18002113c`
- `0x180022de0`
- `0x180025274`
- `0x180025efc`
- `0x18002675c`
- `0x180027b2c`
- `0x180029654`
- `0x180029ee4`
- `0x18002a3f8`
- `0x18002b0ac`
- `0x18003e95c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a47c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002a47c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aab6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002aab6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a63c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a63c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaab`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002aaab`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18002a5d7`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x18002a5d7`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a652`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002a652`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a632`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18002a632`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a77b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002a77b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a955`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002a955`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9e0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a999`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18002a9e0`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002aa31`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002a617`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002a758`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002a617`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18002a758`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002a57f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18002a57f`

## string_xrefs

- `0x18002a89b`: `AccessFlags`
- `0x18002a8d1`: `AccessFlags`

## pseudocode

```c
// Hidden C++ exception states: #wind=253
__int64 __fastcall StorageService::SetWriteAccess(__int64 a1, int a2, unsigned int a3, unsigned int a4)
{
  unsigned int v4; // esi
  __int64 v6; // r12
  bool v8; // r14
  int ActiveDeviceInstance; // ebx
  __int64 v10; // r15
  unsigned int v11; // edx
  int v12; // r13d
  signed int NamedSecurityInfoW; // eax
  signed int LastError; // eax
  bool v15; // sf
  StorageService *v16; // rcx
  unsigned int v17; // r11d
  StorageService *v18; // rcx
  StorageService *v19; // rcx
  bool v20; // r8
  unsigned int v21; // r14d
  int v22; // eax
  __int64 v23; // rbx
  unsigned int v24; // r13d
  HKEY v25; // rsi
  StorageService *v26; // rcx
  int v27; // r15d
  LSTATUS v28; // eax
  bool v29; // sf
  LSTATUS v30; // eax
  bool v31; // sf
  __int64 v32; // r8
  LSTATUS v33; // eax
  bool v34; // sf
  int v35; // r9d
  bool v37; // [rsp+40h] [rbp-C0h]
  unsigned int v39; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbData; // [rsp+50h] [rbp-B0h] BYREF
  int v41; // [rsp+54h] [rbp-ACh] BYREF
  DWORD Type; // [rsp+58h] [rbp-A8h] BYREF
  int v43; // [rsp+5Ch] [rbp-A4h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  HKEY phkResult; // [rsp+68h] [rbp-98h] BYREF
  PSECURITY_DESCRIPTOR hMem; // [rsp+70h] [rbp-90h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+78h] [rbp-88h]
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+80h] [rbp-80h] BYREF
  PACL ppDacl[2]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR pObjectName[264]; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR PathName[264]; // [rsp+2C0h] [rbp+1C0h] BYREF
  WCHAR pszPath[264]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v4 = a4;
  v6 = a2;
  v39 = a3;
  phkResult = 0;
  hKey = 0;
  v8 = !a2 && !a3;
  v37 = v8;
  hMem = 0;
  lpCriticalSection = (LPCRITICAL_SECTION)(a1 + 1584);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1584));
  ActiveDeviceInstance = StorageService::GetActiveDeviceInstance(a1, (unsigned int)v6, a3, &v39);
  if ( ActiveDeviceInstance < 0 )
  {
    LODWORD(v10) = v39;
    goto LABEL_79;
  }
  v10 = v39;
  ActiveDeviceInstance = StorageService::CheckDeviceId(a1, (unsigned int)v6, v39);
  v41 = ActiveDeviceInstance;
  if ( ActiveDeviceInstance < 0 )
    goto LABEL_79;
  if ( (unsigned int)StorageService::CheckPresenceState(a1, (unsigned int)v6, (unsigned int)v10, 2)
    && !(unsigned int)StorageService::IsVolumeStatusSet(a1, (unsigned int)v6, (unsigned int)v10, 4) )
  {
    ActiveDeviceInstance = -2147418113;
    goto LABEL_79;
  }
  if ( !v8 && (v4 & 0x77) != 0 )
  {
    v12 = v4 & 0x10000;
    if ( (v4 & 0x10000) == 0 )
    {
      ppDacl[0] = 0;
      memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
      ActiveDeviceInstance = GetUserFolder(pObjectName, v11);
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      NamedSecurityInfoW = GetNamedSecurityInfoW(
                             pObjectName,
                             (SE_OBJECT_TYPE)(v12 + 1),
                             v12 + 4,
                             0,
                             0,
                             ppDacl,
                             0,
                             &hMem);
      ActiveDeviceInstance = NamedSecurityInfoW;
      if ( NamedSecurityInfoW > 0 )
        ActiveDeviceInstance = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      SecurityAttributes.nLength = 24;
      SecurityAttributes.bInheritHandle = 0;
      SecurityAttributes.lpSecurityDescriptor = hMem;
      ActiveDeviceInstance = StringCchCopyW(pszPath, 0x104u, pObjectName);
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      PathStripPathW(pszPath);
      ActiveDeviceInstance = StringCchCopyW(
                               PathName,
                               0x104u,
                               (const wchar_t *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112 * v10 + 4));
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      ActiveDeviceInstance = PathCchAppend(PathName, 0x104u, pszPath);
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      if ( !CreateDirectoryW(PathName, &SecurityAttributes) )
      {
        LastError = GetLastError();
        ActiveDeviceInstance = LastError;
        if ( LastError == 183 )
        {
          if ( (GetFileAttributesW(PathName) & 0x10) == 0 )
          {
            ActiveDeviceInstance = -2147024891;
            goto LABEL_79;
          }
          ActiveDeviceInstance = StorageService::ApplyFolderDacl((StorageService *)a1, PathName, ppDacl[0]);
          v15 = ActiveDeviceInstance < 0;
        }
        else
        {
          if ( LastError > 0 )
            ActiveDeviceInstance = (unsigned __int16)LastError | 0x80070000;
          v15 = ActiveDeviceInstance < 0;
        }
        if ( v15 )
          goto LABEL_79;
      }
      ActiveDeviceInstance = StorageService::ProvisionStorageCardForUser(
                               (StorageService *)a1,
                               v6,
                               v10,
                               (__int64)pObjectName,
                               (__int64)pszPath,
                               v4,
                               &SecurityAttributes,
                               ppDacl[0]);
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
      ActiveDeviceInstance = StorageService::SetLibraries(v16, PathName, v4, 1);
      v41 = ActiveDeviceInstance;
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_79;
    }
    if ( (v4 & 0x10) != 0 )
    {
      if ( !(unsigned int)StorageService::SupportsAppXInstall(a1, (unsigned int)v6, (unsigned int)v10) )
      {
        ActiveDeviceInstance = -2147024846;
        goto LABEL_79;
      }
      ActiveDeviceInstance = StringCchCopyW(
                               pObjectName,
                               0x104u,
                               (const wchar_t *)(1112 * v10 + *(_QWORD *)(a1 + 8 * v6 + 40) + 4LL));
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_78;
      ActiveDeviceInstance = PathCchAppend(pObjectName, v17, L"WindowsApps");
      if ( ActiveDeviceInstance < 0 )
        goto LABEL_78;
      if ( StorageService::DirectoryIsReparsePoint(v18, pObjectName) && !DeleteFileW(pObjectName) )
      {
        ActiveDeviceInstance = -2147024814;
        goto LABEL_78;
      }
      ActiveDeviceInstance = StorageService::CreateStorageCardDirectory(
                               (StorageService *)a1,
                               v6,
                               v10,
                               (__int64)L"WindowsApps",
                               1,
                               0,
                               0,
                               0);
      if ( ActiveDeviceInstance < 0
        || (ActiveDeviceInstance = StorageService::PairStorageCardForApps(
                                     a1,
                                     (unsigned int)v6,
                                     (unsigned int)v10,
                                     v12 != 0),
            v41 = ActiveDeviceInstance,
            ActiveDeviceInstance < 0) )
      {
LABEL_78:
        v4 = a4;
        goto LABEL_79;
      }
      StorageService::SetStorageCardPowerPolicy(a1, (unsigned int)v6, (unsigned int)v10);
      if ( StringCchPrintfW(
             pszPath,
             0x104u,
             L"\\\\.\\%c:",
             *(unsigned __int16 *)(1112 * v10 + *(_QWORD *)(a1 + 8 * v6 + 40) + 4)) >= 0 )
      {
        *(_OWORD *)&SecurityAttributes.nLength = *(_OWORD *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112 * v10 + 548);
        SetStorageCardWriteBackCache(pszPath, (GUID *)&SecurityAttributes, v20);
      }
      StorageService::ChangeServiceStartSettings(v19);
      v4 = a4;
    }
  }
  if ( (v4 & 0x10000) == 0 )
  {
    v21 = 0;
    LOBYTE(v22) = 0;
    v43 = 0;
    v23 = v39;
    while ( 1 )
    {
      ppDacl[0] = (PACL)0x3300320031LL;
      v24 = 1 << v22;
      if ( ((1 << v22) & 0x10) != 0 )
      {
        v25 = hKey;
        if ( hKey )
          goto LABEL_53;
        hKey = 0;
        if ( (int)OpenStorageRegKey(HKEY_LOCAL_MACHINE, (wchar_t *)L"AccessFlags", &hKey) >= 0 )
        {
          v25 = hKey;
          goto LABEL_53;
        }
      }
      else
      {
        v25 = phkResult;
        if ( phkResult )
          goto LABEL_53;
        phkResult = 0;
        if ( (int)OpenStorageRegKey(HKEY_CURRENT_USER, (wchar_t *)L"AccessFlags", &phkResult) >= 0 )
        {
          v25 = phkResult;
LABEL_53:
          if ( StringCchPrintfW((unsigned __int16 *)ppDacl, 4u, L"%02d", v24) >= 0 )
          {
            v27 = a4 & v24;
            if ( v37 || !v27 )
            {
              *(_OWORD *)&SecurityAttributes.nLength = 0;
              Type = 0;
              cbData = 0;
              v28 = RegQueryValueExW(v25, (LPCWSTR)ppDacl, 0, &Type, 0, &cbData);
              v29 = v28 < 0;
              if ( v28 > 0 )
                v29 = 1;
              if ( !v29 && cbData == 16 )
              {
                v30 = RegQueryValueExW(v25, (LPCWSTR)ppDacl, 0, &Type, (LPBYTE)&SecurityAttributes, &cbData);
                v31 = v30 < 0;
                if ( v30 > 0 )
                  v31 = 1;
                if ( !v31 )
                {
                  if ( v37 && v27
                    || (v32 = *(_QWORD *)(a1 + 8 * v6 + 40),
                        *(_QWORD *)&SecurityAttributes.nLength == *(_QWORD *)(v32 + 1112 * v23 + 548))
                    && SecurityAttributes.lpSecurityDescriptor == *(LPVOID *)(v32 + 1112 * v23 + 556) )
                  {
                    v33 = RegDeleteValueW(v25, (LPCWSTR)ppDacl);
                    v34 = v33 < 0;
                    if ( v33 > 0 )
                      v34 = 1;
                    if ( !v34 )
                      v21 |= v24;
                  }
                }
              }
            }
            else
            {
              RegSetValueExW(
                v25,
                (LPCWSTR)ppDacl,
                0,
                3u,
                (const BYTE *)(*(_QWORD *)(a1 + 8 * v6 + 40) + 1112 * v23 + 548),
                0x10u);
            }
          }
        }
      }
      v22 = v43 + 1;
      v43 = v22;
      if ( v22 >= 8 )
      {
        ActiveDeviceInstance = v41;
        if ( (v21 & 0x27) == 0
          || (ActiveDeviceInstance = StorageService::SetLibraries(
                                       v26,
                                       (const unsigned __int16 *)(*(_QWORD *)(a1 + 40) + 4LL),
                                       v21,
                                       0),
              ActiveDeviceInstance >= 0) )
        {
          if ( (v21 & 0x10) != 0 )
            ActiveDeviceInstance = StorageService::PairStorageCardForApps(a1, 0, 0, 0);
        }
        LODWORD(v10) = v39;
        goto LABEL_78;
      }
    }
  }
LABEL_79:
  if ( hMem )
    LocalFree(hMem);
  LeaveCriticalSection(lpCriticalSection);
  if ( ActiveDeviceInstance < 0 && (unsigned int)dword_1800BF000 > 5 )
  {
    v43 = ActiveDeviceInstance;
    Type = v4;
    v41 = v10;
    cbData = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)byte_1800A76BB,
      0,
      v35,
      (__int64)&cbData,
      (__int64)&v41,
      (__int64)&Type,
      (__int64)&v43);
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (unsigned int)ActiveDeviceInstance;
}

```

## disassembly

```asm
0x18002a3f8  mov     [rsp-8+arg_18], rbx
0x18002a3fd  push    rbp
0x18002a3fe  push    rsi
0x18002a3ff  push    rdi
0x18002a400  push    r12
0x18002a402  push    r13
0x18002a404  push    r14
0x18002a406  push    r15
0x18002a408  lea     rbp, [rsp-5F0h]
0x18002a410  sub     rsp, 6F0h
0x18002a417  mov     rax, cs:__security_cookie
0x18002a41e  xor     rax, rsp
0x18002a421  mov     [rbp+620h+var_40], rax
0x18002a428  mov     esi, r9d
0x18002a42b  mov     [rsp+720h+var_6DC], r9d
0x18002a430  mov     ebx, r8d
0x18002a433  movsxd  r12, edx
0x18002a436  mov     rdi, rcx
0x18002a439  mov     [rsp+720h+var_6D8], ebx
0x18002a43d  mov     [rsp+720h+phkResult], 0
0x18002a446  mov     [rsp+720h+hKey], 0
0x18002a44f  test    edx, edx
0x18002a451  jnz     short loc_18002A45C
0x18002a453  test    ebx, ebx
0x18002a455  jnz     short loc_18002A45C
0x18002a457  mov     r14b, 1
0x18002a45a  jmp     short loc_18002A45F
0x18002a45c  xor     r14b, r14b
0x18002a45f  mov     [rsp+720h+var_6E0], r14b
0x18002a464  mov     [rsp+720h+hMem], 0
0x18002a46d  lea     rax, [rcx+630h]
0x18002a474  mov     [rsp+720h+lpCriticalSection], rax
0x18002a479  mov     rcx, rax; lpCriticalSection
0x18002a47c  call    cs:__imp_EnterCriticalSection
0x18002a482  lea     r9, [rsp+720h+var_6D8]
0x18002a487  mov     r8d, ebx
0x18002a48a  mov     edx, r12d
0x18002a48d  mov     rcx, rdi
0x18002a490  call    ?GetActiveDeviceInstance@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAK@Z; StorageService::GetActiveDeviceInstance(_STORAGE_DEVICE_TYPE,ulong,ulong *)
0x18002a495  mov     ebx, eax
0x18002a497  test    eax, eax
0x18002a499  js      loc_18002AB5D
0x18002a49f  mov     r15d, [rsp+720h+var_6D8]
0x18002a4a4  mov     r8d, r15d
0x18002a4a7  mov     edx, r12d
0x18002a4aa  mov     rcx, rdi
0x18002a4ad  call    ?CheckDeviceId@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::CheckDeviceId(_STORAGE_DEVICE_TYPE,ulong)
0x18002a4b2  mov     ebx, eax
0x18002a4b4  mov     [rsp+720h+var_6CC], eax
0x18002a4b8  test    eax, eax
0x18002a4ba  js      loc_18002AAA1
0x18002a4c0  mov     r9d, 2
0x18002a4c6  mov     r8d, r15d
0x18002a4c9  mov     edx, r12d
0x18002a4cc  mov     rcx, rdi
0x18002a4cf  call    ?CheckPresenceState@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KW4_STORAGE_PRESENCE_STATE@@@Z; StorageService::CheckPresenceState(_STORAGE_DEVICE_TYPE,ulong,_STORAGE_PRESENCE_STATE)
0x18002a4d4  test    eax, eax
0x18002a4d6  jz      short loc_18002A4FA
0x18002a4d8  mov     r9d, 4
0x18002a4de  mov     r8d, r15d
0x18002a4e1  mov     edx, r12d
0x18002a4e4  mov     rcx, rdi
0x18002a4e7  call    ?IsVolumeStatusSet@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@KK@Z; StorageService::IsVolumeStatusSet(_STORAGE_DEVICE_TYPE,ulong,ulong)
0x18002a4ec  test    eax, eax
0x18002a4ee  jnz     short loc_18002A4FA
0x18002a4f0  mov     ebx, 8000FFFFh
0x18002a4f5  jmp     loc_18002AAA1
0x18002a4fa  test    r14b, r14b
0x18002a4fd  jnz     loc_18002A851
0x18002a503  test    sil, 77h
0x18002a507  jz      loc_18002A851
0x18002a50d  mov     r13d, esi
0x18002a510  mov     r14d, 104h
0x18002a516  and     r13d, 10000h
0x18002a51d  jnz     loc_18002A6F5
0x18002a523  mov     [rbp+620h+var_680], 0
0x18002a52b  xorps   xmm0, xmm0
0x18002a52e  xor     eax, eax
0x18002a530  movups  xmmword ptr [rbp+620h+SecurityAttributes.nLength], xmm0
0x18002a534  mov     qword ptr [rbp+620h+SecurityAttributes.bInheritHandle], rax
0x18002a538  lea     rcx, [rbp+620h+pObjectName]; wchar_t *
0x18002a53c  call    ?GetUserFolder@@YAJPEAGK@Z; GetUserFolder(ushort *,ulong)
0x18002a541  mov     ebx, eax
0x18002a543  test    eax, eax
0x18002a545  js      loc_18002AAA1
0x18002a54b  lea     rax, [rsp+720h+hMem]
0x18002a550  mov     [rsp+720h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18002a555  mov     [rsp+720h+ppSacl], 0; ppSacl
0x18002a55e  lea     rax, [rbp+620h+var_680]
0x18002a562  mov     [rsp+720h+ppDacl], rax; ppDacl
0x18002a567  mov     [rsp+720h+ppsidGroup], 0; ppsidGroup
0x18002a570  xor     r9d, r9d; ppsidOwner
0x18002a573  lea     edx, [r13+1]; ObjectType
0x18002a577  lea     r8d, [r13+4]; SecurityInfo
0x18002a57b  lea     rcx, [rbp+620h+pObjectName]; pObjectName
0x18002a57f  call    cs:__imp_GetNamedSecurityInfoW
0x18002a585  mov     ebx, eax
0x18002a587  test    eax, eax
0x18002a589  jle     short loc_18002A594
0x18002a58b  movzx   ebx, ax
0x18002a58e  or      ebx, 80070000h
0x18002a594  test    ebx, ebx
0x18002a596  js      loc_18002AAA1
0x18002a59c  mov     [rbp+620h+SecurityAttributes.nLength], 18h
0x18002a5a3  mov     [rbp+620h+SecurityAttributes.bInheritHandle], 0
0x18002a5aa  mov     rax, [rsp+720h+hMem]
0x18002a5af  mov     [rbp+620h+SecurityAttributes.lpSecurityDescriptor], rax
0x18002a5b3  lea     r8, [rbp+620h+pObjectName]; wchar_t *
0x18002a5b7  mov     rdx, r14; unsigned __int64
0x18002a5ba  lea     rcx, [rbp+620h+pszPath]; wchar_t *
0x18002a5c1  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a5c6  mov     ebx, eax
0x18002a5c8  test    eax, eax
0x18002a5ca  js      loc_18002AAA1
0x18002a5d0  lea     rcx, [rbp+620h+pszPath]; pszPath
0x18002a5d7  call    cs:__imp_PathStripPathW
0x18002a5dd  imul    r8, r15, 458h
0x18002a5e4  add     r8, 4
0x18002a5e8  add     r8, [rdi+r12*8+28h]; wchar_t *
0x18002a5ed  mov     rdx, r14; unsigned __int64
0x18002a5f0  lea     rcx, [rbp+620h+PathName]; wchar_t *
0x18002a5f7  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a5fc  mov     ebx, eax
0x18002a5fe  test    eax, eax
0x18002a600  js      loc_18002AAA1
0x18002a606  lea     r8, [rbp+620h+pszPath]; pszMore
0x18002a60d  mov     rdx, r14; cchPath
0x18002a610  lea     rcx, [rbp+620h+PathName]; pszPath
0x18002a617  call    cs:__imp_PathCchAppend
0x18002a61d  mov     ebx, eax
0x18002a61f  test    eax, eax
0x18002a621  js      loc_18002AAA1
0x18002a627  lea     rdx, [rbp+620h+SecurityAttributes]; lpSecurityAttributes
0x18002a62b  lea     rcx, [rbp+620h+PathName]; lpPathName
0x18002a632  call    cs:__imp_CreateDirectoryW
0x18002a638  test    eax, eax
0x18002a63a  jnz     short loc_18002A694
0x18002a63c  call    cs:__imp_GetLastError
0x18002a642  mov     ebx, eax
0x18002a644  cmp     eax, 0B7h
0x18002a649  jnz     short loc_18002A67F
0x18002a64b  lea     rcx, [rbp+620h+PathName]; lpFileName
0x18002a652  call    cs:__imp_GetFileAttributesW
0x18002a658  test    al, 10h
0x18002a65a  jnz     short loc_18002A666
0x18002a65c  mov     ebx, 80070005h
0x18002a661  jmp     loc_18002AAA1
0x18002a666  mov     r8, [rbp+620h+var_680]; struct _ACL *
0x18002a66a  lea     rdx, [rbp+620h+PathName]; unsigned __int16 *
0x18002a671  mov     rcx, rdi; this
0x18002a674  call    ?ApplyFolderDacl@StorageService@@AEAAJPEAGPEAU_ACL@@@Z; StorageService::ApplyFolderDacl(ushort *,_ACL *)
0x18002a679  mov     ebx, eax
0x18002a67b  test    eax, eax
0x18002a67d  jmp     short loc_18002A68E
0x18002a67f  test    eax, eax
0x18002a681  jle     short loc_18002A68C
0x18002a683  movzx   ebx, ax
0x18002a686  or      ebx, 80070000h
0x18002a68c  test    ebx, ebx
0x18002a68e  js      loc_18002AAA1
0x18002a694  mov     rax, [rbp+620h+var_680]
0x18002a698  mov     [rsp+720h+ppSecurityDescriptor], rax
0x18002a69d  lea     rax, [rbp+620h+SecurityAttributes]
0x18002a6a1  mov     [rsp+720h+ppSacl], rax
0x18002a6a6  mov     dword ptr [rsp+720h+ppDacl], esi
0x18002a6aa  lea     rax, [rbp+620h+pszPath]
0x18002a6b1  mov     [rsp+720h+ppsidGroup], rax
0x18002a6b6  lea     r9, [rbp+620h+pObjectName]
0x18002a6ba  mov     r8d, r15d
0x18002a6bd  mov     edx, r12d
0x18002a6c0  mov     rcx, rdi
0x18002a6c3  call    ?ProvisionStorageCardForUser@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEAG1KPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@@Z; StorageService::ProvisionStorageCardForUser(_STORAGE_DEVICE_TYPE,ulong,ushort *,ushort *,ulong,_SECURITY_ATTRIBUTES *,_ACL *)
0x18002a6c8  mov     ebx, eax
0x18002a6ca  test    eax, eax
0x18002a6cc  js      loc_18002AAA1
0x18002a6d2  mov     r9d, 1; int
0x18002a6d8  mov     r8d, esi; unsigned int
0x18002a6db  lea     rdx, [rbp+620h+PathName]; unsigned __int16 *
0x18002a6e2  call    ?SetLibraries@StorageService@@IEAAJPEBGKH@Z; StorageService::SetLibraries(ushort const *,ulong,int)
0x18002a6e7  mov     ebx, eax
0x18002a6e9  mov     [rsp+720h+var_6CC], eax
0x18002a6ed  test    eax, eax
0x18002a6ef  js      loc_18002AAA1
0x18002a6f5  test    sil, 10h
0x18002a6f9  jz      loc_18002A851
0x18002a6ff  mov     r8d, r15d
0x18002a702  mov     edx, r12d
0x18002a705  mov     rcx, rdi
0x18002a708  call    ?SupportsAppXInstall@StorageService@@IEAAHW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SupportsAppXInstall(_STORAGE_DEVICE_TYPE,ulong)
0x18002a70d  test    eax, eax
0x18002a70f  jnz     short loc_18002A71B
0x18002a711  mov     ebx, 80070032h
0x18002a716  jmp     loc_18002AAA1
0x18002a71b  imul    r14, r15, 458h
0x18002a722  mov     r8, [rdi+r12*8+28h]
0x18002a727  add     r8, 4
0x18002a72b  add     r8, r14; wchar_t *
0x18002a72e  mov     r11d, 104h
0x18002a734  mov     edx, r11d; unsigned __int64
0x18002a737  lea     rcx, [rbp+620h+pObjectName]; wchar_t *
0x18002a73b  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x18002a740  mov     ebx, eax
0x18002a742  test    eax, eax
0x18002a744  js      loc_18002AA9D
0x18002a74a  lea     r8, aWindowsapps; "WindowsApps"
0x18002a751  mov     edx, r11d; cchPath
0x18002a754  lea     rcx, [rbp+620h+pObjectName]; pszPath
0x18002a758  call    cs:__imp_PathCchAppend
0x18002a75e  mov     ebx, eax
0x18002a760  test    eax, eax
0x18002a762  js      loc_18002AA9D
0x18002a768  lea     rdx, [rbp+620h+pObjectName]; unsigned __int16 *
0x18002a76c  call    ?DirectoryIsReparsePoint@StorageService@@AEAAHPEBG@Z; StorageService::DirectoryIsReparsePoint(ushort const *)
0x18002a771  xor     ebx, ebx
0x18002a773  test    eax, eax
0x18002a775  jz      short loc_18002A78F
0x18002a777  lea     rcx, [rbp+620h+pObjectName]; lpFileName
0x18002a77b  call    cs:__imp_DeleteFileW
0x18002a781  test    eax, eax
0x18002a783  jnz     short loc_18002A78F
0x18002a785  mov     ebx, 80070052h
0x18002a78a  jmp     loc_18002AA9D
0x18002a78f  mov     dword ptr [rsp+720h+ppSecurityDescriptor], ebx
0x18002a793  mov     [rsp+720h+ppSacl], rbx
0x18002a798  mov     [rsp+720h+ppDacl], rbx
0x18002a79d  mov     dword ptr [rsp+720h+ppsidGroup], 1
0x18002a7a5  lea     r9, aWindowsapps; "WindowsApps"
0x18002a7ac  mov     r8d, r15d
0x18002a7af  mov     edx, r12d
0x18002a7b2  mov     rcx, rdi
0x18002a7b5  call    ?CreateStorageCardDirectory@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEBGKPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@H@Z; StorageService::CreateStorageCardDirectory(_STORAGE_DEVICE_TYPE,ulong,ushort const *,ulong,_SECURITY_ATTRIBUTES *,_ACL *,int)
0x18002a7ba  mov     ebx, eax
0x18002a7bc  test    eax, eax
0x18002a7be  js      loc_18002AA9D
0x18002a7c4  xor     r9d, r9d
0x18002a7c7  test    r13d, r13d
0x18002a7ca  setnz   r9b
0x18002a7ce  mov     r8d, r15d
0x18002a7d1  mov     edx, r12d
0x18002a7d4  mov     rcx, rdi
0x18002a7d7  call    ?PairStorageCardForApps@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KH@Z; StorageService::PairStorageCardForApps(_STORAGE_DEVICE_TYPE,ulong,int)
0x18002a7dc  mov     ebx, eax
0x18002a7de  mov     [rsp+720h+var_6CC], eax
0x18002a7e2  test    eax, eax
0x18002a7e4  js      loc_18002AA9D
0x18002a7ea  mov     r8d, r15d
0x18002a7ed  mov     edx, r12d
0x18002a7f0  mov     rcx, rdi
0x18002a7f3  call    ?SetStorageCardPowerPolicy@StorageService@@IEAAXW4_STORAGE_DEVICE_TYPE@@K@Z; StorageService::SetStorageCardPowerPolicy(_STORAGE_DEVICE_TYPE,ulong)
0x18002a7f8  mov     rax, [rdi+r12*8+28h]
0x18002a7fd  movzx   r9d, word ptr [r14+rax+4]
0x18002a803  lea     r8, aC; "\\\\.\\%c:"
0x18002a80a  mov     edx, 104h; unsigned __int64
0x18002a80f  lea     rcx, [rbp+620h+pszPath]; unsigned __int16 *
0x18002a816  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002a81b  test    eax, eax
0x18002a81d  js      short loc_18002A848
0x18002a81f  imul    rcx, r15, 458h
0x18002a826  mov     rax, [rdi+r12*8+28h]
0x18002a82b  movups  xmm0, xmmword ptr [rax+rcx+224h]
0x18002a833  movdqu  xmmword ptr [rbp+620h+SecurityAttributes.nLength], xmm0
0x18002a838  lea     rdx, [rbp+620h+SecurityAttributes]; rguid
0x18002a83c  lea     rcx, [rbp+620h+pszPath]; unsigned __int16 *
0x18002a843  call    ?SetStorageCardWriteBackCache@@YAJPEBGU_GUID@@_N@Z; SetStorageCardWriteBackCache(ushort const *,_GUID,bool)
0x18002a848  call    ?ChangeServiceStartSettings@StorageService@@IEAAXXZ; StorageService::ChangeServiceStartSettings(void)
0x18002a84d  mov     esi, [rsp+720h+var_6DC]
0x18002a851  bt      esi, 10h
0x18002a855  jb      loc_18002AAA1
0x18002a85b  xor     r14d, r14d
0x18002a85e  xor     eax, eax
0x18002a860  mov     [rsp+720h+var_6C4], eax
0x18002a864  mov     ebx, [rsp+720h+var_6D8]
0x18002a868  mov     rcx, 3300320031h
0x18002a872  mov     [rbp+620h+var_680], rcx
0x18002a876  mov     ecx, eax
0x18002a878  mov     r13d, 1
0x18002a87e  shl     r13d, cl
0x18002a881  test    r13b, 10h
0x18002a885  jz      short loc_18002A8BD
0x18002a887  mov     rsi, [rsp+720h+hKey]
0x18002a88c  test    rsi, rsi
0x18002a88f  jnz     short loc_18002A8F1
0x18002a891  mov     [rsp+720h+hKey], rsi
0x18002a896  lea     r8, [rsp+720h+hKey]; phkResult
0x18002a89b  lea     rdx, aAccessflags; "AccessFlags"
0x18002a8a2  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002a8a9  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18002a8ae  test    eax, eax
0x18002a8b0  js      loc_18002AA4A
0x18002a8b6  mov     rsi, [rsp+720h+hKey]
0x18002a8bb  jmp     short loc_18002A8F1
0x18002a8bd  mov     rsi, [rsp+720h+phkResult]
0x18002a8c2  test    rsi, rsi
0x18002a8c5  jnz     short loc_18002A8F1
0x18002a8c7  mov     [rsp+720h+phkResult], rsi
0x18002a8cc  lea     r8, [rsp+720h+phkResult]; phkResult
0x18002a8d1  lea     rdx, aAccessflags; "AccessFlags"
0x18002a8d8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18002a8df  call    ?OpenStorageRegKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@@Z; OpenStorageRegKey(HKEY__ *,ushort const *,HKEY__ * *)
0x18002a8e4  test    eax, eax
  ... truncated ...
```
