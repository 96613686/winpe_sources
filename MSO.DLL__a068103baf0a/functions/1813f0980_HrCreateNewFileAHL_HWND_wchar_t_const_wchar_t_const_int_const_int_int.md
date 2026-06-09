# HrCreateNewFileAHL(HWND__ *,wchar_t const *,wchar_t const *,int const *,int,int *)

- ea: `0x1813f0980`
- end: `0x1813f1532`
- name: `?HrCreateNewFileAHL@@YAJPEAUHWND__@@PEB_W1PEBHHPEAH@Z`
- size: `2994`
- prototype: `int(HWND, const wchar_t *, const wchar_t *, const int *, int, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1813f18b0`
- `0x1813f9cd4`

## callees

- `0x180032d80`
- `0x1800410a0`
- `0x180087e30`
- `0x18008a404`
- `0x1800bbe90`
- `0x1800e8dc0`
- `0x1800f9a68`
- `0x18011fab8`
- `0x1801255bc`
- `0x180165d54`
- `0x1801ca044`
- `0x1801ffba8`
- `0x18022897c`
- `0x180239aa0`
- `0x18023c2e0`
- `0x1809e9028`
- `0x1813f08a0`
- `0x1813f0980`
- `0x1813f1e10`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1813f1399`
- `KERNEL32!GetLastError` at `0x1813f13aa`
- `KERNEL32!GetLastError` at `0x1813f149f`
- `KERNEL32!GetLastError` at `0x1813f14a9`
- `KERNEL32!GetLastError` at `0x1813f1399`
- `KERNEL32!GetLastError` at `0x1813f13aa`
- `KERNEL32!GetLastError` at `0x1813f149f`
- `KERNEL32!GetLastError` at `0x1813f14a9`
- `KERNEL32!GetFileAttributesW` at `0x1813f104a`
- `KERNEL32!GetFileAttributesW` at `0x1813f104a`
- `KERNEL32!WriteFile` at `0x1813f0f53`
- `KERNEL32!WriteFile` at `0x1813f1264`
- `KERNEL32!WriteFile` at `0x1813f0f53`
- `KERNEL32!WriteFile` at `0x1813f1264`
- `KERNEL32!CloseHandle` at `0x1813f0f5c`
- `KERNEL32!CloseHandle` at `0x1813f0ff4`
- `KERNEL32!CloseHandle` at `0x1813f126d`
- `KERNEL32!CloseHandle` at `0x1813f14e9`
- `KERNEL32!CloseHandle` at `0x1813f0f5c`
- `KERNEL32!CloseHandle` at `0x1813f0ff4`
- `KERNEL32!CloseHandle` at `0x1813f126d`
- `KERNEL32!CloseHandle` at `0x1813f14e9`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1813f10ec`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x1813f10ec`
- `KERNEL32!GetTempPathW` at `0x1813f0d6e`
- `KERNEL32!GetTempPathW` at `0x1813f0d6e`
- `KERNEL32!FormatMessageW` at `0x1813f1316`
- `KERNEL32!FormatMessageW` at `0x1813f1316`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1813f13bd`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1813f13bd`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x1813f13dd`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x1813f13dd`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x1813f140a`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x1813f140a`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1813f1465`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x1813f1465`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x1813f1435`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x1813f1435`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1813f147f`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1813f147f`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1813f13c8`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1813f13c8`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0a6b`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0a86`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0aa1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0abc`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0a6b`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0a86`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0aa1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813f0abc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f1495`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f14dc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f1500`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f1495`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f14dc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813f1500`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0efc`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0f0f`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0f23`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0efc`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0f0f`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813f0f23`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x1813f132b`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x1813f132b`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f0eb4`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f0fde`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f1239`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f136d`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f0eb4`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f0fde`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f1239`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x1813f136d`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1813f0c83`
- `Mso20Win32Client!__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z` at `0x1813f0c83`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0b22`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0b39`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0d90`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f116c`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f1180`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f11b4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f11c8`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0b22`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0b39`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f0d90`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f116c`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f1180`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f11b4`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813f11c8`
- `VCRUNTIME140!wcschr` at `0x1813f1016`
- `VCRUNTIME140!wcschr` at `0x1813f12d4`
- `VCRUNTIME140!wcschr` at `0x1813f1016`
- `VCRUNTIME140!wcschr` at `0x1813f12d4`
- `VCRUNTIME140!wcsrchr` at `0x1813f0a19`
- `VCRUNTIME140!wcsrchr` at `0x1813f0a19`
- `ole32!CoTaskMemFree` at `0x1813f108f`
- `ole32!CoTaskMemFree` at `0x1813f10c5`
- `ole32!CoTaskMemFree` at `0x1813f111a`
- `ole32!CoTaskMemFree` at `0x1813f113a`
- `ole32!CoTaskMemFree` at `0x1813f108f`
- `ole32!CoTaskMemFree` at `0x1813f10c5`
- `ole32!CoTaskMemFree` at `0x1813f111a`
- `ole32!CoTaskMemFree` at `0x1813f113a`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0bb1`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0bec`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0c31`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0bb1`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0bec`
- `ADVAPI32!RegQueryValueExW` at `0x1813f0c31`
- `ADVAPI32!RegCloseKey` at `0x1813f0cce`
- `ADVAPI32!RegCloseKey` at `0x1813f0ce6`
- `ADVAPI32!RegCloseKey` at `0x1813f0d03`
- `ADVAPI32!RegCloseKey` at `0x1813f0d13`
- `ADVAPI32!RegCloseKey` at `0x1813f0cce`
- `ADVAPI32!RegCloseKey` at `0x1813f0ce6`
- `ADVAPI32!RegCloseKey` at `0x1813f0d03`
- `ADVAPI32!RegCloseKey` at `0x1813f0d13`
- `ADVAPI32!RegQueryValueW` at `0x1813f0b02`
- `ADVAPI32!RegQueryValueW` at `0x1813f0b02`
- `ADVAPI32!RegQueryValueExA` at `0x1813f0c73`
- `ADVAPI32!RegQueryValueExA` at `0x1813f0cb8`
- `ADVAPI32!RegQueryValueExA` at `0x1813f0c73`
- `ADVAPI32!RegQueryValueExA` at `0x1813f0cb8`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813f1076`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813f10ac`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813f1076`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813f10ac`
- `SHELL32!SHGetPathFromIDListEx` at `0x1813f110f`
- `SHELL32!SHGetPathFromIDListEx` at `0x1813f112f`
- `SHELL32!SHGetPathFromIDListEx` at `0x1813f110f`
- `SHELL32!SHGetPathFromIDListEx` at `0x1813f112f`

## string_xrefs

- `0x1813f09e4`: `HrCreateNewFileAHL`
- `0x1813f0c25`: `Command`

## pseudocode

```c
__int64 __fastcall HrCreateNewFileAHL(
        HWND a1,
        const wchar_t *a2,
        wchar_t *a3,
        ITEMIDLIST *a4,
        unsigned int a5,
        int *a6)
{
  LPITEMIDLIST v6; // r15
  const wchar_t *v7; // r13
  __int64 v8; // rbx
  __int64 v9; // rax
  __int64 v10; // r8
  wchar_t *v11; // rdi
  unsigned int v12; // ebx
  int v13; // r12d
  void *v14; // r14
  char v15; // di
  char v16; // si
  unsigned int v17; // r8d
  HKEY v18; // rcx
  unsigned int v19; // r9d
  const char *const near *v20; // rsi
  int v21; // edi
  const wchar_t **i; // r15
  void *v23; // r14
  __int64 v24; // rdi
  void *v25; // rax
  unsigned int v26; // esi
  __int64 v27; // rax
  __int64 v28; // rax
  void *v29; // rax
  void *v30; // rsi
  int v31; // esi
  va_list v32; // rdi
  wchar_t *v33; // rax
  void *FileW; // rax
  HINSTANCE v35; // rax
  __int64 ResourceString; // rax
  int v37; // edx
  int v38; // edx
  Mso::Alerts *v39; // rcx
  const struct MsoReserveTag *TelemetryNamespace; // rax
  const struct Mso::Alerts::AlertParam *v41; // r9
  unsigned int v43; // r9d
  signed int LastError; // eax
  unsigned int v45; // edi
  char v46; // [rsp+42h] [rbp-BEh]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-A8h] BYREF
  const char *v51; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v52; // [rsp+68h] [rbp-98h] BYREF
  HWND v53; // [rsp+70h] [rbp-90h]
  _BYTE v54[16]; // [rsp+78h] [rbp-88h] BYREF
  LONG cbData; // [rsp+88h] [rbp-78h] BYREF
  DWORD lpcbData; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD v57; // [rsp+90h] [rbp-70h] BYREF
  int *v58; // [rsp+98h] [rbp-68h]
  wchar_t *v59; // [rsp+A0h] [rbp-60h]
  va_list Arguments[4]; // [rsp+A8h] [rbp-58h] BYREF
  char v61[24]; // [rsp+C8h] [rbp-38h] BYREF
  char Source[48]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v63[24]; // [rsp+110h] [rbp+10h] BYREF
  struct _SHELLEXECUTEINFOW Dst; // [rsp+140h] [rbp+40h] BYREF
  char v65; // [rsp+1B8h] [rbp+B8h]
  char Destination[160]; // [rsp+350h] [rbp+250h] BYREF
  wchar_t lpData[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR Data[272]; // [rsp+600h] [rbp+500h] BYREF
  WCHAR v69[264]; // [rsp+820h] [rbp+720h] BYREF
  WCHAR Buffer[264]; // [rsp+A30h] [rbp+930h] BYREF
  wchar_t v71[264]; // [rsp+C40h] [rbp+B40h] BYREF

  v6 = a4;
  ppidl = a4;
  v59 = a3;
  v7 = a2;
  v53 = a1;
  v58 = a6;
  LOBYTE(a2) = 2;
  v8 = Mso::Telemetry::EventFlags::EventFlags(Arguments, a2, 2);
  v51 = "HrCreateNewFileAHL";
  v9 = Office::FileIO::MSO::EventName(v61, &v51);
  LOBYTE(v10) = 2;
  Mso::Telemetry::Activity::Activity(v54, v9, v10, v8);
  v11 = wcsrchr(v7, 0x2Eu);
  v12 = 0;
  v52 = 0;
  hKey = 0;
  v46 = 0;
  LODWORD(v51) = 0;
  v13 = 0;
  v14 = 0;
  Type = 0;
  lpcbData = 520;
  v57 = 520;
  NumberOfBytesWritten = 0;
  cbData = 520;
  if ( !v11 )
  {
LABEL_34:
    if ( a5 && (unsigned int)sub_1813F1E10() != 6 )
    {
      v12 = -2147467260;
      Mso::Telemetry::SetActivityResultHr(
        (Mso::Telemetry *)v54,
        (struct Mso::Telemetry::Activity *)0x80004004LL,
        504443682,
        v19);
      goto LABEL_108;
    }
    FileW = (void *)MsoCreateFileW(v7, 0x40000000, 0, 0, (unsigned int)(*(_DWORD *)&v6->mkid.cb != 0) + 1, 128, 0);
    if ( FileW == (void *)-1LL )
      goto LABEL_102;
    CloseHandle(FileW);
    goto LABEL_115;
  }
  if ( !(unsigned int)MsoFWzEqual(v11, L".htm", 1) && !(unsigned int)MsoFWzEqual(v11, L".html", 1) )
  {
    if ( !(unsigned int)MsoFWzEqual(v11, L".mht", 1) && !(unsigned int)MsoFWzEqual(v11, L".mhtml", 1) )
    {
      if ( (unsigned int)MsoRegOpenKeyExW(HKEY_CLASSES_ROOT, v11, 0x20019u, &v52) )
      {
        v18 = v52;
LABEL_28:
        if ( v18 )
          RegCloseKey(v18);
        if ( hKey )
          RegCloseKey(hKey);
        if ( v14 )
        {
          operator delete(v14);
          v14 = 0;
        }
        goto LABEL_34;
      }
      if ( RegQueryValueW(HKEY_CLASSES_ROOT, v11, Data, &cbData)
        || (MsoWzAppend(L"\\", Data, 270),
            MsoWzAppend(L"ShellNew", Data, 270),
            (unsigned int)MsoRegOpenKeyExW(v52, Data, 0x20019u, &hKey)) )
      {
        MsoWzCopy(L"ShellNew", Data, 270);
      }
      if ( (unsigned int)MsoRegOpenKeyExW(v52, Data, 0x20019u, &hKey) )
      {
        v15 = 0;
        v16 = 0;
        goto LABEL_26;
      }
      if ( RegQueryValueExW(hKey, L"NullFile", 0, &Type, 0, 0) )
      {
        if ( !RegQueryValueExW(hKey, L"FileName", 0, &Type, (LPBYTE)lpData, &lpcbData) && Type == 1 )
        {
          v16 = 1;
          v15 = 0;
LABEL_24:
          RegCloseKey(hKey);
          hKey = 0;
LABEL_26:
          RegCloseKey(v52);
          v18 = 0;
          v52 = 0;
          goto LABEL_57;
        }
        if ( RegQueryValueExW(hKey, L"Command", 0, &Type, (LPBYTE)v71, &v57) || Type - 1 > 1 )
        {
          if ( !RegQueryValueExA(hKey, "Data", 0, &Type, 0, &NumberOfBytesWritten) )
          {
            v14 = Mso::Memory::AllocateEx((Mso::Memory *)NumberOfBytesWritten, 0, v17);
            if ( !v14 )
              goto LABEL_109;
            RegQueryValueExA(hKey, "Data", 0, &Type, (LPBYTE)v14, &NumberOfBytesWritten);
            v46 = 1;
          }
        }
        else
        {
          LODWORD(v51) = 1;
        }
        v15 = 0;
      }
      else
      {
        v15 = 1;
      }
      v16 = 0;
      goto LABEL_24;
    }
    v13 = 1;
  }
  if ( !GetTempPathW(0x104u, Buffer) )
    goto LABEL_104;
  MsoWzAppend(L"msohdinh.tmp", Buffer, 261);
  strcpy(Source, "MIME-Version: 1.0\r\nContent-Type: text/html\r\n\r\n");
  strcpy((char *)v63, "<html>\r\n<head>\r\n<meta name=\"ProgId\" content=\"");
  strcpy(v61, "\">\r\n</head>\r\n</html>");
  v20 = 0;
  v21 = 0;
  for ( i = (const wchar_t **)&rgwchAppName; (__int64)i < (__int64)L"Microsoft PowerPoint"; ++i )
  {
    if ( Mso::StringExact::Equal(v59, *i) )
    {
      v20 = (&rgchHtmlProgId)[v21];
      break;
    }
    ++v21;
  }
  if ( v21 < 6 && v20 )
  {
    if ( v13 && (unsigned int)(v21 - 3) <= 2 )
      v20 = rgchHtmlProgId;
    v23 = (void *)MsoCreateFileW(Buffer, 0x40000000, 0, 0, 2, 128, 0);
    v24 = -1;
    if ( v23 == (void *)-1LL )
      goto LABEL_104;
    Destination[0] = 0;
    if ( v13 )
      MsoSzCopy(Source, Destination, 149);
    MsoSzAppend(v63, Destination, 149);
    MsoSzAppend(v20, Destination, 149);
    MsoSzAppend(v61, Destination, 149);
    do
      ++v24;
    while ( Destination[v24] );
    NumberOfBytesWritten = v24;
    WriteFile(v23, Destination, v24, &NumberOfBytesWritten, 0);
    CloseHandle(v23);
    if ( !(unsigned int)sub_1813F08A0(Buffer, v7, a5, *(unsigned int *)&ppidl->mkid.cb) )
      goto LABEL_104;
    *v58 = 0;
    Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v54, 1);
LABEL_108:
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v54);
    return v12;
  }
  v18 = v52;
  v6 = ppidl;
  v15 = 0;
  v16 = 0;
