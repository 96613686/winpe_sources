# Container::Manager::Core::Details::ApplyRegistryOverrides(Csl::Path const &,utl::vector<Container::Manager::Core::Details::RegistryKey,utl::allocator<Container::Manager::Core::Details::RegistryKey>> const &)

- ea: `0x18010b5b0`
- end: `0x18010be1d`
- name: `?ApplyRegistryOverrides@Details@Core@Manager@Container@@YAJAEBVPath@Csl@@AEBV?$vector@URegistryKey@Details@Core@Manager@Container@@V?$allocator@URegistryKey@Details@Core@Manager@Container@@@utl@@@utl@@@Z`
- size: `2157`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800c467c`

## callees

- `0x180004fc4`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x18000dad8`
- `0x180016774`
- `0x18002fae4`
- `0x18002ff9c`
- `0x1800493c8`
- `0x18010a5e4`
- `0x18010b5b0`
- `0x1801911c0`
- `0x180197498`
- `0x180198db0`
- `0x1801994e8`
- `0x180199f54`
- `0x18019a018`
- `0x18019a294`
- `0x1801a2a90`
- `0x1801a3558`
- `0x1801a4010`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x18010b744`
- `ntdll!RtlAcquirePrivilege` at `0x18010b744`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b8ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010b8ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010b8ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18010b8ed`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010b892`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010bb06`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010b892`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18010bb06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b8df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010bb4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010bd15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010b8df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010bb4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010bd15`

## string_xrefs

