# Container::Manager::Core::Details::SpecializationLayer::MirrorSpecializationRegistryKeys(utl::optional<ulong> const &)

- ea: `0x1800dcbac`
- end: `0x1800dd86b`
- name: `?MirrorSpecializationRegistryKeys@SpecializationLayer@Details@Core@Manager@Container@@AEAAJAEBV?$optional@K@utl@@@Z`
- size: `3263`
- prototype: ``
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800d89b0`

## callees

- `0x180004bd0`
- `0x180004fc4`
- `0x18000a10c`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x180016774`
- `0x18002dc0c`
- `0x18002fc34`
- `0x180034364`
- `0x180080034`
- `0x180080264`
- `0x180088eb0`
- `0x1800dcbac`
- `0x1800dd874`
- `0x180106f88`
- `0x180197498`
- `0x180198db0`
- `0x180199248`
- `0x180199640`
- `0x180199710`
- `0x18019a018`
- `0x18019a294`

## import_xrefs

- `ntdll!RtlAcquirePrivilege` at `0x1800dcca2`
- `ntdll!RtlAcquirePrivilege` at `0x1800dcca2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dd1c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dd25e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dd1c2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800dd25e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd5e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd5fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd6ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd6bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd230`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd5e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd5fa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd6ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd6bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7cb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800dd7df`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcd58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcdaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dceba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcf60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcf76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd016`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd02c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcd58`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcdaa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcea4`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dceba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcf60`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dcf76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd016`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800dd02c`

## string_xrefs

- `0x1800dccb9`: `onecore\base\gendrv\silos\csl\lib\CslPrivilege.h`
- `0x1800dd178`: `Microsoft\Windows\CurrentVersion\SideBySide\Configuration`
- `0x1800dd38f`: `Windows\System32\config\SYSTEM`
- `0x1800dd16d`: `ReadOnlyImage`
- `0x1800dcedc`: `EnableVirtualizationBasedSecurity`
- `0x1800dd48e`: `Windows\System32\config\SOFTWARE`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::SpecializationLayer::MirrorSpecializationRegistryKeys(
        struct Path *a1,
        __int64 a2)
{
  int v4; // eax
  unsigned int LastError; // ebx
  char *v6; // r14
  int v7; // eax
  NTSTATUS v8; // eax
  int v9; // eax
  __int64 v10; // rdx
  int v11; // r12d
  int v12; // eax
  int v13; // eax
  __int64 v14; // r9
  __int64 v15; // rdx
  __int64 *v16; // rbx
  Csl *p_hKey; // r14
  Csl::OfflineHive *v18; // rsi
  unsigned int v19; // edi
  void *v20; // rcx
  __int64 v21; // rax
  const struct Path *v22; // r9
  int v23; // eax
  HANDLE FileW; // rax
  const char *v25; // r9
  void *v26; // rbx
  int v27; // eax
  HANDLE v28; // rax
  const char *v29; // r9
  void *v30; // rdi
  int v31; // eax
  unsigned int v32; // esi
  __int64 v33; // r8
  __int64 v34; // rdx
  __int64 v35; // rdx
  void *v36; // rcx
  __int64 v37; // r8
  LPCWSTR v38; // rdx
  __int64 v39; // rdx
  const char *v40; // r9
  const char *v41; // r9
  __int64 v42; // rcx
  int v43; // eax
  void *v45; // rsi
  DWORD dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositiona; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationDispositionb; // [rsp+20h] [rbp-E0h]
  PVOID ReturnedState; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int8 v50[8]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v51[8]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v52; // [rsp+58h] [rbp-A8h]
  HKEY hKey; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v54[8]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v55; // [rsp+70h] [rbp-90h]
  void *v56[2]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v57; // [rsp+88h] [rbp-78h]
  void *v58[2]; // [rsp+90h] [rbp-70h] BYREF
  __int16 v59; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v60; // [rsp+A2h] [rbp-5Eh]
  int v61; // [rsp+AAh] [rbp-56h]
  __int16 v62; // [rsp+AEh] [rbp-52h]
  __m128i si128; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v64; // [rsp+C0h] [rbp-40h]
  void *v65[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v66; // [rsp+D8h] [rbp-28h] BYREF
  void *v67[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int16 v68; // [rsp+100h] [rbp+0h] BYREF
  __int64 v69; // [rsp+102h] [rbp+2h]
  int v70; // [rsp+10Ah] [rbp+Ah]
  __int16 v71; // [rsp+10Eh] [rbp+Eh]
  __m128i v72; // [rsp+110h] [rbp+10h] BYREF
  __int64 v73; // [rsp+120h] [rbp+20h]
  void *v74[2]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v75; // [rsp+138h] [rbp+38h] BYREF
  void *v76[2]; // [rsp+150h] [rbp+50h] BYREF
  _WORD v77[8]; // [rsp+160h] [rbp+60h] BYREF
  __int128 v78; // [rsp+170h] [rbp+70h] BYREF
  __int64 v79; // [rsp+180h] [rbp+80h]
  ULONG Privilege[2]; // [rsp+188h] [rbp+88h] BYREF
  int v81; // [rsp+190h] [rbp+90h]
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v54[0] = 0;
  v55 = 0;
  v4 = Csl::OfflineHive::Open((Csl::OfflineHive *)v54, a1);
  LastError = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x45E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v4,
      dwCreationDisposition);
    goto LABEL_118;
  }
  v6 = (char *)a1 + 32;
  v51[0] = 0;
  v52 = 0;
  v7 = Csl::OfflineHive::Open((Csl::OfflineHive *)v51, (struct Path *)((char *)a1 + 32));
  LastError = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x461,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v7,
      dwCreationDisposition);
LABEL_5:
    Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
    goto LABEL_118;
  }
  ReturnedState = 0;
  Privilege[0] = 17;
  Privilege[1] = 18;
  v81 = 8;
  v8 = RtlAcquirePrivilege(Privilege, 3u, 0, &ReturnedState);
  if ( v8 < 0 )
  {
    v9 = wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)0x52,
           (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslPrivilege.h",
           (const char *)(unsigned int)v8,
           dwCreationDisposition);
    LastError = v9;
    if ( v9 < 0 )
    {
      v10 = 1128;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)(unsigned int)v9,
        dwCreationDisposition);
LABEL_10:
      Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
      goto LABEL_5;
    }
  }
  v11 = *(_DWORD *)(*((_QWORD *)a1 + 8) + 228LL);
  if ( (v11 & 1) != 0 )
  {
    hKey = 0;
    v12 = Csl::OpenRegistryHive(1, 131097, &hKey);
    LastError = v12;
    if ( v12 >= 0 )
    {
      *(_QWORD *)Privilege = 0;
      v13 = Csl::OpenRegistryHive(0, 131097, Privilege);
      LastError = v13;
      if ( v13 >= 0 )
      {
        v16 = &qword_1801BD800;
        while ( 1 )
        {
          if ( *(_DWORD *)v16 )
          {
            if ( *(_DWORD *)v16 != 1 )
            {
              LastError = -2147467259;
              v15 = 1164;
              v14 = 2147500037LL;
              goto LABEL_18;
            }
            p_hKey = (Csl *)&hKey;
            v18 = (Csl::OfflineHive *)v54;
          }
          else
          {
            p_hKey = (Csl *)Privilege;
            v18 = (Csl::OfflineHive *)v51;
          }
          v19 = Csl::OfflineHive::DeleteKeyRecursive(v18, (const unsigned __int16 *)v16[1]);
          if ( (int)(v19 + 0x80000000) >= 0 && v19 != -2147024894 )
            break;
          v20 = (void *)v16[1];
          v76[0] = v77;
          v77[0] = 0;
          v76[1] = v77;
          v21 = -1;
          v56[0] = v20;
          do
            ++v21;
          while ( *((_WORD *)v20 + v21) );
          v56[1] = (void *)v21;
          if ( !(unsigned __int8)Csl::Path::Assign((Csl::Path *)v76) )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x498,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
              (const char *)0x8007000ELL,
              dwCreationDisposition);
            if ( v76[0] != v77 )
              operator delete(v76[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( *(_QWORD *)Privilege )
              RegCloseKey(*(HKEY *)Privilege);
            if ( hKey )
              RegCloseKey(hKey);
            Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
            Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
            LastError = -2147024882;
            goto LABEL_118;
          }
          v23 = Csl::CopyRegistryTreeToOfflineHive(p_hKey, v18, (struct Csl::OfflineHive *)v76, v22);
          v19 = v23;
          if ( v23 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x49D,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
              (const char *)(unsigned int)v23,
              dwCreationDisposition);
            if ( v76[0] != v77 )
              operator delete(v76[0], (const struct std::nothrow_t *)&std::nothrow);
            goto LABEL_45;
          }
          if ( v76[0] != v77 )
            operator delete(v76[0], (const struct std::nothrow_t *)&std::nothrow);
          v16 += 2;
          if ( v16 == (__int64 *)off_1801BD860 )
          {
            if ( *(_QWORD *)Privilege )
              RegCloseKey(*(HKEY *)Privilege);
            if ( hKey )
              RegCloseKey(hKey);
            v6 = (char *)a1 + 32;
            goto LABEL_39;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x494,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
          (const char *)v19,
          dwCreationDisposition);
LABEL_45:
        if ( *(_QWORD *)Privilege )
          RegCloseKey(*(HKEY *)Privilege);
        if ( hKey )
          RegCloseKey(hKey);
        goto LABEL_49;
      }
      v14 = (unsigned int)v13;
      v15 = 1143;
LABEL_18:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)v14,
        dwCreationDisposition);
      if ( *(_QWORD *)Privilege )
        RegCloseKey(*(HKEY *)Privilege);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x472,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)(unsigned int)v12,
        dwCreationDisposition);
    }
    if ( hKey )
      RegCloseKey(hKey);
    goto LABEL_10;
  }
LABEL_39:
  if ( (v11 & 2) != 0 )
  {
    if ( *(_BYTE *)(a2 + 4) )
    {
      *(_DWORD *)v50 = 1;
      v9 = Csl::OfflineHive::SetValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\DeviceGuard",
             L"EnableVirtualizationBasedSecurity",
             v50,
             4u,
             4u);
      LastError = v9;
      if ( v9 < 0 )
      {
        v10 = 1194;
        goto LABEL_9;
      }
      *(_DWORD *)v50 = 1;
      v9 = Csl::OfflineHive::SetValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\Session Manager\\Memory Management",
             L"HotPatchRestrictions",
             v50,
             4u,
             4u);
      LastError = v9;
      if ( v9 < 0 )
      {
        v10 = 1200;
        goto LABEL_9;
      }
      *(_DWORD *)v50 = *(_DWORD *)a2;
      v9 = Csl::OfflineHive::SetValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\Session Manager\\Memory Management",
             L"HotPatchTableSize",
             v50,
             4u,
             4u);
      LastError = v9;
      if ( v9 < 0 )
      {
        v10 = 1206;
        goto LABEL_9;
      }
    }
    else
    {
      v9 = Csl::OfflineHive::DeleteValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\DeviceGuard",
             L"EnableVirtualizationBasedSecurity");
      LastError = v9;
      if ( (int)(v9 + 0x80000000) >= 0 && v9 != -2147024894 )
      {
        v10 = 1214;
        goto LABEL_9;
      }
      v9 = Csl::OfflineHive::DeleteValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\Session Manager\\Memory Management",
             L"HotPatchRestrictions");
      LastError = v9;
      if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -2147024894 )
      {
        v10 = 1221;
        goto LABEL_9;
      }
      v9 = Csl::OfflineHive::DeleteValue(
             (Csl::OfflineHive *)v54,
             L"ControlSet001\\Control\\Session Manager\\Memory Management",
             L"HotPatchTableSize");
      LastError = v9;
      if ( ((v9 + 0x80000000) & 0x80000000) == 0 && v9 != -2147024894 )
      {
        v10 = 1228;
        goto LABEL_9;
      }
    }
  }
  *(_DWORD *)v50 = 1;
  v9 = Csl::OfflineHive::SetValue(
         (Csl::OfflineHive *)v51,
         L"Microsoft\\Windows\\CurrentVersion\\SideBySide\\Configuration",
         L"ReadOnlyImage",
         v50,
         4u,
         4u);
  LastError = v9;
  if ( v9 < 0 )
  {
    v10 = 1238;
    goto LABEL_9;
  }
  FileW = CreateFileW(*(LPCWSTR *)a1, 2u, 0, 0, 3u, 0x80000000, 0);
  v26 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x4E2,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
                  v25);
    goto LABEL_10;
  }
  v27 = Csl::OfflineHive::Save((Csl::OfflineHive *)v54, FileW);
  v19 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x4E4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)(unsigned int)v27,
      dwCreationDispositiona);
    goto LABEL_78;
  }
  v28 = CreateFileW(*(LPCWSTR *)v6, 2u, 0, 0, 3u, 0x80000000, 0);
  v30 = v28;
  if ( v28 != (HANDLE)-1LL )
  {
    v31 = Csl::OfflineHive::Save((Csl::OfflineHive *)v51, v28);
    v32 = v31;
    if ( v31 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x4F2,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
        (const char *)(unsigned int)v31,
        dwCreationDispositionb);
      goto LABEL_113;
    }
    v33 = *((_QWORD *)a1 + 1) - *(_QWORD *)a1;
    v34 = *(_QWORD *)a1;
    v58[0] = &v59;
    v58[1] = &v59;
    v65[0] = &v66;
    v66 = 0;
    v65[1] = &v66;
    v60 = 0;
    v61 = 0;
    v62 = 0;
    v59 = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
    v64 = -1;
    LOWORD(v66) = 0;
    if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                            v65,
                            v34,
                            v33 >> 1) )
    {
      v56[1] = (void *)30;
      v56[0] = L"Windows\\System32\\config\\SYSTEM";
      if ( (unsigned __int8)Csl::Path::Assign((Csl::Path *)v58) )
      {
        v37 = *((_QWORD *)v6 + 1) - *(_QWORD *)v6;
        v38 = *(LPCWSTR *)v6;
        v67[0] = &v68;
        v67[1] = &v68;
        v74[0] = &v75;
        v75 = 0;
        v74[1] = &v75;
        v69 = 0;
        v70 = 0;
        v71 = 0;
        v68 = 0;
        v72 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
        v73 = -1;
        LOWORD(v75) = 0;
        if ( (unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                                v74,
                                v38,
                                v37 >> 1) )
        {
          v56[1] = (void *)32;
          v56[0] = L"Windows\\System32\\config\\SOFTWARE";
          if ( (unsigned __int8)Csl::Path::Assign((Csl::Path *)v67) )
          {
            v57 = -1;
            *(__m128i *)v56 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
            if ( (unsigned __int8)utl::vector<Container::Manager::Core::Details::BindMapping,utl::allocator<Container::Manager::Core::Details::BindMapping>>::_SetCapacity(
                                    v56,
                                    8) )
            {
              if ( !(unsigned __int8)utl::vector<Container::Manager::Core::Details::BindMapping,utl::allocator<Container::Manager::Core::Details::BindMapping>>::emplace_back<Container::Manager::Core::Details::BindMapping,0>(
                                       v56,
                                       v58) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x502,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
                  v40);
              if ( !(unsigned __int8)utl::vector<Container::Manager::Core::Details::BindMapping,utl::allocator<Container::Manager::Core::Details::BindMapping>>::emplace_back<Container::Manager::Core::Details::BindMapping,0>(
                                       v56,
                                       v67) )
                wil::details::in1diag3::_FailFast_Unexpected(
                  retaddr,
                  (void *)0x503,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
                  v41);
              v42 = *((_QWORD *)a1 + 35);
              v79 = v57;
              v78 = *(_OWORD *)v56;
              v43 = Container::Manager::Core::Details::BindingStore::AddBindMappings(v42, qword_1801D8958, &v78, 0);
              v32 = v43;
              if ( v43 >= 0 )
              {
                if ( v74[0] != &v75 )
                  operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
                utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v72);
                if ( v67[0] != &v68 )
                  operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
                if ( v65[0] != &v66 )
                  operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
                utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&si128);
                if ( v58[0] != &v59 )
                  operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
                if ( v30 )
                  CloseHandle(v30);
                if ( v26 )
                  CloseHandle(v26);
                Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
                Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
                Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v54);
                return 0;
              }
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x509,
                (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
                (const char *)(unsigned int)v43,
                dwCreationDispositionb);
              if ( v74[0] != &v75 )
                operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
              utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v72);
              if ( v67[0] != &v68 )
                operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
              if ( v65[0] != &v66 )
                operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
              utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&si128);
              if ( v58[0] != &v59 )
                operator delete(v58[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_113:
              if ( v30 )
                CloseHandle(v30);
              if ( v26 )
                CloseHandle(v26);
              Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
              Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
              LastError = v32;
              goto LABEL_118;
            }
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x500,
              (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
              (const char *)0x8007000ELL,
              dwCreationDispositionb);
            v45 = v56[0];
            if ( v56[0] != (void *)-1LL )
            {
              utl::_RangeDestroyApc<utl::allocator<Container::Manager::Core::Details::BindMapping>>(
                (char *)v56[1] - (char *)v56[0],
                v56[0],
                ((char *)v56[1] - (char *)v56[0]) / 88);
              operator delete(v45, (const struct std::nothrow_t *)&std::nothrow);
            }
            if ( v74[0] != &v75 )
              operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
            utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v72);
            if ( v67[0] != &v68 )
              operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
            if ( v65[0] != &v66 )
              operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
            utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&si128);
            v36 = v58[0];
            if ( v58[0] == &v59 )
            {
LABEL_142:
              if ( v30 )
                CloseHandle(v30);
              if ( v26 )
                CloseHandle(v26);
              Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
              Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
              Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v54);
              return 2147942414LL;
            }
LABEL_141:
            operator delete(v36, (const struct std::nothrow_t *)&std::nothrow);
            goto LABEL_142;
          }
          v39 = 1277;
        }
        else
        {
          v39 = 1275;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v39,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
          (const char *)0x8007000ELL,
          dwCreationDispositionb);
        if ( v74[0] != &v75 )
          operator delete(v74[0], (const struct std::nothrow_t *)&std::nothrow);
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&v72);
        if ( v67[0] != &v68 )
          operator delete(v67[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_87:
        if ( v65[0] != &v66 )
          operator delete(v65[0], (const struct std::nothrow_t *)&std::nothrow);
        utl::vector<Container::Manager::Core::Details::OverlayDirectory,utl::allocator<Container::Manager::Core::Details::OverlayDirectory>>::_Uninit(&si128);
        v36 = v58[0];
        if ( v58[0] == &v59 )
          goto LABEL_142;
        goto LABEL_141;
      }
      v35 = 1272;
    }
    else
    {
      v35 = 1270;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v35,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
      (const char *)0x8007000ELL,
      dwCreationDispositionb);
    goto LABEL_87;
  }
  v19 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0x4F0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\specialization.cpp",
          v29);
LABEL_78:
  if ( v26 )
    CloseHandle(v26);
LABEL_49:
  Csl::AcquiredPrivileges::~AcquiredPrivileges((Csl::AcquiredPrivileges *)&ReturnedState);
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v51);
  LastError = v19;
LABEL_118:
  Csl::OfflineHive::~OfflineHive((Csl::OfflineHive *)v54);
  return LastError;
}

```

