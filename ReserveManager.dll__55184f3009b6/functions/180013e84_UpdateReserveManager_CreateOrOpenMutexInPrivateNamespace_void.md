# UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace(void)

- ea: `0x180013e84`
- end: `0x18001473a`
- name: `?CreateOrOpenMutexInPrivateNamespace@UpdateReserveManager@@AEAAJXZ`
- size: `2230`
- prototype: `__int64 __fastcall(UpdateReserveManager *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800177f8`

## callees

- `0x180003870`
- `0x180008140`
- `0x18000fafc`
- `0x180013e84`
- `0x1800248e0`
- `0x180033010`

## import_xrefs

- `ntdll!NtCreatePrivateNamespace` at `0x180014280`
- `ntdll!NtCreatePrivateNamespace` at `0x180014280`
- `ntdll!NtCreateMutant` at `0x18001443d`
- `ntdll!NtCreateMutant` at `0x18001443d`
- `ntdll!NtOpenPrivateNamespace` at `0x180014251`
- `ntdll!NtOpenPrivateNamespace` at `0x180014251`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180013ec3`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180013ec3`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180013ffe`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800143c6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180014518`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800145d6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180013ffe`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800143c6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180014518`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1800145d6`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180013f79`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014028`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001408e`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180013f79`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180014028`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001408e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001400c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001430e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001439f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013edd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013eee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f8b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013f9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001400c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014036`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014047`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014099`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800140d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014117`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014128`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001430e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001439f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800143d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800144f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014534`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800145f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014607`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014618`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800146a3`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800141f8`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800141f8`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800141b6`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800141b6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180014303`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180014394`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800144a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800144e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800145a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180014303`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x180014394`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800144a4`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800144e6`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x1800145a4`

## string_xrefs

- `0x180013efe`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013fac`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014057`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800140a8`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014138`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800142b4`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014344`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001444d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014547`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014628`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800146af`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180013ebc`: `api-ms-win-core-namespace-l1-1-0.dll`
- `0x180013f0a`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180013fb8`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014063`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x1800140b4`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014144`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x1800142c0`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014350`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014459`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014553`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180014634`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x1800146bb`: `UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace`
- `0x180013f6f`: `CreateBoundaryDescriptorW`
- `0x180013fcd`: `pfnCreateBoundaryDescriptorW = reinterpret_cast<decltype(CreateBoundaryDescriptorW)*>(GetProcAddress(hPrivateNamespaceApiSet, "CreateBoundaryDescriptorW"))`
- `0x18001401e`: `AddSIDToBoundaryDescriptor`
- `0x180014078`: `pfnAddSIDToBoundaryDescriptor = reinterpret_cast<decltype(AddSIDToBoundaryDescriptor)*>(GetProcAddress(hPrivateNamespaceApiSet, "AddSIDToBoundaryDescriptor"))`
- `0x180014084`: `DeleteBoundaryDescriptor`
- `0x1800140c9`: `pfnDeleteBoundaryDescriptor = reinterpret_cast<decltype(DeleteBoundaryDescriptor)*>(GetProcAddress(hPrivateNamespaceApiSet, "DeleteBoundaryDescriptor"))`
- `0x1800140f1`: `ReserveManager_BoundaryDescriptor`
- `0x180014159`: `BoundaryDescriptor.IsValid()`
- `0x1800146d0`: `::CreateWellKnownSid(WinBuiltinAdministratorsSid, nullptr, AdminSid, &SidSize)`
- `0x180014649`: `pfnAddSIDToBoundaryDescriptor(BoundaryDescriptor.GetMutablePointer(), AdminSid)`
- `0x180014568`: `::ConvertStringSecurityDescriptorToSecurityDescriptorW(L"O:BAG:BAD:(A;;GA;;;BA)(A;;GA;;;SY)", 1, SecurityDescriptor.GetInitPointer(), &SecDescSize)`
- `0x18001446e`: `NtCreateMutant(m_Mutex.GetInitPointer(), MutexAccess, &MutexAttributes, 0 )`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace(UpdateReserveManager *this)
{
  HMODULE Library; // rax
  HMODULE v3; // rbx
  __int64 v4; // rdi
  FARPROC ProcAddress; // rdi
  const char *v7; // rax
  FARPROC v8; // rsi
  FARPROC v9; // rax
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // r15d
  void **v14; // rsi
  int v15; // eax
  int v16; // eax
  int v17; // eax
  void *v18; // rax
  __int64 v19; // rdx
  __int64 v20; // r8
  __int64 v21; // r9
  unsigned int v22; // r14d
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  int v26; // ecx
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  __int64 v30; // rdx
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdx
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  const char *v39; // [rsp+20h] [rbp-E0h] BYREF
  const char *v40; // [rsp+28h] [rbp-D8h]
  __int64 v41; // [rsp+30h] [rbp-D0h]
  const char *v42; // [rsp+38h] [rbp-C8h]
  __int64 v43; // [rsp+40h] [rbp-C0h]
  HMODULE v44; // [rsp+48h] [rbp-B8h]
  __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v46; // [rsp+58h] [rbp-A8h]
  __int64 v47; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+68h] [rbp-98h]
  __int64 v49; // [rsp+70h] [rbp-90h]
  __int64 v50; // [rsp+78h] [rbp-88h]
  PSECURITY_DESCRIPTOR v51; // [rsp+80h] [rbp-80h]
  __int64 v52; // [rsp+88h] [rbp-78h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+C0h] [rbp-40h] BYREF
  void (__fastcall *v55)(__int64, __int64, __int64, __int64, const char *, const char *); // [rsp+C8h] [rbp-38h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+D0h] [rbp-30h] BYREF
  DWORD cbSid; // [rsp+D8h] [rbp-28h] BYREF
  ULONG SecurityDescriptorSize; // [rsp+DCh] [rbp-24h] BYREF
  _BYTE pSid[80]; // [rsp+E0h] [rbp-20h] BYREF

  v43 = -2;
  Library = LoadLibraryExW(L"api-ms-win-core-namespace-l1-1-0.dll", 0, 0);
  v3 = Library;
  v44 = Library;
  if ( !Library )
  {
    if ( !GetLastError() )
    {
      LODWORD(v4) = 14077;
LABEL_5:
      v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
      v41 = 4344;
      v42 = "hPrivateNamespaceApiSet.IsValid()";
      if ( (int)v4 > 0 )
        LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
      RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
      return (unsigned int)v4;
    }
    LODWORD(v4) = GetLastError();
    if ( (_DWORD)v4 )
      goto LABEL_5;
LABEL_120:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  ProcAddress = GetProcAddress(Library, "CreateBoundaryDescriptorW");
  if ( !ProcAddress )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_120;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4346;
    v7 = "pfnCreateBoundaryDescriptorW = reinterpret_cast<decltype(CreateBoundaryDescriptorW)*>(GetProcAddress(hPrivateNa"
         "mespaceApiSet, \"CreateBoundaryDescriptorW\"))";
LABEL_14:
    v42 = v7;
    if ( (int)v4 > 0 )
      LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
    goto LABEL_17;
  }
  v8 = GetProcAddress(v3, "AddSIDToBoundaryDescriptor");
  if ( !v8 )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_120;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4347;
    v7 = "pfnAddSIDToBoundaryDescriptor = reinterpret_cast<decltype(AddSIDToBoundaryDescriptor)*>(GetProcAddress(hPrivate"
         "NamespaceApiSet, \"AddSIDToBoundaryDescriptor\"))";
    goto LABEL_14;
  }
  v9 = GetProcAddress(v3, "DeleteBoundaryDescriptor");
  if ( !v9 )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_120;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4348;
    v7 = "pfnDeleteBoundaryDescriptor = reinterpret_cast<decltype(DeleteBoundaryDescriptor)*>(GetProcAddress(hPrivateName"
         "spaceApiSet, \"DeleteBoundaryDescriptor\"))";
    goto LABEL_14;
  }
  v55 = (void (__fastcall *)(__int64, __int64, __int64, __int64, const char *, const char *))v9;
  v54 = ((__int64 (__fastcall *)(const wchar_t *, _QWORD))ProcAddress)(L"ReserveManager_BoundaryDescriptor", 0);
  if ( !v54 )
  {
    if ( !GetLastError() )
    {
      LODWORD(v4) = 14077;
LABEL_34:
      v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
      v41 = 4355;
      v42 = "BoundaryDescriptor.IsValid()";
      if ( (int)v4 > 0 )
        LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
      RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
      if ( v54 )
      {
        v55(v54, v10, v11, v12, v39, v40);
        v54 = 0;
      }
      goto LABEL_17;
    }
    LODWORD(v4) = GetLastError();
    if ( (_DWORD)v4 )
      goto LABEL_34;
LABEL_119:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  cbSid = 68;
  if ( !CreateWellKnownSid(WinBuiltinAdministratorsSid, 0, pSid, &cbSid) )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_119;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4360;
    v42 = "::CreateWellKnownSid(WinBuiltinAdministratorsSid, nullptr, AdminSid, &SidSize)";
    if ( (int)v4 > 0 )
      LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
    if ( v54 )
    {
      v55(v54, v36, v37, v38, v39, v40);
      v54 = 0;
    }
LABEL_17:
    if ( FreeLibrary(v3) )
      return (unsigned int)v4;
LABEL_18:
    GetLastError();
    __fastfail(7u);
  }
  if ( !((unsigned int (__fastcall *)(__int64 *, _BYTE *))v8)(&v54, pSid) )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_119;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4361;
    v42 = "pfnAddSIDToBoundaryDescriptor(BoundaryDescriptor.GetMutablePointer(), AdminSid)";
    if ( (int)v4 > 0 )
      LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
    if ( v54 )
    {
      v55(v54, v33, v34, v35, v39, v40);
      v54 = 0;
    }
    goto LABEL_17;
  }
  SecurityDescriptor = 0;
  SecurityDescriptorSize = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          L"O:BAG:BAD:(A;;GA;;;BA)(A;;GA;;;SY)",
          1u,
          &SecurityDescriptor,
          &SecurityDescriptorSize) )
  {
    if ( GetLastError() )
    {
      LODWORD(v4) = GetLastError();
      if ( !(_DWORD)v4 )
        goto LABEL_121;
    }
    else
    {
      LODWORD(v4) = 14077;
    }
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4369;
    v42 = "::ConvertStringSecurityDescriptorToSecurityDescriptorW(L\"O:BAG:BAD:(A;;GA;;;BA)(A;;GA;;;SY)\", 1, SecurityDes"
          "criptor.GetInitPointer(), &SecDescSize)";
    if ( (int)v4 > 0 )
      LODWORD(v4) = (unsigned __int16)v4 | 0x80070000;
    RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
    if ( SecurityDescriptor )
    {
      if ( LocalFree(SecurityDescriptor) )
      {
        GetLastError();
        __fastfail(7u);
      }
      SecurityDescriptor = 0;
    }
    if ( v54 )
    {
      v55(v54, v30, v31, v32, v39, v40);
      v54 = 0;
    }
LABEL_99:
    if ( FreeLibrary(v3) )
      return (unsigned int)v4;
    goto LABEL_18;
  }
  v47 = 48;
  v50 = 0;
  v48 = 0;
  v49 = 0;
  v51 = SecurityDescriptor;
  v52 = 0;
  v13 = 3;
  LODWORD(v4) = 0;
  v14 = (void **)((char *)this + 1184);
  while ( 1 )
  {
    if ( *v14 )
      goto LABEL_121;
    v15 = NtOpenPrivateNamespace((char *)this + 1184, 6, 0, v54);
    if ( v15 < 0 )
    {
      v16 = v15 | 0x10000000;
      if ( (int)v4 < 0 )
        v16 = v4;
      LODWORD(v4) = v16;
      if ( *v14 )
        goto LABEL_121;
      v17 = NtCreatePrivateNamespace((char *)this + 1184, 6, &v47, v54);
      if ( v17 < 0 )
      {
        if ( v17 != -1073741771 )
        {
          v22 = v17 | 0x10000000;
          v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
          v41 = 4426;
          v42 = "((HRESULT) ((Status) | 0x10000000))";
          RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v22);
          if ( SecurityDescriptor )
          {
            if ( LocalFree(SecurityDescriptor) )
            {
              GetLastError();
              __fastfail(7u);
            }
            SecurityDescriptor = 0;
          }
          if ( v54 )
          {
            v55(v54, v23, v24, v25, v39, v40);
            v54 = 0;
          }
          if ( !FreeLibrary(v3) )
          {
            GetLastError();
            __fastfail(7u);
          }
          return v22;
        }
        --v13;
      }
    }
    v18 = *v14;
    if ( *v14 )
      break;
    if ( !v13 )
    {
      if ( (int)v4 < 0 )
      {
        v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
        v41 = 4434;
        v42 = "FirstError";
        RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v4);
        if ( SecurityDescriptor )
        {
          if ( LocalFree(SecurityDescriptor) )
          {
            GetLastError();
            __fastfail(7u);
          }
          SecurityDescriptor = 0;
        }
        if ( v54 )
        {
          v55(v54, v19, v20, v21, v39, v40);
          v54 = 0;
        }
        goto LABEL_99;
      }
LABEL_121:
      INTERNAL_ERROR_ACTION(-1073741595);
    }
  }
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 128;
  v45 = 4849736;
  v46 = L"F9F074B6-362D-4593-B6F4-B506059C34E9";
  ObjectAttributes.RootDirectory = v18;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v45;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.SecurityQualityOfService = 0;
  if ( *((_QWORD *)this + 149) )
    goto LABEL_121;
  v26 = NtCreateMutant((PHANDLE)this + 149, 0x100001u, &ObjectAttributes, 0);
  if ( v26 < 0 )
  {
    v39 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v40 = "UpdateReserveManager::CreateOrOpenMutexInPrivateNamespace";
    v41 = 4450;
    v42 = "NtCreateMutant(m_Mutex.GetInitPointer(), MutexAccess, &MutexAttributes, 0 )";
    v4 = (unsigned int)ConvertNtStatusToHResult(v26);
    RtlReportErrorOrigination(&v39, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v4);
    if ( SecurityDescriptor )
    {
      if ( LocalFree(SecurityDescriptor) )
      {
        GetLastError();
        __fastfail(7u);
      }
      SecurityDescriptor = 0;
    }
    if ( v54 )
    {
      ((void (__fastcall *)(__int64, __int64, __int64, __int64, const char *, const char *, __int64, const char *, __int64, HMODULE, __int64, const wchar_t *, __int64, __int64, __int64, __int64, PSECURITY_DESCRIPTOR, __int64, _QWORD, HANDLE))v55)(
        v54,
        v27,
        v28,
        v29,
        v39,
        v40,
        v41,
        v42,
        v43,
        v44,
        v45,
        v46,
        v47,
        v48,
        v49,
        v50,
        v51,
        v52,
        *(_QWORD *)&ObjectAttributes.Length,
        ObjectAttributes.RootDirectory);
      v54 = 0;
    }
    goto LABEL_99;
  }
  if ( SecurityDescriptor )
  {
    if ( LocalFree(SecurityDescriptor) )
    {
      GetLastError();
      __fastfail(7u);
    }
    SecurityDescriptor = 0;
  }
  if ( v54 )
  {
    ((void (*)(void))v55)();
    v54 = 0;
  }
  if ( !FreeLibrary(v3) )
  {
    GetLastError();
    __fastfail(7u);
  }
  return 0;
}

```