- `0x18010b75b`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x18010b63a`: `Windows\System32\Config`
- `0x18010b96a`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18010bb1f`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`
- `0x18010bb75`: `onecore\base\gendrv\silos\csl\lib\cslofflineregistry.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Container::Manager::Core::Details::ApplyRegistryOverrides(_QWORD *a1, int **a2)
{
  int **v2; // r14
  __int64 v3; // rdx
  void *v4; // rcx
  void **v5; // r8
  _QWORD *v6; // rcx
  int *v7; // rbx
  int *v8; // rdi
  void **v9; // rdx
  void **v10; // rax
  int v11; // r10d
  __int64 v12; // r9
  NTSTATUS v13; // eax
  int v14; // eax
  int LastError; // ebx
  void *v16; // rcx
  _QWORD *v18; // rsi
  __int64 v19; // rdx
  HANDLE FileW; // rax
  bool v21; // r8
  const char *v22; // r9
  void *v23; // rdi
  int v24; // eax
  const struct Path *v25; // rdx
  DWORD v26; // ebx
  int *v27; // rdi
  int *v28; // r15
  __int64 v29; // r14
  unsigned int v30; // eax
  char v31; // r14
  __int64 v32; // rbx
  __int64 v33; // r14
  int v34; // r13d
  __int64 v35; // rdx
  const unsigned __int8 *v36; // r9
  __int64 v37; // rax
  HANDLE v38; // rax
  const char *v39; // r9
  void *v40; // rdi
  unsigned int v41; // eax
  unsigned __int64 v42; // rcx
  _QWORD *v43; // rax
  unsigned __int64 v44; // rax
  __int64 v45; // rdx
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-99h]
  void *v47; // [rsp+40h] [rbp-79h] BYREF
  char *v48; // [rsp+48h] [rbp-71h]
  _WORD v49[8]; // [rsp+50h] [rbp-69h] BYREF
  const wchar_t *v50; // [rsp+60h] [rbp-59h] BYREF
  __int64 v51; // [rsp+68h] [rbp-51h]
  LPCWSTR lpFileName[2]; // [rsp+70h] [rbp-49h] BYREF
  _WORD v53[8]; // [rsp+80h] [rbp-39h] BYREF
  _QWORD v54[2]; // [rsp+90h] [rbp-29h] BYREF
  _QWORD *v55; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h]
  _QWORD v57[12]; // [rsp+B0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]
  __int64 Privilege; // [rsp+120h] [rbp+67h] BYREF
  int **v60; // [rsp+128h] [rbp+6Fh]
  PVOID ReturnedState; // [rsp+130h] [rbp+77h] BYREF
  __int64 v62; // [rsp+138h] [rbp+7Fh]

  v60 = a2;
  v2 = a2;
  v47 = v49;
  v48 = (char *)v49;
  v49[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           &v47,
                           *a1,
                           (__int64)(a1[1] - *a1) >> 1) )
  {
    v3 = 1222;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
      (const char *)0x8007000ELL,
      dwCreationDisposition);
    goto LABEL_4;
  }
  v50 = L"Windows\\System32\\Config";
  v51 = 23;
  if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)&v47) )
  {
    v3 = 1223;
    goto LABEL_3;
  }
  v5 = (void **)v54;
  v54[0] = v54;
  v6 = v54;
  v54[1] = v54;
  v55 = v54;
  v56 = 0;
  v7 = *v2;
  v8 = v2[1];
  while ( v7 != v8 )
  {
    if ( v6 == v54 )
      goto LABEL_18;
    v9 = (void **)v54;
    v10 = v5;
    v11 = *v7;
    do
    {
      if ( *((_DWORD *)v10 + 6) < v11 )
      {
        v12 = 2;
      }
      else
      {
        v9 = v10;
        v12 = 1;
      }
      v10 = (void **)v10[v12];
    }
    while ( v10 != &utl::_TreeSentinel );
    if ( v9 == v54 || v11 < *((_DWORD *)v9 + 6) )
    {
LABEL_18:
      utl::_Tree<enum Container::Manager::Core::Details::RegistryKey::Hive,enum Container::Manager::Core::Details::RegistryKey::Hive,utl::less<enum Container::Manager::Core::Details::RegistryKey::Hive>,utl::allocator<enum Container::Manager::Core::Details::RegistryKey::Hive>,0>::emplace<enum Container::Manager::Core::Details::RegistryKey::Hive const &,0>(
        v54,
        v57,
        v7);
      if ( !v57[0] )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4D0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
          (const char *)0x8007000ELL,
          dwCreationDisposition);
        utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
LABEL_4:
        v4 = v47;
        if ( v47 != v49 )
LABEL_118:
          operator delete(v4, (const struct std::nothrow_t *)&std::nothrow);
        return 2147942414LL;
      }
      v6 = v55;
      v5 = (void **)v54[0];
    }
    v7 += 16;
  }
  ReturnedState = 0;
  Privilege = 0x1200000011LL;
  v13 = RtlAcquirePrivilege((PULONG)&Privilege, 2u, 0, &ReturnedState);
  if ( v13 < 0 )
  {
    v14 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)0x52,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
            (const char *)(unsigned int)v13,
            dwCreationDisposition);
    LastError = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4D8,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
        (const char *)(unsigned int)v14,
        dwCreationDisposition);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
      v16 = v47;
      if ( v47 != v49 )
        goto LABEL_25;
      return (unsigned int)LastError;
    }
  }
  v18 = v55;
  while ( 1 )
  {
    if ( v18 == v54 )
    {
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
      if ( v47 != v49 )
        operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    lpFileName[0] = v53;
    lpFileName[1] = v53;
    v53[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             lpFileName,
                             v47,
                             (v48 - (_BYTE *)v47) >> 1) )
    {
      v19 = 1246;
LABEL_115:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
        (const char *)0x8007000ELL,
        dwCreationDisposition);
      if ( lpFileName[0] != v53 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
      v4 = v47;
      if ( v47 != v49 )
        goto LABEL_118;
      return 2147942414LL;
    }
    if ( *((_DWORD *)v18 + 6) != 1 )
    {
      if ( *((_DWORD *)v18 + 6) != 2 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4F2,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
          (const char *)0x80070057LL,
          dwCreationDisposition);
LABEL_97:
        if ( lpFileName[0] != v53 )
          operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
        Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
        utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
        if ( v47 != v49 )
          operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
        return 2147942487LL;
      }
      v57[2] = L"SOFTWARE";
      v57[3] = 8;
      if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpFileName) )
      {
        v19 = 1252;
        goto LABEL_115;
      }
      goto LABEL_35;
    }
    v57[0] = L"SYSTEM";
    v57[1] = 6;
    if ( !(unsigned __int8)Csl::Path::Append((Csl::Path *)lpFileName) )
    {
      v19 = 1258;
      goto LABEL_115;
    }