## disassembly

```asm
0x1800dcbac  mov     [rsp-8+arg_10], rbx
0x1800dcbb1  push    rbp
0x1800dcbb2  push    rsi
0x1800dcbb3  push    rdi
0x1800dcbb4  push    r12
0x1800dcbb6  push    r13
0x1800dcbb8  push    r14
0x1800dcbba  push    r15
0x1800dcbbc  lea     rbp, [rsp-0A0h]
0x1800dcbc4  sub     rsp, 1A0h
0x1800dcbcb  mov     rax, cs:__security_cookie
0x1800dcbd2  xor     rax, rsp
0x1800dcbd5  mov     [rbp+0D0h+var_38], rax
0x1800dcbdc  mov     r13, rdx
0x1800dcbdf  mov     r15, rcx
0x1800dcbe2  mov     rdx, rcx; struct Path *
0x1800dcbe5  xor     esi, esi
0x1800dcbe7  lea     rcx, [rsp+1D0h+var_168]; this
0x1800dcbec  mov     [rsp+1D0h+var_168], sil
0x1800dcbf1  mov     [rsp+1D0h+var_160], rsi
0x1800dcbf6  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x1800dcbfb  mov     ebx, eax
0x1800dcbfd  test    eax, eax
0x1800dcbff  jns     short loc_1800DCC21
0x1800dcc01  mov     rcx, [rbp+0D8h]; this
0x1800dcc08  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcc0f  mov     r9d, eax; char *
0x1800dcc12  mov     edx, 45Eh; void *
0x1800dcc17  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcc1c  jmp     loc_1800DD61C
0x1800dcc21  lea     r14, [r15+20h]
0x1800dcc25  mov     [rsp+1D0h+var_180], sil
0x1800dcc2a  mov     rdx, r14; struct Path *
0x1800dcc2d  mov     [rsp+1D0h+var_178], rsi
0x1800dcc32  lea     rcx, [rsp+1D0h+var_180]; this
0x1800dcc37  call    ?Open@OfflineHive@Csl@@QEAAJAEBVPath@2@@Z; Csl::OfflineHive::Open(Csl::Path const &)
0x1800dcc3c  mov     ebx, eax
0x1800dcc3e  test    eax, eax
0x1800dcc40  jns     short loc_1800DCC6C
0x1800dcc42  mov     rcx, [rbp+0D8h]; this
0x1800dcc49  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcc50  mov     r9d, eax; char *
0x1800dcc53  mov     edx, 461h; void *
0x1800dcc58  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcc5d  lea     rcx, [rsp+1D0h+var_180]; this
0x1800dcc62  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x1800dcc67  jmp     loc_1800DD61C
0x1800dcc6c  xor     r8d, r8d; Flags
0x1800dcc6f  mov     [rsp+1D0h+ReturnedState], rsi
0x1800dcc74  lea     r9, [rsp+1D0h+ReturnedState]; ReturnedState
0x1800dcc79  mov     [rbp+0D0h+Privilege], 11h
0x1800dcc83  lea     rcx, [rbp+0D0h+Privilege]; Privilege
0x1800dcc8a  mov     [rbp+0D0h+Privilege+4], 12h
0x1800dcc94  mov     [rbp+0D0h+var_40], 8
0x1800dcc9e  lea     edx, [r8+3]; NumPriv
0x1800dcca2  call    cs:__imp_RtlAcquirePrivilege
0x1800dcca9  nop     dword ptr [rax+rax+00h]
0x1800dccae  test    eax, eax
0x1800dccb0  jns     short loc_1800DCCFD
0x1800dccb2  mov     rcx, [rbp+0D8h]; this
0x1800dccb9  lea     r8, aOnecoreBaseGen; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800dccc0  mov     r9d, eax; char *
0x1800dccc3  mov     edx, 52h ; 'R'; void *
0x1800dccc8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800dcccd  mov     ebx, eax
0x1800dcccf  test    eax, eax
0x1800dccd1  jns     short loc_1800DCCFD
0x1800dccd3  mov     edx, 468h; void *
0x1800dccd8  mov     rcx, [rbp+0D8h]; this
0x1800dccdf  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcce6  mov     r9d, eax; char *
0x1800dcce9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dccee  lea     rcx, [rsp+1D0h+ReturnedState]; this
0x1800dccf3  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800dccf8  jmp     loc_1800DCC5D
0x1800dccfd  mov     rax, [r15+40h]
0x1800dcd01  mov     r12d, [rax+0E4h]
0x1800dcd08  test    r12b, 1
0x1800dcd0c  jz      loc_1800DCECA
0x1800dcd12  mov     edi, 20019h
0x1800dcd17  mov     [rsp+1D0h+hKey], rsi
0x1800dcd1c  mov     edx, edi
0x1800dcd1e  lea     r8, [rsp+1D0h+hKey]
0x1800dcd23  mov     ecx, 1
0x1800dcd28  call    ?OpenRegistryHive@Csl@@YAJW4RegistryHive@1@W4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryHive(Csl::RegistryHive,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800dcd2d  mov     ebx, eax
0x1800dcd2f  test    eax, eax
0x1800dcd31  jns     short loc_1800DCD66
0x1800dcd33  mov     rcx, [rbp+0D8h]; this
0x1800dcd3a  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcd41  mov     r9d, eax; char *
0x1800dcd44  mov     edx, 472h; void *
0x1800dcd49  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcd4e  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800dcd53  test    rcx, rcx
0x1800dcd56  jz      short loc_1800DCCEE
0x1800dcd58  call    cs:__imp_RegCloseKey
0x1800dcd5f  nop     dword ptr [rax+rax+00h]
0x1800dcd64  jmp     short loc_1800DCCEE
0x1800dcd66  lea     r8, [rbp+0D0h+Privilege]
0x1800dcd6d  mov     qword ptr [rbp+0D0h+Privilege], rsi
0x1800dcd74  mov     edx, edi
0x1800dcd76  xor     ecx, ecx
0x1800dcd78  call    ?OpenRegistryHive@Csl@@YAJW4RegistryHive@1@W4RegistryKeyAccess@1@AEAVRegistryKey@1@@Z; Csl::OpenRegistryHive(Csl::RegistryHive,Csl::RegistryKeyAccess,Csl::RegistryKey &)
0x1800dcd7d  mov     ebx, eax
0x1800dcd7f  test    eax, eax
0x1800dcd81  jns     short loc_1800DCDB8
0x1800dcd83  mov     r9d, eax; char *
0x1800dcd86  mov     edx, 477h; void *
0x1800dcd8b  mov     rcx, [rbp+0D8h]; this
0x1800dcd92  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcd99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcd9e  mov     rcx, qword ptr [rbp+0D0h+Privilege]; hKey
0x1800dcda5  test    rcx, rcx
0x1800dcda8  jz      short loc_1800DCD4E
0x1800dcdaa  call    cs:__imp_RegCloseKey
0x1800dcdb1  nop     dword ptr [rax+rax+00h]
0x1800dcdb6  jmp     short loc_1800DCD4E
0x1800dcdb8  lea     rbx, qword_1801BD800
0x1800dcdbf  mov     ecx, [rbx]
0x1800dcdc1  test    ecx, ecx
0x1800dcdc3  jz      short loc_1800DCDDA
0x1800dcdc5  cmp     ecx, 1
0x1800dcdc8  jnz     loc_1800DCF27
0x1800dcdce  lea     r14, [rsp+1D0h+hKey]
0x1800dcdd3  lea     rsi, [rsp+1D0h+var_168]
0x1800dcdd8  jmp     short loc_1800DCDE6
0x1800dcdda  lea     r14, [rbp+0D0h+Privilege]
0x1800dcde1  lea     rsi, [rsp+1D0h+var_180]
0x1800dcde6  mov     rdx, [rbx+8]; unsigned __int16 *
0x1800dcdea  mov     rcx, rsi; this
0x1800dcded  call    ?DeleteKeyRecursive@OfflineHive@Csl@@QEAAJPEBG@Z; Csl::OfflineHive::DeleteKeyRecursive(ushort const *)
0x1800dcdf2  mov     edi, eax
0x1800dcdf4  mov     eax, 80000000h
0x1800dcdf9  lea     ecx, [rdi+rax]
0x1800dcdfc  test    eax, ecx
0x1800dcdfe  jnz     short loc_1800DCE0C
0x1800dce00  cmp     edi, 80070002h
0x1800dce06  jnz     loc_1800DCF39
0x1800dce0c  mov     rcx, [rbx+8]
0x1800dce10  lea     rax, [rbp+0D0h+var_70]
0x1800dce14  mov     [rbp+0D0h+var_80], rax
0x1800dce18  xor     edi, edi
0x1800dce1a  lea     rax, [rbp+0D0h+var_70]
0x1800dce1e  mov     [rbp+0D0h+var_70], di
0x1800dce22  mov     [rbp+0D0h+var_78], rax
0x1800dce26  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800dce2a  mov     [rsp+1D0h+var_158], rcx
0x1800dce2f  inc     rax
0x1800dce32  cmp     [rcx+rax*2], di
0x1800dce36  jnz     short loc_1800DCE2F
0x1800dce38  lea     rdx, [rsp+1D0h+var_158]
0x1800dce3d  mov     [rbp+0D0h+var_158+8], rax
0x1800dce41  lea     rcx, [rbp+0D0h+var_80]; this
0x1800dce45  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x1800dce4a  test    al, al
0x1800dce4c  jz      loc_1800DCFD3
0x1800dce52  lea     r8, [rbp+0D0h+var_80]; struct Csl::OfflineHive *
0x1800dce56  mov     rdx, rsi; struct Csl::RegistryKey *
0x1800dce59  mov     rcx, r14; this
0x1800dce5c  call    ?CopyRegistryTreeToOfflineHive@Csl@@YAJAEAVRegistryKey@1@AEAVOfflineHive@1@AEBVPath@1@@Z; Csl::CopyRegistryTreeToOfflineHive(Csl::RegistryKey &,Csl::OfflineHive &,Csl::Path const &)
0x1800dce61  mov     edi, eax
0x1800dce63  test    eax, eax
0x1800dce65  js      loc_1800DCF9D
0x1800dce6b  mov     rcx, [rbp+0D0h+var_80]; void *
0x1800dce6f  lea     rax, [rbp+0D0h+var_70]
0x1800dce73  cmp     rcx, rax
0x1800dce76  jz      short loc_1800DCE84
0x1800dce78  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dce7f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dce84  add     rbx, 10h
0x1800dce88  lea     rax, off_1801BD860; "Windows\\Fonts"
0x1800dce8f  cmp     rbx, rax
0x1800dce92  jnz     loc_1800DCDBF
0x1800dce98  mov     rcx, qword ptr [rbp+0D0h+Privilege]; hKey
0x1800dce9f  test    rcx, rcx
0x1800dcea2  jz      short loc_1800DCEB0
0x1800dcea4  call    cs:__imp_RegCloseKey
0x1800dceab  nop     dword ptr [rax+rax+00h]
0x1800dceb0  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800dceb5  test    rcx, rcx
0x1800dceb8  jz      short loc_1800DCEC6
0x1800dceba  call    cs:__imp_RegCloseKey
0x1800dcec1  nop     dword ptr [rax+rax+00h]
0x1800dcec6  lea     r14, [r15+20h]
0x1800dceca  mov     edi, 4
0x1800dcecf  test    r12b, 2
0x1800dced3  jz      loc_1800DD15C
0x1800dced9  xor     r12d, r12d
0x1800dcedc  lea     r8, aEnablevirtuali_0; "EnableVirtualizationBasedSecurity"
0x1800dcee3  lea     rdx, aControlset001C_11; "ControlSet001\\Control\\DeviceGuard"
0x1800dceea  lea     rcx, [rsp+1D0h+var_168]; this
0x1800dceef  cmp     [r13+4], r12b
0x1800dcef3  jz      loc_1800DD0D4
0x1800dcef9  mov     [rsp+1D0h+dwFlagsAndAttributes], edi; unsigned int
0x1800dcefd  lea     r9, [rsp+1D0h+var_188]; unsigned __int8 *
0x1800dcf02  mov     [rsp+1D0h+dwCreationDisposition], edi; unsigned int
0x1800dcf06  mov     dword ptr [rsp+1D0h+var_188], 1
0x1800dcf0e  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x1800dcf13  mov     ebx, eax
0x1800dcf15  test    eax, eax
0x1800dcf17  jns     loc_1800DD056
0x1800dcf1d  mov     edx, 4AAh
0x1800dcf22  jmp     loc_1800DCCD8
0x1800dcf27  mov     ebx, 80004005h
0x1800dcf2c  mov     edx, 48Ch
0x1800dcf31  mov     r9d, ebx
0x1800dcf34  jmp     loc_1800DCD8B
0x1800dcf39  mov     rcx, [rbp+0D8h]; this
0x1800dcf40  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcf47  mov     r9d, edi; char *
0x1800dcf4a  mov     edx, 494h; void *
0x1800dcf4f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcf54  mov     rcx, qword ptr [rbp+0D0h+Privilege]; hKey
0x1800dcf5b  test    rcx, rcx
0x1800dcf5e  jz      short loc_1800DCF6C
0x1800dcf60  call    cs:__imp_RegCloseKey
0x1800dcf67  nop     dword ptr [rax+rax+00h]
0x1800dcf6c  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800dcf71  test    rcx, rcx
0x1800dcf74  jz      short loc_1800DCF82
0x1800dcf76  call    cs:__imp_RegCloseKey
0x1800dcf7d  nop     dword ptr [rax+rax+00h]
0x1800dcf82  lea     rcx, [rsp+1D0h+ReturnedState]; this
0x1800dcf87  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800dcf8c  lea     rcx, [rsp+1D0h+var_180]; this
0x1800dcf91  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x1800dcf96  mov     ebx, edi
0x1800dcf98  jmp     loc_1800DD61C
0x1800dcf9d  mov     rcx, [rbp+0D8h]; this
0x1800dcfa4  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcfab  mov     r9d, edi; char *
0x1800dcfae  mov     edx, 49Dh; void *
0x1800dcfb3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcfb8  mov     rcx, [rbp+0D0h+var_80]; void *
0x1800dcfbc  lea     rax, [rbp+0D0h+var_70]
0x1800dcfc0  cmp     rcx, rax
0x1800dcfc3  jz      short loc_1800DCF54
0x1800dcfc5  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dcfcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dcfd1  jmp     short loc_1800DCF54
0x1800dcfd3  mov     rcx, [rbp+0D8h]; this
0x1800dcfda  lea     r8, aOnecoreBaseGen_25; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800dcfe1  mov     r9d, 8007000Eh; char *
0x1800dcfe7  mov     edx, 498h; void *
0x1800dcfec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800dcff1  mov     rcx, [rbp+0D0h+var_80]; void *
0x1800dcff5  lea     rax, [rbp+0D0h+var_70]
0x1800dcff9  cmp     rcx, rax
0x1800dcffc  jz      short loc_1800DD00A
0x1800dcffe  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800dd005  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800dd00a  mov     rcx, qword ptr [rbp+0D0h+Privilege]; hKey
0x1800dd011  test    rcx, rcx
0x1800dd014  jz      short loc_1800DD022
0x1800dd016  call    cs:__imp_RegCloseKey
0x1800dd01d  nop     dword ptr [rax+rax+00h]
0x1800dd022  mov     rcx, [rsp+1D0h+hKey]; hKey
0x1800dd027  test    rcx, rcx
0x1800dd02a  jz      short loc_1800DD038
0x1800dd02c  call    cs:__imp_RegCloseKey
0x1800dd033  nop     dword ptr [rax+rax+00h]
0x1800dd038  lea     rcx, [rsp+1D0h+ReturnedState]; this
0x1800dd03d  call    ??1AcquiredPrivileges@Csl@@QEAA@XZ; Csl::AcquiredPrivileges::~AcquiredPrivileges(void)
0x1800dd042  lea     rcx, [rsp+1D0h+var_180]; this
0x1800dd047  call    ??1OfflineHive@Csl@@QEAA@XZ; Csl::OfflineHive::~OfflineHive(void)
0x1800dd04c  mov     ebx, 8007000Eh
0x1800dd051  jmp     loc_1800DD61C
0x1800dd056  mov     [rsp+1D0h+dwFlagsAndAttributes], edi; unsigned int
0x1800dd05a  lea     r9, [rsp+1D0h+var_188]; unsigned __int8 *
0x1800dd05f  lea     r8, aHotpatchrestri; "HotPatchRestrictions"
0x1800dd066  mov     [rsp+1D0h+dwCreationDisposition], edi; unsigned int
0x1800dd06a  lea     rdx, aControlset001C_8; "ControlSet001\\Control\\Session Manager"...
0x1800dd071  mov     dword ptr [rsp+1D0h+var_188], 1
0x1800dd079  lea     rcx, [rsp+1D0h+var_168]; this
0x1800dd07e  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x1800dd083  mov     ebx, eax
0x1800dd085  test    eax, eax
0x1800dd087  jns     short loc_1800DD093
0x1800dd089  mov     edx, 4B0h
0x1800dd08e  jmp     loc_1800DCCD8
0x1800dd093  mov     eax, [r13+0]
0x1800dd097  lea     r9, [rsp+1D0h+var_188]; unsigned __int8 *
0x1800dd09c  mov     [rsp+1D0h+dwFlagsAndAttributes], edi; unsigned int
0x1800dd0a0  lea     r8, aHotpatchtables; "HotPatchTableSize"
0x1800dd0a7  lea     rdx, aControlset001C_8; "ControlSet001\\Control\\Session Manager"...
0x1800dd0ae  mov     dword ptr [rsp+1D0h+var_188], eax
0x1800dd0b2  lea     rcx, [rsp+1D0h+var_168]; this
0x1800dd0b7  mov     [rsp+1D0h+dwCreationDisposition], edi; unsigned int
0x1800dd0bb  call    ?SetValue@OfflineHive@Csl@@QEAAJPEBG0PEBEKK@Z; Csl::OfflineHive::SetValue(ushort const *,ushort const *,uchar const *,ulong,ulong)
0x1800dd0c0  mov     ebx, eax
0x1800dd0c2  test    eax, eax
0x1800dd0c4  jns     loc_1800DD15F
0x1800dd0ca  mov     edx, 4B6h
0x1800dd0cf  jmp     loc_1800DCCD8
0x1800dd0d4  call    ?DeleteValue@OfflineHive@Csl@@QEAAJQEBG0@Z; Csl::OfflineHive::DeleteValue(ushort const * const,ushort const * const)
0x1800dd0d9  mov     esi, 80000000h
0x1800dd0de  mov     ebx, eax
0x1800dd0e0  mov     r13d, 80070002h
0x1800dd0e6  lea     ecx, [rax+rsi]
  ... truncated ...
```