## disassembly

```asm
0x180013e84  push    rbp
0x180013e86  push    rbx
0x180013e87  push    rsi
0x180013e88  push    rdi
0x180013e89  push    r12
0x180013e8b  push    r13
0x180013e8d  push    r14
0x180013e8f  push    r15
0x180013e91  lea     rbp, [rsp-48h]
0x180013e96  sub     rsp, 148h
0x180013e9d  mov     [rsp+180h+var_140], 0FFFFFFFFFFFFFFFEh
0x180013ea6  mov     rax, cs:__security_cookie
0x180013ead  xor     rax, rsp
0x180013eb0  mov     [rbp+80h+var_50], rax
0x180013eb4  mov     r13, rcx
0x180013eb7  xor     r8d, r8d; dwFlags
0x180013eba  xor     edx, edx; hFile
0x180013ebc  lea     rcx, aApiMsWinCoreNa; "api-ms-win-core-namespace-l1-1-0.dll"
0x180013ec3  call    cs:__imp_LoadLibraryExW
0x180013ec9  mov     rbx, rax
0x180013ecc  mov     [rsp+180h+var_138], rax
0x180013ed1  xor     r12d, r12d
0x180013ed4  test    rax, rax
0x180013ed7  jnz     loc_180013F6F
0x180013edd  call    cs:__imp_GetLastError
0x180013ee3  test    eax, eax
0x180013ee5  jnz     short loc_180013EEE
0x180013ee7  mov     edi, 36FDh
0x180013eec  jmp     short loc_180013EFE
0x180013eee  call    cs:__imp_GetLastError
0x180013ef4  mov     edi, eax
0x180013ef6  test    eax, eax
0x180013ef8  jz      loc_180014724
0x180013efe  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180013f05  mov     [rsp+180h+var_160], rax
0x180013f0a  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x180013f11  mov     [rsp+180h+var_158], rax
0x180013f16  mov     [rsp+180h+var_150], 10F8h
0x180013f1f  lea     rax, aHprivatenamesp; "hPrivateNamespaceApiSet.IsValid()"
0x180013f26  mov     [rsp+180h+var_148], rax
0x180013f2b  test    edi, edi
0x180013f2d  jle     short loc_180013F38
0x180013f2f  movzx   edi, di
0x180013f32  or      edi, 80070000h
0x180013f38  mov     r8d, edi
0x180013f3b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013f42  lea     rcx, [rsp+180h+var_160]
0x180013f47  call    RtlReportErrorOrigination
0x180013f4c  nop
0x180013f4d  mov     eax, edi
0x180013f4f  mov     rcx, [rbp+80h+var_50]
0x180013f53  xor     rcx, rsp; StackCookie
0x180013f56  call    __security_check_cookie
0x180013f5b  add     rsp, 148h
0x180013f62  pop     r15
0x180013f64  pop     r14
0x180013f66  pop     r13
0x180013f68  pop     r12
0x180013f6a  pop     rdi
0x180013f6b  pop     rsi
0x180013f6c  pop     rbx
0x180013f6d  pop     rbp
0x180013f6e  retn
0x180013f6f  lea     rdx, aCreateboundary; "CreateBoundaryDescriptorW"
0x180013f76  mov     rcx, rbx; hModule
0x180013f79  call    cs:__imp_GetProcAddress
0x180013f7f  mov     rdi, rax
0x180013f82  test    rax, rax
0x180013f85  jnz     loc_18001401E
0x180013f8b  call    cs:__imp_GetLastError
0x180013f91  test    eax, eax
0x180013f93  jnz     short loc_180013F9C
0x180013f95  mov     edi, 36FDh
0x180013f9a  jmp     short loc_180013FAC
0x180013f9c  call    cs:__imp_GetLastError
0x180013fa2  mov     edi, eax
0x180013fa4  test    eax, eax
0x180013fa6  jz      loc_180014724
0x180013fac  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180013fb3  mov     [rsp+180h+var_160], rax
0x180013fb8  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x180013fbf  mov     [rsp+180h+var_158], rax
0x180013fc4  mov     [rsp+180h+var_150], 10FAh
0x180013fcd  lea     rax, aPfncreatebound; "pfnCreateBoundaryDescriptorW = reinterp"...
0x180013fd4  test    edi, edi
0x180013fd6  mov     [rsp+180h+var_148], rax
0x180013fdb  jle     short loc_180013FE6
0x180013fdd  movzx   edi, di
0x180013fe0  or      edi, 80070000h
0x180013fe6  mov     r8d, edi
0x180013fe9  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180013ff0  lea     rcx, [rsp+180h+var_160]
0x180013ff5  call    RtlReportErrorOrigination
0x180013ffa  nop
0x180013ffb  mov     rcx, rbx; hLibModule
0x180013ffe  call    cs:__imp_FreeLibrary
0x180014004  test    eax, eax
0x180014006  jnz     loc_180013F4D
0x18001400c  call    cs:__imp_GetLastError
0x180014012  mov     ecx, 7
0x180014017  int     29h; Win8: RtlFailFast(ecx)
0x180014019  jmp     loc_180013F4D
0x18001401e  lea     rdx, aAddsidtobounda; "AddSIDToBoundaryDescriptor"
0x180014025  mov     rcx, rbx; hModule
0x180014028  call    cs:__imp_GetProcAddress
0x18001402e  mov     rsi, rax
0x180014031  test    rax, rax
0x180014034  jnz     short loc_180014084
0x180014036  call    cs:__imp_GetLastError
0x18001403c  test    eax, eax
0x18001403e  jnz     short loc_180014047
0x180014040  mov     edi, 36FDh
0x180014045  jmp     short loc_180014057
0x180014047  call    cs:__imp_GetLastError
0x18001404d  mov     edi, eax
0x18001404f  test    eax, eax
0x180014051  jz      loc_180014724
0x180014057  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001405e  mov     [rsp+180h+var_160], rax
0x180014063  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x18001406a  mov     [rsp+180h+var_158], rax
0x18001406f  mov     [rsp+180h+var_150], 10FBh
0x180014078  lea     rax, aPfnaddsidtobou_0; "pfnAddSIDToBoundaryDescriptor = reinter"...
0x18001407f  jmp     loc_180013FD4
0x180014084  lea     rdx, aDeleteboundary; "DeleteBoundaryDescriptor"
0x18001408b  mov     rcx, rbx; hModule
0x18001408e  call    cs:__imp_GetProcAddress
0x180014094  test    rax, rax
0x180014097  jnz     short loc_1800140E7
0x180014099  call    cs:__imp_GetLastError
0x18001409f  test    eax, eax
0x1800140a1  jnz     short loc_1800140D5
0x1800140a3  mov     edi, 36FDh
0x1800140a8  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800140af  mov     [rsp+180h+var_160], rax
0x1800140b4  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x1800140bb  mov     [rsp+180h+var_158], rax
0x1800140c0  mov     [rsp+180h+var_150], 10FCh
0x1800140c9  lea     rax, aPfndeletebound; "pfnDeleteBoundaryDescriptor = reinterpr"...
0x1800140d0  jmp     loc_180013FD4
0x1800140d5  call    cs:__imp_GetLastError
0x1800140db  mov     edi, eax
0x1800140dd  test    eax, eax
0x1800140df  jz      loc_180014724
0x1800140e5  jmp     short loc_1800140A8
0x1800140e7  mov     [rbp+80h+var_C0], r12
0x1800140eb  mov     [rbp+80h+var_B8], rax
0x1800140ef  xor     edx, edx
0x1800140f1  lea     rcx, aReservemanager_2; "ReserveManager_BoundaryDescriptor"
0x1800140f8  mov     rax, rdi
0x1800140fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014100  cmp     [rbp+80h+var_C0], r12
0x180014104  jnz     loc_180014719
0x18001410a  mov     [rbp+80h+var_C0], rax
0x18001410e  test    rax, rax
0x180014111  jnz     loc_1800141A2
0x180014117  call    cs:__imp_GetLastError
0x18001411d  test    eax, eax
0x18001411f  jnz     short loc_180014128
0x180014121  mov     edi, 36FDh
0x180014126  jmp     short loc_180014138
0x180014128  call    cs:__imp_GetLastError
0x18001412e  mov     edi, eax
0x180014130  test    eax, eax
0x180014132  jz      loc_180014719
0x180014138  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001413f  mov     [rsp+180h+var_160], rax
0x180014144  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x18001414b  mov     [rsp+180h+var_158], rax
0x180014150  mov     [rsp+180h+var_150], 1103h
0x180014159  lea     rax, aBoundarydescri; "BoundaryDescriptor.IsValid()"
0x180014160  mov     [rsp+180h+var_148], rax
0x180014165  test    edi, edi
0x180014167  jle     short loc_180014172
0x180014169  movzx   edi, di
0x18001416c  or      edi, 80070000h
0x180014172  mov     r8d, edi
0x180014175  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001417c  lea     rcx, [rsp+180h+var_160]
0x180014181  call    RtlReportErrorOrigination
0x180014186  nop
0x180014187  mov     rcx, [rbp+80h+var_C0]
0x18001418b  test    rcx, rcx
0x18001418e  jz      short loc_18001419D
0x180014190  mov     rax, [rbp+80h+var_B8]
0x180014194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014199  mov     [rbp+80h+var_C0], r12
0x18001419d  jmp     loc_180013FFB
0x1800141a2  mov     [rbp+80h+cbSid], 44h ; 'D'
0x1800141a9  lea     r9, [rbp+80h+cbSid]; cbSid
0x1800141ad  lea     r8, [rbp+80h+pSid]; pSid
0x1800141b1  xor     edx, edx; DomainSid
0x1800141b3  lea     ecx, [rdx+1Ah]; WellKnownSidType
0x1800141b6  call    cs:__imp_CreateWellKnownSid
0x1800141bc  test    eax, eax
0x1800141be  jz      loc_180014692
0x1800141c4  lea     rdx, [rbp+80h+pSid]
0x1800141c8  lea     rcx, [rbp+80h+var_C0]
0x1800141cc  mov     rax, rsi
0x1800141cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800141d4  test    eax, eax
0x1800141d6  jz      loc_180014607
0x1800141dc  mov     [rbp+80h+SecurityDescriptor], r12
0x1800141e0  mov     [rbp+80h+SecurityDescriptorSize], r12d
0x1800141e4  lea     r9, [rbp+80h+SecurityDescriptorSize]; SecurityDescriptorSize
0x1800141e8  lea     r8, [rbp+80h+SecurityDescriptor]; SecurityDescriptor
0x1800141ec  mov     edx, 1; StringSDRevision
0x1800141f1  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;GA;;;BA)(A;;GA;;;SY)"
0x1800141f8  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800141fe  test    eax, eax
0x180014200  jz      loc_180014534
0x180014206  mov     [rsp+180h+var_120], 30h ; '0'
0x18001420f  mov     [rsp+180h+var_108], r12
0x180014214  mov     [rsp+180h+var_118], r12
0x180014219  mov     [rsp+180h+var_110], r12
0x18001421e  mov     rax, [rbp+80h+SecurityDescriptor]
0x180014222  mov     [rbp+80h+var_100], rax
0x180014226  mov     [rbp+80h+var_F8], r12
0x18001422a  mov     r15d, 3
0x180014230  mov     edi, r12d
0x180014233  lea     rsi, [r13+4A0h]
0x18001423a  cmp     [rsi], r12
0x18001423d  jnz     loc_18001472F
0x180014243  mov     r9, [rbp+80h+var_C0]
0x180014247  xor     r8d, r8d
0x18001424a  lea     edx, [r8+6]
0x18001424e  mov     rcx, rsi
0x180014251  call    cs:__imp_NtOpenPrivateNamespace
0x180014257  test    eax, eax
0x180014259  jns     short loc_18001429B
0x18001425b  bts     eax, 1Ch
0x18001425f  test    edi, edi
0x180014261  cmovs   eax, edi
0x180014264  mov     edi, eax
0x180014266  cmp     [rsi], r12
0x180014269  jnz     loc_18001472F
0x18001426f  mov     r9, [rbp+80h+var_C0]
0x180014273  lea     r8, [rsp+180h+var_120]
0x180014278  mov     edx, 6
0x18001427d  mov     rcx, rsi
0x180014280  call    cs:__imp_NtCreatePrivateNamespace
0x180014286  mov     r14d, eax
0x180014289  test    eax, eax
0x18001428b  jns     short loc_18001429B
0x18001428d  cmp     eax, 0C0000035h
0x180014292  jnz     loc_180014337
0x180014298  dec     r15d
0x18001429b  mov     rax, [rsi]
0x18001429e  test    rax, rax
0x1800142a1  jnz     loc_1800143E3
0x1800142a7  test    r15d, r15d
0x1800142aa  jnz     short loc_18001423A
0x1800142ac  test    edi, edi
0x1800142ae  jns     loc_18001472F
0x1800142b4  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800142bb  mov     [rsp+180h+var_160], rax
0x1800142c0  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x1800142c7  mov     [rsp+180h+var_158], rax
0x1800142cc  mov     [rsp+180h+var_150], 1152h
0x1800142d5  lea     rax, aFirsterror; "FirstError"
0x1800142dc  mov     [rsp+180h+var_148], rax
0x1800142e1  mov     r8d, edi
0x1800142e4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800142eb  lea     rcx, [rsp+180h+var_160]
0x1800142f0  call    RtlReportErrorOrigination
0x1800142f5  nop
0x1800142f6  lea     esi, [r15+7]
0x1800142fa  mov     rcx, [rbp+80h+SecurityDescriptor]; hMem
0x1800142fe  test    rcx, rcx
0x180014301  jz      short loc_18001431C
0x180014303  call    cs:__imp_LocalFree
0x180014309  test    rax, rax
0x18001430c  jz      short loc_180014318
0x18001430e  call    cs:__imp_GetLastError
0x180014314  mov     ecx, esi
0x180014316  int     29h; Win8: RtlFailFast(ecx)
0x180014318  mov     [rbp+80h+SecurityDescriptor], r12
0x18001431c  mov     rcx, [rbp+80h+var_C0]
0x180014320  test    rcx, rcx
0x180014323  jz      short loc_180014332
0x180014325  mov     rax, [rbp+80h+var_B8]
0x180014329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001432e  mov     [rbp+80h+var_C0], r12
0x180014332  jmp     loc_1800145D3
0x180014337  or      r14d, 10000000h
0x18001433e  jge     loc_18001472F
0x180014344  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001434b  mov     [rsp+180h+var_160], rax
0x180014350  lea     rax, aUpdatereservem_9; "UpdateReserveManager::CreateOrOpenMutex"...
0x180014357  mov     [rsp+180h+var_158], rax
0x18001435c  mov     [rsp+180h+var_150], 114Ah
0x180014365  lea     rax, aHresultStatus0; "((HRESULT) ((Status) | 0x10000000))"
0x18001436c  mov     [rsp+180h+var_148], rax
0x180014371  mov     r8d, r14d
0x180014374  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001437b  lea     rcx, [rsp+180h+var_160]
0x180014380  call    RtlReportErrorOrigination
0x180014385  nop
0x180014386  mov     esi, 7
0x18001438b  mov     rcx, [rbp+80h+SecurityDescriptor]; hMem
  ... truncated ...
```