LABEL_35:
    FileW = CreateFileW(lpFileName[0], 1u, 0, 0, 3u, 0x2000080u, 0);
    v23 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x503,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
                    v22);
      goto LABEL_109;
    }
    LOBYTE(v50) = 0;
    v51 = 0;
    v24 = Csl::OfflineHive::Open((Csl::OfflineHive *)&v50, FileW, v21);
    LastError = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x507,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
        (const char *)(unsigned int)v24,
        dwCreationDisposition);
      Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v50);
      if ( v23 )
        CloseHandle(v23);
      goto LABEL_109;
    }
    if ( v23 )
    {
      v26 = GetLastError();
      CloseHandle(v23);
      SetLastError(v26);
    }
    LastError = Csl::DeletePath((Csl *)lpFileName, v25);
    if ( LastError < 0 )
    {
      v45 = 1294;
LABEL_95:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v45,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
        (const char *)(unsigned int)LastError,
        dwCreationDisposition);
      Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v50);
LABEL_109:
      if ( lpFileName[0] != v53 )
        operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
      v16 = v47;
      if ( v47 != v49 )
LABEL_25:
        operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)LastError;
    }
    v27 = *v2;
    v28 = v2[1];
    v29 = v51;
    v62 = v51;
LABEL_41:
    if ( v27 != v28 )
      break;
    v38 = CreateFileW(lpFileName[0], 2u, 0, 0, 1u, 0x80u, 0);
    v40 = v38;
    if ( v38 == (HANDLE)-1LL )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xD7,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                    v39);
    }
    else
    {
      LastError = Csl::OfflineHive::Save((Csl::OfflineHive *)&v50, v38);
      if ( v40 )
        CloseHandle(v40);
    }
    if ( LastError < 0 )
    {
      v45 = 1349;
      goto LABEL_95;
    }
    v51 = 0;
    v41 = ORCloseHive(v29);
    if ( v41 )
      wil::details::in1diag3::_Log_Win32(
        retaddr,
        (void *)0x43,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
        (const char *)v41,
        dwCreationDisposition);
    LOBYTE(v50) = 0;
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v50);
    if ( lpFileName[0] != v53 )
      operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
    v42 = v18[2];
    if ( (void **)v42 == &utl::_TreeSentinel )
    {
      v43 = (_QWORD *)(*v18 & 0xFFFFFFFFFFFFFFFEuLL);
      v42 = (unsigned __int64)v43;
      if ( (_QWORD *)v43[2] == v18 && (_QWORD *)*v43 != v18 )
      {
        v42 = *v43 & 0xFFFFFFFFFFFFFFFEuLL;
        if ( *(_QWORD **)(v42 + 16) == v43 && *(_QWORD **)v42 != v43 )
        {
          do
          {
            v44 = v42;
            v42 = *(_QWORD *)v42 & 0xFFFFFFFFFFFFFFFEuLL;
          }
          while ( *(_QWORD *)(v42 + 16) == v44 );
        }
      }
    }
    else
    {
      if ( v18 == (_QWORD *)v42 )
        __int2c();
      for ( ; *(void ***)(v42 + 8) != &utl::_TreeSentinel; v42 = *(_QWORD *)(v42 + 8) )
        ;
    }
    v18 = (_QWORD *)v42;
    v2 = v60;
  }
  if ( *v27 != *((_DWORD *)v18 + 6) )
  {
LABEL_71:
    v27 += 16;
    goto LABEL_41;
  }
  Privilege = 0;
  v30 = OROpenKey(v29, *((_QWORD *)v27 + 1), &Privilege);
  if ( v30 == 2 )
  {
    v31 = 0;
    if ( Privilege )
LABEL_50:
      ORCloseKey();
LABEL_51:
    LastError = 0;
  }
  else
  {
    if ( !v30 )
    {
      v31 = 1;
      if ( Privilege )
        goto LABEL_50;
      goto LABEL_51;
    }
    v31 = 0;
    LastError = wil::details::in1diag3::Return_Win32(
                  retaddr,
                  (void *)0x150,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslofflineregistry.cpp",
                  (const char *)v30,
                  dwCreationDisposition);
    if ( Privilege )
      ORCloseKey();
  }
  if ( LastError < 0 )
  {
    v45 = 1306;
    goto LABEL_95;
  }
  if ( !v31 )
  {
    LOBYTE(Privilege) = 0;
    LastError = Csl::OfflineHive::CreateKey(
                  (Csl::OfflineHive *)&v50,
                  *((const unsigned __int16 *const *)v27 + 1),
                  (bool *)&Privilege);
    if ( LastError < 0 )
    {
      v45 = 1310;
      goto LABEL_95;
    }
  }
  v32 = *((_QWORD *)v27 + 5);
  v33 = *((_QWORD *)v27 + 6);
  while ( 2 )
  {
    if ( v32 == v33 )
    {
      v29 = v62;
      goto LABEL_71;
    }
    if ( *(_DWORD *)(v32 + 32) != 1 )
    {
      if ( *(_DWORD *)(v32 + 32) != 4 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x53E,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
          (const char *)0x80070057LL,
          dwCreationDisposition);
        Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v50);
        goto LABEL_97;
      }
      LODWORD(Privilege) = *(_DWORD *)(v32 + 80);
      v34 = Csl::OfflineHive::SetValue(
              (Csl::OfflineHive *)&v50,
              *((const unsigned __int16 **)v27 + 1),
              *(const unsigned __int16 **)v32,
              (const unsigned __int8 *)&Privilege,
              4u,
              4u);
      if ( v34 < 0 )
      {
        v35 = 1323;
        goto LABEL_61;
      }
      goto LABEL_69;
    }
    v36 = *(const unsigned __int8 **)(v32 + 40);
    v37 = -1;
    do
      ++v37;
    while ( *(_WORD *)&v36[2 * v37] );
    v34 = Csl::OfflineHive::SetValue(
            (Csl::OfflineHive *)&v50,
            *((const unsigned __int16 **)v27 + 1),
            *(const unsigned __int16 **)v32,
            v36,
            2 * (int)v37 + 2,
            1u);
    if ( v34 >= 0 )
    {
LABEL_69:
      v32 += 88;
      continue;
    }
    break;
  }
  v35 = 1333;