LABEL_57:
  if ( v15 )
  {
    v25 = (void *)MsoCreateFileW(v7, 0x40000000, 0, 0, (unsigned int)(*(_DWORD *)&v6->mkid.cb != 0) + 1, 128, 0);
    if ( v25 != (void *)-1LL )
    {
      CloseHandle(v25);
      goto LABEL_95;
    }
    goto LABEL_102;
  }
  if ( !v16 )
  {
    if ( v46 )
    {
      v29 = (void *)MsoCreateFileW(v7, 0x40000000, 0, 0, (unsigned int)(*(_DWORD *)&v6->mkid.cb != 0) + 1, 128, 0);
      v30 = v29;
      if ( v29 != (void *)-1LL )
      {
        WriteFile(v29, v14, NumberOfBytesWritten, &NumberOfBytesWritten, 0);
        CloseHandle(v30);
        operator delete(v14);
        goto LABEL_95;
      }
      goto LABEL_102;
    }
    v31 = (int)v51;
    if ( (_DWORD)v51 )
    {
      memset_0(&Dst, 0, sizeof(Dst));
      wcscpy((wchar_t *)&Dst, L"p");
      Dst.fMask = 512;
      v32 = (va_list)v53;
      Dst.hwnd = v53;
      Dst.nShow = 10;
      Dst.lpFile = v71;
      v33 = wcschr(v71, 0x20u);
      if ( v33 )
      {
        *v33 = 0;
        Arguments[0] = v32;
        Arguments[1] = (va_list)v7;
        FormatMessageW(0x2400u, v33 + 1, 0, 0, v69, 0x104u, Arguments);
        v33 = v69;
      }
      Dst.lpParameters = v33;
      MsoShellExecuteExW(&Dst);
      if ( Dst.hInstApp <= HINSTANCE_ERROR )
        goto LABEL_102;
LABEL_100:
      *v58 = v31;
LABEL_115:
      Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v54, 1);
      Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v54);
      return 0;
    }
    goto LABEL_28;
  }
  v26 = 0;
  if ( wcschr(lpData, 0x5Cu) )
    goto LABEL_63;
  MsoWzCopy(lpData, v69, 260);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( v26 < 2 )
        {
          ppidl = 0;
          if ( SHGetSpecialFolderLocation(0, v26 != 0 ? 45 : 21, &ppidl) >= 0 && ppidl )
          {
            SHGetPathFromIDListEx(ppidl, (PWSTR)&Dst, 0x104u, 2);
            CoTaskMemFree(ppidl);
            goto LABEL_85;
          }
          if ( ppidl )
            CoTaskMemFree(ppidl);
          ++v26;
        }
        if ( v26 != 2 )
          break;
        ppidl = 0;
        if ( SHGetSpecialFolderLocation(0, 36, &ppidl) >= 0 && ppidl )
        {
          SHGetPathFromIDListEx(ppidl, (PWSTR)&Dst, 0x104u, 2);
          CoTaskMemFree(ppidl);
          v27 = -1;
          do
            ++v27;
          while ( *((_WORD *)&Dst.cbSize + v27) );
          if ( v63[(int)v27 + 23] != 92 )
            MsoWzAppend(L"\\", &Dst, 260);
          MsoWzAppend(L"ShellNew\\", &Dst, 260);
          goto LABEL_85;
        }
        if ( ppidl )
          CoTaskMemFree(ppidl);
        v26 = 3;
      }
      if ( v26 != 3 )
        goto LABEL_102;
      if ( ExpandEnvironmentStringsW(L"%windir%\\ShellNew\\", (LPWSTR)&Dst, 0x103u) )
        break;
      v26 = 4;
    }