LABEL_61:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v35,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\deploymentsettings.cpp",
    (const char *)(unsigned int)v34,
    dwCreationDisposition);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)&v50);
  if ( lpFileName[0] != v53 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(v54);
  if ( v47 != v49 )
    operator delete(v47, (const struct std::nothrow_t *)&std::nothrow);
  return (unsigned int)v34;
}

```

## disassembly

```asm
0x18010b5b0  mov     [rsp-8+arg_8], rdx
0x18010b5b5  push    rbp
0x18010b5b6  push    rbx
0x18010b5b7  push    rsi
0x18010b5b8  push    rdi
0x18010b5b9  push    r12
0x18010b5bb  push    r13
0x18010b5bd  push    r14
0x18010b5bf  push    r15
0x18010b5c1  lea     rbp, [rsp-1Fh]
0x18010b5c6  sub     rsp, 0D8h
0x18010b5cd  mov     r14, rdx
0x18010b5d0  lea     rax, [rbp+57h+var_C0]
0x18010b5d4  mov     [rbp+57h+var_D0], rax
0x18010b5d8  lea     rax, [rbp+57h+var_C0]
0x18010b5dc  mov     [rbp+57h+var_C8], rax
0x18010b5e0  xor     r13d, r13d
0x18010b5e3  mov     [rbp+57h+var_C0], r13w
0x18010b5e8  mov     r8, [rcx+8]
0x18010b5ec  sub     r8, [rcx]
0x18010b5ef  sar     r8, 1
0x18010b5f2  mov     rdx, [rcx]
0x18010b5f5  lea     rcx, [rbp+57h+var_D0]
0x18010b5f9  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18010b5fe  test    al, al
0x18010b600  jnz     short loc_18010B63A
0x18010b602  mov     edx, 4C6h; void *
0x18010b607  lea     r8, aOnecoreBaseGen_58; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18010b60e  mov     r9d, 8007000Eh; char *
0x18010b614  mov     rcx, [rbp+5Fh]; this
0x18010b618  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b61d  mov     rcx, [rbp+57h+var_D0]
0x18010b621  lea     rax, [rbp+57h+var_C0]
0x18010b625  cmp     rcx, rax
0x18010b628  jz      loc_18010BDD8
0x18010b62e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18010b635  jmp     loc_18010BDD3
0x18010b63a  lea     rax, aWindowsSystem3_21; "Windows\\System32\\Config"
0x18010b641  mov     [rbp+57h+var_B0], rax
0x18010b645  mov     [rbp+57h+var_A8], 17h
0x18010b64d  lea     rdx, [rbp+57h+var_B0]
0x18010b651  lea     rcx, [rbp+57h+var_D0]; this
0x18010b655  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18010b65a  test    al, al
0x18010b65c  jnz     short loc_18010B665
0x18010b65e  mov     edx, 4C7h
0x18010b663  jmp     short loc_18010B607
0x18010b665  lea     r8, [rbp+57h+var_80]
0x18010b669  mov     [rbp+57h+var_80], r8
0x18010b66d  lea     rcx, [rbp+57h+var_80]
0x18010b671  mov     [rbp+57h+var_78], rcx
0x18010b675  mov     [rbp+57h+var_70], rcx
0x18010b679  mov     [rbp+57h+var_68], r13
0x18010b67d  mov     rbx, [r14]
0x18010b680  mov     rdi, [r14+8]
0x18010b684  lea     r15, ?_TreeSentinel@utl@@3PEAXEA; void * utl::_TreeSentinel
0x18010b68b  cmp     rbx, rdi
0x18010b68e  jz      loc_18010B723
0x18010b694  lea     rax, [rbp+57h+var_80]
0x18010b698  cmp     rcx, rax
0x18010b69b  jz      short loc_18010B6D6
0x18010b69d  lea     rdx, [rbp+57h+var_80]
0x18010b6a1  mov     rax, r8
0x18010b6a4  mov     r10d, [rbx]
0x18010b6a7  cmp     [rax+18h], r10d
0x18010b6ab  jl      short loc_18010B6B8
0x18010b6ad  mov     rdx, rax
0x18010b6b0  mov     r9d, 8
0x18010b6b6  jmp     short loc_18010B6BE
0x18010b6b8  mov     r9d, 10h
0x18010b6be  mov     rax, [r9+rax]
0x18010b6c2  cmp     rax, r15
0x18010b6c5  jnz     short loc_18010B6A7
0x18010b6c7  lea     rax, [rbp+57h+var_80]
0x18010b6cb  cmp     rdx, rax
0x18010b6ce  jz      short loc_18010B6D6
0x18010b6d0  cmp     r10d, [rdx+18h]
0x18010b6d4  jge     short loc_18010B6F4
0x18010b6d6  mov     r8, rbx
0x18010b6d9  lea     rdx, [rbp+57h+var_60]
0x18010b6dd  lea     rcx, [rbp+57h+var_80]
0x18010b6e1  call    ??$emplace@AEBW4Hive@RegistryKey@Details@Core@Manager@Container@@$0A@@?$_Tree@W4Hive@RegistryKey@Details@Core@Manager@Container@@W4123456@U?$less@W4Hive@RegistryKey@Details@Core@Manager@Container@@@utl@@V?$allocator@W4Hive@RegistryKey@Details@Core@Manager@Container@@@8@$0A@@utl@@QEAA?AU?$pair@V?$_TreeConstIt@W4Hive@RegistryKey@Details@Core@Manager@Container@@@utl@@_N@1@AEBW4Hive@RegistryKey@Details@Core@Manager@Container@@@Z; utl::_Tree<Container::Manager::Core::Details::RegistryKey::Hive,Container::Manager::Core::Details::RegistryKey::Hive,utl::less<Container::Manager::Core::Details::RegistryKey::Hive>,utl::allocator<Container::Manager::Core::Details::RegistryKey::Hive>,0>::emplace<Container::Manager::Core::Details::RegistryKey::Hive const &,0>(Container::Manager::Core::Details::RegistryKey::Hive const &)
0x18010b6e6  cmp     [rbp+57h+var_60], r13
0x18010b6ea  jz      short loc_18010B6FA
0x18010b6ec  mov     rcx, [rbp+57h+var_70]
0x18010b6f0  mov     r8, [rbp+57h+var_80]
0x18010b6f4  add     rbx, 40h ; '@'
0x18010b6f8  jmp     short loc_18010B68B
0x18010b6fa  mov     rcx, [rbp+5Fh]; this
0x18010b6fe  mov     r9d, 8007000Eh; char *
0x18010b704  lea     r8, aOnecoreBaseGen_58; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18010b70b  mov     edx, 4D0h; void *
0x18010b710  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b715  lea     rcx, [rbp+57h+var_80]
0x18010b719  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18010b71e  jmp     loc_18010B61D
0x18010b723  mov     [rbp+57h+ReturnedState], r13
0x18010b727  mov     dword ptr [rbp+57h+Privilege], 11h
0x18010b72e  mov     dword ptr [rbp+57h+Privilege+4], 12h
0x18010b735  lea     r9, [rbp+57h+ReturnedState]; ReturnedState
0x18010b739  xor     r8d, r8d; Flags
0x18010b73c  lea     edx, [r8+2]; NumPriv
0x18010b740  lea     rcx, [rbp+57h+Privilege]; Privilege
0x18010b744  call    cs:__imp_RtlAcquirePrivilege
0x18010b74b  nop     dword ptr [rax+rax+00h]
0x18010b750  test    eax, eax
0x18010b752  jns     short loc_18010B7BC
0x18010b754  mov     rcx, [rbp+5Fh]; this
0x18010b758  mov     r9d, eax; char *
0x18010b75b  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18010b762  mov     edx, 52h ; 'R'; void *
0x18010b767  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18010b76c  mov     ebx, eax
0x18010b76e  test    eax, eax
0x18010b770  jns     short loc_18010B7BC
0x18010b772  mov     rcx, [rbp+5Fh]; this
0x18010b776  mov     r9d, eax; char *
0x18010b779  lea     r8, aOnecoreBaseGen_58; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18010b780  mov     edx, 4D8h; void *
0x18010b785  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010b78a  lea     rcx, [rbp+57h+ReturnedState]; this
0x18010b78e  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x18010b793  lea     rcx, [rbp+57h+var_80]
0x18010b797  call    ??1?$_Tree@PEAVContainerHandle@Core@Manager@Container@@PEAV1234@U?$less@PEAVContainerHandle@Core@Manager@Container@@@utl@@V?$allocator@PEAVContainerHandle@Core@Manager@Container@@@6@$0A@@utl@@IEAA@XZ; utl::_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>::~_Tree<Container::Manager::Core::ContainerHandle *,Container::Manager::Core::ContainerHandle *,utl::less<Container::Manager::Core::ContainerHandle *>,utl::allocator<Container::Manager::Core::ContainerHandle *>,0>(void)
0x18010b79c  mov     rcx, [rbp+57h+var_D0]; void *
0x18010b7a0  lea     rax, [rbp+57h+var_C0]
0x18010b7a4  cmp     rcx, rax
0x18010b7a7  jz      short loc_18010B7B5
0x18010b7a9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18010b7b0  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010b7b5  mov     eax, ebx
0x18010b7b7  jmp     loc_18010BE08
0x18010b7bc  mov     rsi, [rbp+57h+var_70]
0x18010b7c0  lea     r12, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18010b7c7  lea     rax, [rbp+57h+var_80]
0x18010b7cb  cmp     rsi, rax
0x18010b7ce  jz      loc_18010BDDF
0x18010b7d4  lea     rax, [rbp+57h+var_90]
0x18010b7d8  mov     [rbp+57h+lpFileName], rax
0x18010b7dc  lea     rax, [rbp+57h+var_90]
0x18010b7e0  mov     [rbp+57h+var_98], rax
0x18010b7e4  mov     [rbp+57h+var_90], r13w
0x18010b7e9  mov     rdx, [rbp+57h+var_D0]
0x18010b7ed  mov     r8, [rbp+57h+var_C8]
0x18010b7f1  sub     r8, rdx
0x18010b7f4  sar     r8, 1
0x18010b7f7  lea     rcx, [rbp+57h+lpFileName]
0x18010b7fb  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x18010b800  test    al, al
0x18010b802  jz      loc_18010BD81
0x18010b808  mov     ecx, [rsi+18h]
0x18010b80b  sub     ecx, 1
0x18010b80e  jz      short loc_18010B847
0x18010b810  cmp     ecx, 1
0x18010b813  jnz     loc_18010BC17
0x18010b819  lea     rax, aSoftware; "SOFTWARE"
0x18010b820  mov     [rbp+57h+var_50], rax
0x18010b824  mov     [rbp+57h+var_48], 8
0x18010b82c  lea     rdx, [rbp+57h+var_50]
0x18010b830  lea     rcx, [rbp+57h+lpFileName]; this
0x18010b834  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18010b839  test    al, al
0x18010b83b  jnz     short loc_18010B86F
0x18010b83d  mov     edx, 4E4h
0x18010b842  jmp     loc_18010BD86
0x18010b847  lea     rax, aSystem; "SYSTEM"
0x18010b84e  mov     [rbp+57h+var_60], rax
0x18010b852  mov     [rbp+57h+var_58], 6
0x18010b85a  lea     rdx, [rbp+57h+var_60]
0x18010b85e  lea     rcx, [rbp+57h+lpFileName]; this
0x18010b862  call    ?Append@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Append(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18010b867  test    al, al
0x18010b869  jz      loc_18010BD7A
0x18010b86f  mov     [rsp+110h+hTemplateFile], r13; hTemplateFile
0x18010b874  mov     [rsp+110h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x18010b87c  mov     [rsp+110h+dwCreationDisposition], 3; int
0x18010b884  xor     r9d, r9d; lpSecurityAttributes
0x18010b887  xor     r8d, r8d; dwShareMode
0x18010b88a  lea     edx, [r9+1]; dwDesiredAccess
0x18010b88e  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x18010b892  call    cs:__imp_CreateFileW
0x18010b899  nop     dword ptr [rax+rax+00h]
0x18010b89e  mov     rdi, rax
0x18010b8a1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18010b8a5  jz      loc_18010BD23
0x18010b8ab  mov     byte ptr [rbp+57h+var_B0], r13b
0x18010b8af  mov     [rbp+57h+var_A8], r13
0x18010b8b3  mov     rdx, rax; void *
0x18010b8b6  lea     rcx, [rbp+57h+var_B0]; this
0x18010b8ba  call    ?Open@OfflineHive@Csl@@QEAAJPEAX_N@Z; Csl::OfflineHive::Open(void *,bool)
0x18010b8bf  mov     ebx, eax
0x18010b8c1  test    eax, eax
0x18010b8c3  js      loc_18010BCEC
0x18010b8c9  test    rdi, rdi
0x18010b8cc  jz      short loc_18010B8F9
0x18010b8ce  call    cs:__imp_GetLastError
0x18010b8d5  nop     dword ptr [rax+rax+00h]
0x18010b8da  mov     ebx, eax
0x18010b8dc  mov     rcx, rdi; hObject
0x18010b8df  call    cs:__imp_CloseHandle
0x18010b8e6  nop     dword ptr [rax+rax+00h]
0x18010b8eb  mov     ecx, ebx; dwErrCode
0x18010b8ed  call    cs:__imp_SetLastError
0x18010b8f4  nop     dword ptr [rax+rax+00h]
0x18010b8f9  lea     rcx, [rbp+57h+lpFileName]; this
0x18010b8fd  call    ?DeletePath@Csl@@YAJAEBVPath@1@@Z; Csl::DeletePath(Csl::Path const &)
0x18010b902  mov     ebx, eax
0x18010b904  test    eax, eax
0x18010b906  js      loc_18010BCE2
0x18010b90c  mov     rdi, [r14]
0x18010b90f  mov     r15, [r14+8]
0x18010b913  mov     r14, [rbp+57h+var_A8]
0x18010b917  mov     [rbp+57h+arg_18], r14
0x18010b91b  cmp     rdi, r15
0x18010b91e  jz      loc_18010BAE3
0x18010b924  mov     eax, [rsi+18h]
0x18010b927  cmp     [rdi], eax
0x18010b929  jnz     loc_18010BADA
0x18010b92f  mov     [rbp+57h+Privilege], r13
0x18010b933  lea     r8, [rbp+57h+Privilege]
0x18010b937  mov     rdx, [rdi+8]
0x18010b93b  mov     rcx, r14
0x18010b93e  call    OROpenKey
0x18010b943  cmp     eax, 2
0x18010b946  jnz     short loc_18010B95C
0x18010b948  mov     r14b, r13b
0x18010b94b  mov     rcx, [rbp+57h+Privilege]
0x18010b94f  test    rcx, rcx
0x18010b952  jz      short loc_18010B9A0
0x18010b954  call    ORCloseKey
0x18010b959  nop
0x18010b95a  jmp     short loc_18010B9A0
0x18010b95c  test    eax, eax
0x18010b95e  jz      short loc_18010B98E
0x18010b960  mov     r14b, r13b
0x18010b963  mov     rcx, [rbp+5Fh]; this
0x18010b967  mov     r9d, eax; char *
0x18010b96a  lea     r8, aOnecoreBaseGen_33; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18010b971  mov     edx, 150h; void *
0x18010b976  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18010b97b  mov     ebx, eax
0x18010b97d  mov     rcx, [rbp+57h+Privilege]
0x18010b981  test    rcx, rcx
0x18010b984  jz      short loc_18010B9A3
0x18010b986  call    ORCloseKey
0x18010b98b  nop
0x18010b98c  jmp     short loc_18010B9A3
0x18010b98e  mov     r14b, 1
0x18010b991  mov     rcx, [rbp+57h+Privilege]
0x18010b995  test    rcx, rcx
0x18010b998  jz      short loc_18010B9A0
0x18010b99a  call    ORCloseKey
0x18010b99f  nop
0x18010b9a0  mov     ebx, r13d
0x18010b9a3  test    ebx, ebx
0x18010b9a5  js      loc_18010BCCE
0x18010b9ab  test    r14b, r14b
0x18010b9ae  jnz     short loc_18010B9CF
0x18010b9b0  mov     byte ptr [rbp+57h+Privilege], r13b
0x18010b9b4  lea     r8, [rbp+57h+Privilege]; bool *
0x18010b9b8  mov     rdx, [rdi+8]; unsigned __int16 *
0x18010b9bc  lea     rcx, [rbp+57h+var_B0]; this
0x18010b9c0  call    ?CreateKey@OfflineHive@Csl@@QEAAJQEBGAEA_N@Z; Csl::OfflineHive::CreateKey(ushort const * const,bool &)
0x18010b9c5  mov     ebx, eax
0x18010b9c7  test    eax, eax
0x18010b9c9  js      loc_18010BC34
0x18010b9cf  mov     rbx, [rdi+28h]
0x18010b9d3  mov     r14, [rdi+30h]
0x18010b9d7  cmp     rbx, r14
0x18010b9da  jz      loc_18010BAD6
0x18010b9e0  mov     ecx, [rbx+20h]
0x18010b9e3  sub     ecx, 1
0x18010b9e6  jz      loc_18010BA8A
0x18010b9ec  cmp     ecx, 3
0x18010b9ef  jnz     loc_18010BC5A
0x18010b9f5  mov     eax, [rbx+50h]
0x18010b9f8  mov     dword ptr [rbp+57h+Privilege], eax
0x18010b9fb  lea     eax, [rcx+1]
0x18010b9fe  mov     [rsp+110h+dwFlagsAndAttributes], eax; unsigned int
0x18010ba02  mov     [rsp+110h+dwCreationDisposition], eax; int
0x18010ba06  lea     r9, [rbp+57h+Privilege]; unsigned __int8 *
0x18010ba0a  mov     r8, [rbx]; unsigned __int16 *
0x18010ba0d  mov     rdx, [rdi+8]; unsigned __int16 *
0x18010ba11  lea     rcx, [rbp+57h+var_B0]; this
0x18010ba15  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x18010ba1a  mov     r13d, eax
0x18010ba1d  test    eax, eax
0x18010ba1f  jns     loc_18010BACA
0x18010ba25  mov     edx, 52Bh; void *
0x18010ba2a  mov     r9d, r13d; char *
0x18010ba2d  lea     r8, aOnecoreBaseGen_58; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18010ba34  mov     rcx, [rbp+5Fh]; this
0x18010ba38  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010ba3d  lea     rcx, [rbp+57h+var_B0]; this
0x18010ba41  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x18010ba46  lea     rax, [rbp+57h+var_90]
0x18010ba4a  mov     rcx, [rbp+57h+lpFileName]; void *
0x18010ba4e  cmp     rcx, rax
0x18010ba51  jz      short loc_18010BA5B
0x18010ba53  mov     rdx, r12; struct std::nothrow_t *
  ... truncated ...
```