LABEL_85:
    ++v26;
    v28 = -1;
    do
      ++v28;
    while ( *((_WORD *)&Dst.cbSize + v28) );
    if ( v63[(int)v28 + 23] != 92 )
      MsoWzAppend(L"\\", &Dst, 260);
    MsoWzAppend(v69, &Dst, 260);
    MsoWzCopy((const wchar_t *)&Dst, lpData, 260);
LABEL_63:
    ;
  }
  while ( GetFileAttributesW(lpData) == -1 );
  if ( (unsigned int)sub_1813F08A0(lpData, v7, a5, *(unsigned int *)&v6->mkid.cb) )
  {
LABEL_95:
    v31 = (int)v51;
    goto LABEL_100;
  }
LABEL_102:
  if ( v14 )
    operator delete(v14);
LABEL_104:
  if ( a5 && GetLastError() != 183 && GetLastError() != 80 )
  {
    Mso::Alerts::CreateDefaultAlertParam(&Dst);
    v35 = MsoLocLibraryFromAlias(0xF902F7ED);
    ResourceString = Mso::Strings::LoadResourceString(Arguments, v35, 327726);
    std::wstring::operator=(&Dst.lpParameters, ResourceString);
    std::basic_string<char16_t>::~basic_string<char16_t>(Arguments);
    std::wstring::operator=(&Dst.lpIDList, &Dst.lpParameters);
    LODWORD(Dst.hIcon) = Mso::Alerts::GetAlertIdFromMsoIds((Mso::Alerts *)0x5002E, v37);
    BYTE4(Dst.hMonitor) = 1;
    *(_WORD *)((char *)&Dst.hMonitor + 5) = *(_WORD *)((char *)&v53 + 5);
    HIBYTE(Dst.hMonitor) = HIBYTE(v53);
    LODWORD(Dst.hProcess) = Mso::Alerts::GetWatsonAlertIdFromMsoIds((Mso::Alerts *)0x5002E, v38);
    BYTE4(Dst.hProcess) = 1;
    *(_WORD *)((char *)&Dst.hProcess + 5) = *(_WORD *)((char *)&v53 + 5);
    HIBYTE(Dst.hProcess) = HIBYTE(v53);
    v65 = 1;
    TelemetryNamespace = Mso::Alerts::GetTelemetryNamespace(v39);
    LODWORD(v51) = 504443681;
    v12 = Mso::Alerts::ShowAlert(
            (Mso::Alerts *)&v51,
            TelemetryNamespace,
            (const struct Mso::Telemetry::TelemetryNamespace *)&Dst,
            v41);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(&Dst);
    goto LABEL_108;
  }
LABEL_109:
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v45 = LastError;
    if ( LastError > 0 )
      v45 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v45 = -2147467259;
  }
  Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v54, (struct Mso::Telemetry::Activity *)v45, 504443680, v43);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v54);
  return v45;
}

```

## disassembly

```asm
0x1813f0980  mov     [rsp-8+arg_18], rbx
0x1813f0985  push    rbp
0x1813f0986  push    rsi
0x1813f0987  push    rdi
0x1813f0988  push    r12
0x1813f098a  push    r13
0x1813f098c  push    r14
0x1813f098e  push    r15
0x1813f0990  lea     rbp, [rsp-0D60h]
0x1813f0998  sub     rsp, 0E60h
0x1813f099f  mov     rax, cs:__security_cookie
0x1813f09a6  xor     rax, rsp
0x1813f09a9  mov     [rbp+0D90h+var_40], rax
0x1813f09b0  mov     r15, r9
0x1813f09b3  mov     [rsp+0E90h+ppidl], r9
0x1813f09b8  mov     [rbp+0D90h+var_DF0], r8
0x1813f09bc  mov     r13, rdx
0x1813f09bf  mov     [rsp+0E90h+var_E20], rcx
0x1813f09c4  mov     rax, [rbp+0D90h+arg_28]
0x1813f09cb  mov     [rbp+0D90h+var_DF8], rax
0x1813f09cf  mov     r8d, 2
0x1813f09d5  mov     dl, r8b
0x1813f09d8  lea     rcx, [rbp+0D90h+var_DE8]
0x1813f09dc  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories)
0x1813f09e1  mov     rbx, rax
0x1813f09e4  lea     rax, aHrcreatenewfil; "HrCreateNewFileAHL"
0x1813f09eb  mov     [rsp+0E90h+var_E30], rax
0x1813f09f0  lea     rdx, [rsp+0E90h+var_E30]
0x1813f09f5  lea     rcx, [rbp+0D90h+var_DC8]
0x1813f09f9  call    ?EventName@MSO@FileIO@Office@@YA?AU0Telemetry@Mso@@AEBUValidEventName@45@@Z; Office::FileIO::MSO::EventName(Mso::Telemetry::ValidEventName const &)
0x1813f09fe  mov     r9, rbx
0x1813f0a01  mov     r8b, 2
0x1813f0a04  mov     rdx, rax
0x1813f0a07  lea     rcx, [rsp+0E90h+var_E18]
0x1813f0a0c  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@W4ActivityAggregationMode@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::ActivityAggregationMode,Mso::Telemetry::EventFlags const &)
0x1813f0a11  mov     edx, 2Eh ; '.'; Ch
0x1813f0a16  mov     rcx, r13; Str
0x1813f0a19  call    cs:__imp_wcsrchr
0x1813f0a1f  mov     rdi, rax
0x1813f0a22  xor     ebx, ebx
0x1813f0a24  mov     [rsp+0E90h+var_E28], rbx
0x1813f0a29  mov     [rsp+0E90h+hKey], rbx
0x1813f0a2e  mov     [rsp+0E90h+var_E4E], bl
0x1813f0a32  mov     dword ptr [rsp+0E90h+var_E30], ebx
0x1813f0a36  mov     r12d, ebx
0x1813f0a39  mov     r14d, ebx
0x1813f0a3c  mov     [rsp+0E90h+Type], ebx
0x1813f0a40  mov     eax, 208h
0x1813f0a45  mov     [rbp+0D90h+var_E04], eax
0x1813f0a48  mov     [rbp+0D90h+var_E00], eax
0x1813f0a4b  mov     [rsp+0E90h+NumberOfBytesWritten], ebx
0x1813f0a4f  mov     [rbp+0D90h+cbData], eax
0x1813f0a52  lea     esi, [rbx+1]
0x1813f0a55  test    rdi, rdi
0x1813f0a58  jz      loc_1813F0D29
0x1813f0a5e  mov     r8d, esi
0x1813f0a61  lea     rdx, ?vcwzHtmExt@@3QB_WB; ".htm"
0x1813f0a68  mov     rcx, rdi
0x1813f0a6b  call    cs:__imp_MsoFWzEqual
0x1813f0a71  test    eax, eax
0x1813f0a73  jnz     loc_1813F0D62
0x1813f0a79  mov     r8d, esi
0x1813f0a7c  lea     rdx, ?vcwzHtmlExt@@3QB_WB; ".html"
0x1813f0a83  mov     rcx, rdi
0x1813f0a86  call    cs:__imp_MsoFWzEqual
0x1813f0a8c  test    eax, eax
0x1813f0a8e  jnz     loc_1813F0D62
0x1813f0a94  mov     r8d, esi
0x1813f0a97  lea     rdx, ?vcwzMhtExt@@3QB_WB; ".mht"
0x1813f0a9e  mov     rcx, rdi
0x1813f0aa1  call    cs:__imp_MsoFWzEqual
0x1813f0aa7  test    eax, eax
0x1813f0aa9  jnz     loc_1813F0D5F
0x1813f0aaf  mov     r8d, esi
0x1813f0ab2  lea     rdx, ?vcwzMhtmlExt@@3QB_WB; ".mhtml"
0x1813f0ab9  mov     rcx, rdi
0x1813f0abc  call    cs:__imp_MsoFWzEqual
0x1813f0ac2  test    eax, eax
0x1813f0ac4  jnz     loc_1813F0D5F
0x1813f0aca  lea     r9, [rsp+0E90h+var_E28]; HKEY *
0x1813f0acf  mov     esi, 20019h
0x1813f0ad4  mov     r8d, esi; unsigned int
0x1813f0ad7  mov     rdx, rdi; lpSubKey
0x1813f0ada  mov     r12, 0FFFFFFFF80000000h
0x1813f0ae1  mov     rcx, r12; hKey
0x1813f0ae4  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1813f0ae9  test    eax, eax
0x1813f0aeb  jnz     loc_1813F0CF9
0x1813f0af1  lea     r9, [rbp+0D90h+cbData]; lpcbData
0x1813f0af5  lea     r8, [rbp+0D90h+Data]; lpData
0x1813f0afc  mov     rdx, rdi; lpSubKey
0x1813f0aff  mov     rcx, r12; hKey
0x1813f0b02  call    cs:__imp_RegQueryValueW
0x1813f0b08  mov     edi, 10Eh
0x1813f0b0d  test    eax, eax
0x1813f0b0f  jnz     short loc_1813F0B5C
0x1813f0b11  mov     r8d, edi
0x1813f0b14  lea     rdx, [rbp+0D90h+Data]
0x1813f0b1b  lea     rcx, SubBlock; "\\"
0x1813f0b22  call    cs:__imp_MsoWzAppend
0x1813f0b28  mov     r8d, edi
0x1813f0b2b  lea     rdx, [rbp+0D90h+Data]
0x1813f0b32  lea     rcx, aShellnew_0; "ShellNew"
0x1813f0b39  call    cs:__imp_MsoWzAppend
0x1813f0b3f  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x1813f0b44  mov     r8d, esi; unsigned int
0x1813f0b47  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x1813f0b4e  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x1813f0b53  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1813f0b58  test    eax, eax
0x1813f0b5a  jz      short loc_1813F0B72
0x1813f0b5c  mov     r8d, edi; int
0x1813f0b5f  lea     rdx, [rbp+0D90h+Data]; Destination
0x1813f0b66  lea     rcx, aShellnew_0; "ShellNew"
0x1813f0b6d  call    ?MsoWzCopy@@YAPEA_WPEB_WPEA_WH@Z; MsoWzCopy(wchar_t const *,wchar_t *,int)
0x1813f0b72  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x1813f0b77  mov     r8d, esi; unsigned int
0x1813f0b7a  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x1813f0b81  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x1813f0b86  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1813f0b8b  test    eax, eax
0x1813f0b8d  jnz     loc_1813F0CDB
0x1813f0b93  mov     [rsp+0E90h+lpcbData], rbx; lpcbData
0x1813f0b98  mov     [rsp+0E90h+lpData], rbx; lpData
0x1813f0b9d  lea     r9, [rsp+0E90h+Type]; lpType
0x1813f0ba2  xor     r8d, r8d; lpReserved
0x1813f0ba5  lea     rdx, aNullfile; "NullFile"
0x1813f0bac  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0bb1  call    cs:__imp_RegQueryValueExW
0x1813f0bb7  test    eax, eax
0x1813f0bb9  jnz     short loc_1813F0BC3
0x1813f0bbb  mov     dil, 1
0x1813f0bbe  jmp     loc_1813F0CC6
0x1813f0bc3  lea     rax, [rbp+0D90h+var_E04]
0x1813f0bc7  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x1813f0bcc  lea     rax, [rbp+0D90h+var_AA0]
0x1813f0bd3  mov     [rsp+0E90h+lpData], rax; lpData
0x1813f0bd8  lea     r9, [rsp+0E90h+Type]; lpType
0x1813f0bdd  xor     r8d, r8d; lpReserved
0x1813f0be0  lea     rdx, aFilename_4; "FileName"
0x1813f0be7  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0bec  call    cs:__imp_RegQueryValueExW
0x1813f0bf2  test    eax, eax
0x1813f0bf4  jnz     short loc_1813F0C08
0x1813f0bf6  cmp     [rsp+0E90h+Type], 1
0x1813f0bfb  jnz     short loc_1813F0C08
0x1813f0bfd  mov     sil, 1
0x1813f0c00  mov     dil, bl
0x1813f0c03  jmp     loc_1813F0CC9
0x1813f0c08  lea     rax, [rbp+0D90h+var_E00]
0x1813f0c0c  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x1813f0c11  lea     rax, [rbp+0D90h+var_250]
0x1813f0c18  mov     [rsp+0E90h+lpData], rax; lpData
0x1813f0c1d  lea     r9, [rsp+0E90h+Type]; lpType
0x1813f0c22  xor     r8d, r8d; lpReserved
0x1813f0c25  lea     rdx, aCommand_5; "Command"
0x1813f0c2c  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0c31  call    cs:__imp_RegQueryValueExW
0x1813f0c37  test    eax, eax
0x1813f0c39  jnz     short loc_1813F0C50
0x1813f0c3b  mov     eax, [rsp+0E90h+Type]
0x1813f0c3f  dec     eax
0x1813f0c41  cmp     eax, 1
0x1813f0c44  ja      short loc_1813F0C50
0x1813f0c46  mov     dword ptr [rsp+0E90h+var_E30], 1
0x1813f0c4e  jmp     short loc_1813F0CC3
0x1813f0c50  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x1813f0c55  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x1813f0c5a  mov     [rsp+0E90h+lpData], rbx; lpData
0x1813f0c5f  lea     r9, [rsp+0E90h+Type]; lpType
0x1813f0c64  xor     r8d, r8d; lpReserved
0x1813f0c67  lea     rdx, aData_6; "Data"
0x1813f0c6e  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0c73  call    cs:__imp_RegQueryValueExA
0x1813f0c79  test    eax, eax
0x1813f0c7b  jnz     short loc_1813F0CC3
0x1813f0c7d  mov     ecx, [rsp+0E90h+NumberOfBytesWritten]
0x1813f0c81  xor     edx, edx
0x1813f0c83  call    cs:__imp_?AllocateEx@Memory@Mso@@YAPEAX_KK@Z; Mso::Memory::AllocateEx(unsigned __int64,ulong)
0x1813f0c89  mov     r14, rax
0x1813f0c8c  test    rax, rax
0x1813f0c8f  jz      loc_1813F149F
0x1813f0c95  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x1813f0c9a  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x1813f0c9f  mov     [rsp+0E90h+lpData], r14; lpData
0x1813f0ca4  lea     r9, [rsp+0E90h+Type]; lpType
0x1813f0ca9  xor     r8d, r8d; lpReserved
0x1813f0cac  lea     rdx, aData_6; "Data"
0x1813f0cb3  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0cb8  call    cs:__imp_RegQueryValueExA
0x1813f0cbe  mov     [rsp+0E90h+var_E4E], 1
0x1813f0cc3  mov     dil, bl
0x1813f0cc6  mov     sil, bl
0x1813f0cc9  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0cce  call    cs:__imp_RegCloseKey
0x1813f0cd4  mov     [rsp+0E90h+hKey], rbx
0x1813f0cd9  jmp     short loc_1813F0CE1
0x1813f0cdb  mov     dil, bl
0x1813f0cde  mov     sil, bl
0x1813f0ce1  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x1813f0ce6  call    cs:__imp_RegCloseKey
0x1813f0cec  mov     rcx, rbx
0x1813f0cef  mov     [rsp+0E90h+var_E28], rbx
0x1813f0cf4  jmp     loc_1813F0FAF
0x1813f0cf9  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x1813f0cfe  test    rcx, rcx
0x1813f0d01  jz      short loc_1813F0D09
0x1813f0d03  call    cs:__imp_RegCloseKey
0x1813f0d09  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813f0d0e  test    rcx, rcx
0x1813f0d11  jz      short loc_1813F0D19
0x1813f0d13  call    cs:__imp_RegCloseKey
0x1813f0d19  test    r14, r14
0x1813f0d1c  jz      short loc_1813F0D29
0x1813f0d1e  mov     rcx, r14; void *
0x1813f0d21  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1813f0d26  mov     r14, rbx
0x1813f0d29  cmp     [rbp+0D90h+arg_20], ebx
0x1813f0d2f  jz      loc_1813F1343
0x1813f0d35  call    sub_1813F1E10
0x1813f0d3a  cmp     eax, 6
0x1813f0d3d  jz      loc_1813F1343
0x1813f0d43  mov     ebx, 80004004h
0x1813f0d48  mov     r8d, 1E113322h; int
0x1813f0d4e  mov     edx, ebx; struct Mso::Telemetry::Activity *
0x1813f0d50  lea     rcx, [rsp+0E90h+var_E18]; this
0x1813f0d55  call    ?SetActivityResultHr@Telemetry@Mso@@YAXAEAUActivity@12@JI@Z; Mso::Telemetry::SetActivityResultHr(Mso::Telemetry::Activity &,long,uint)
0x1813f0d5a  jmp     loc_1813F1490
0x1813f0d5f  mov     r12d, esi
0x1813f0d62  lea     rdx, [rbp+0D90h+Buffer]; lpBuffer
0x1813f0d69  mov     ecx, 104h; nBufferLength
0x1813f0d6e  call    cs:__imp_GetTempPathW
0x1813f0d74  test    eax, eax
0x1813f0d76  jz      loc_1813F138D
0x1813f0d7c  mov     r8d, 105h
0x1813f0d82  lea     rdx, [rbp+0D90h+Buffer]
0x1813f0d89  lea     rcx, aMsohdinhTmp; "msohdinh.tmp"
0x1813f0d90  call    cs:__imp_MsoWzAppend
0x1813f0d96  movups  xmm0, xmmword ptr cs:aMimeVersion10C; "MIME-Version: 1.0\r\nContent-Type: text"...
0x1813f0d9d  movups  xmmword ptr [rbp+0D90h+Source], xmm0
0x1813f0da1  movups  xmm1, xmmword ptr cs:aMimeVersion10C+10h; "0\r\nContent-Type: text/html\r\n\r\n"
0x1813f0da8  movups  [rbp+0D90h+var_DA0], xmm1
0x1813f0dac  movsd   xmm0, qword ptr cs:aMimeVersion10C+20h; " text/html\r\n\r\n"
0x1813f0db4  movsd   [rbp+0D90h+var_D90], xmm0
0x1813f0db9  mov     eax, dword ptr cs:aMimeVersion10C+28h; "ml\r\n\r\n"
0x1813f0dbf  mov     [rbp+0D90h+var_D88], eax
0x1813f0dc2  movzx   eax, word ptr cs:aMimeVersion10C+2Ch; "\r\n"
0x1813f0dc9  mov     [rbp+0D90h+var_D84], ax
0x1813f0dcd  mov     al, byte ptr cs:aMimeVersion10C+2Eh; ""
0x1813f0dd3  mov     [rbp+0D90h+var_D82], al
0x1813f0dd6  movups  xmm0, xmmword ptr cs:aHtmlHeadMetaNa; "<html>\r\n<head>\r\n<meta name=\"ProgId"...
0x1813f0ddd  movups  xmmword ptr [rbp+0D90h+var_D80], xmm0
0x1813f0de1  movups  xmm1, xmmword ptr cs:aHtmlHeadMetaNa+10h; "<meta name=\"ProgId\" content=\""
0x1813f0de8  movups  xmmword ptr [rbp+0D90h+var_D80+10h], xmm1
0x1813f0dec  movsd   xmm0, qword ptr cs:aHtmlHeadMetaNa+20h; "Id\" content=\""
0x1813f0df4  movsd   qword ptr [rbp+0D90h+var_D80+20h], xmm0
0x1813f0df9  mov     eax, dword ptr cs:aHtmlHeadMetaNa+28h; "ent=\""
0x1813f0dff  mov     dword ptr [rbp+0D90h+var_D80+28h], eax
0x1813f0e02  movzx   eax, word ptr cs:aHtmlHeadMetaNa+2Ch; "\""
0x1813f0e09  mov     word ptr [rbp+0D90h+var_D80+2Ch], ax
0x1813f0e0d  movups  xmm0, xmmword ptr cs:aHeadHtml; "\">\r\n</head>\r\n</html>"
0x1813f0e14  movups  xmmword ptr [rbp+0D90h+var_DC8], xmm0
0x1813f0e18  mov     eax, dword ptr cs:aHeadHtml+10h; "tml>"
0x1813f0e1e  mov     dword ptr [rbp+0D90h+var_DC8+10h], eax
0x1813f0e21  mov     al, byte ptr cs:aHeadHtml+14h; ""
0x1813f0e27  mov     [rbp+0D90h+var_DC8+14h], al
0x1813f0e2a  mov     rsi, rbx
0x1813f0e2d  mov     edi, ebx
0x1813f0e2f  lea     r15, ?rgwchAppName@@3QBQEB_WB; wchar_t const * const near * const rgwchAppName
0x1813f0e36  lea     rax, aMicrosoftPower; "Microsoft PowerPoint"
0x1813f0e3d  cmp     r15, rax
0x1813f0e40  jge     short loc_1813F0E68
0x1813f0e42  mov     rdx, [r15]; wchar_t *
0x1813f0e45  mov     rcx, [rbp+0D90h+var_DF0]; wchar_t *
0x1813f0e49  call    ?Equal@StringExact@Mso@@SA_NPEB_W0@Z; Mso::StringExact::Equal(wchar_t const *,wchar_t const *)
0x1813f0e4e  test    al, al
0x1813f0e50  jnz     short loc_1813F0E5A
0x1813f0e52  inc     edi
0x1813f0e54  add     r15, 8
0x1813f0e58  jmp     short loc_1813F0E36
0x1813f0e5a  movsxd  rax, edi
0x1813f0e5d  lea     rsi, ?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x1813f0e64  mov     rsi, [rsi+rax*8]
0x1813f0e68  cmp     edi, 6
0x1813f0e6b  jge     loc_1813F0F9F
0x1813f0e71  test    rsi, rsi
0x1813f0e74  jz      loc_1813F0F9F
0x1813f0e7a  test    r12d, r12d
0x1813f0e7d  jz      short loc_1813F0E8D
0x1813f0e7f  lea     eax, [rdi-3]
0x1813f0e82  cmp     eax, 2
0x1813f0e85  cmovbe  rsi, cs:?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x1813f0e8d  mov     [rsp+0E90h+Arguments], rbx
0x1813f0e92  mov     dword ptr [rsp+0E90h+lpcbData], 80h
0x1813f0e9a  mov     dword ptr [rsp+0E90h+lpData], 2
0x1813f0ea2  xor     r9d, r9d
0x1813f0ea5  xor     r8d, r8d
0x1813f0ea8  mov     edx, 40000000h
0x1813f0ead  lea     rcx, [rbp+0D90h+Buffer]
0x1813f0eb4  call    cs:__imp_MsoCreateFileW
  ... truncated ...
```
