# HrCreateNewFileAHL(HWND__ *,wchar_t const *,wchar_t const *,int const *,int,int *)

- ea: `0x181360300`
- end: `0x181360eb7`
- name: `?HrCreateNewFileAHL@@YAJPEAUHWND__@@PEB_W1PEBHHPEAH@Z`
- size: `2999`
- prototype: `int(HWND, const wchar_t *, const wchar_t *, const int *, int, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x181361230`
- `0x181368204`

## callees

- `0x180003890`
- `0x18001aeb0`
- `0x18001d310`
- `0x180029700`
- `0x18002ae88`
- `0x18003bb40`
- `0x18006f8d0`
- `0x180074b00`
- `0x180074d40`
- `0x18009b8b0`
- `0x1800b65ac`
- `0x1801290e8`
- `0x18018a108`
- `0x1802be9ac`
- `0x180485240`
- `0x180741f0c`
- `0x181360220`
- `0x181360300`
- `0x181361790`

## import_xrefs

- `KERNEL32!GetLastError` at `0x181360d1e`
- `KERNEL32!GetLastError` at `0x181360d2f`
- `KERNEL32!GetLastError` at `0x181360e24`
- `KERNEL32!GetLastError` at `0x181360e2e`
- `KERNEL32!GetLastError` at `0x181360d1e`
- `KERNEL32!GetLastError` at `0x181360d2f`
- `KERNEL32!GetLastError` at `0x181360e24`
- `KERNEL32!GetLastError` at `0x181360e2e`
- `KERNEL32!GetFileAttributesW` at `0x1813609cf`
- `KERNEL32!GetFileAttributesW` at `0x1813609cf`
- `KERNEL32!WriteFile` at `0x1813608d8`
- `KERNEL32!WriteFile` at `0x181360be9`
- `KERNEL32!WriteFile` at `0x1813608d8`
- `KERNEL32!WriteFile` at `0x181360be9`
- `KERNEL32!CloseHandle` at `0x1813608e1`
- `KERNEL32!CloseHandle` at `0x181360979`
- `KERNEL32!CloseHandle` at `0x181360bf2`
- `KERNEL32!CloseHandle` at `0x181360e6e`
- `KERNEL32!CloseHandle` at `0x1813608e1`
- `KERNEL32!CloseHandle` at `0x181360979`
- `KERNEL32!CloseHandle` at `0x181360bf2`
- `KERNEL32!CloseHandle` at `0x181360e6e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x181360a71`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x181360a71`
- `KERNEL32!GetTempPathW` at `0x1813606f3`
- `KERNEL32!GetTempPathW` at `0x1813606f3`
- `KERNEL32!FormatMessageW` at `0x181360c9b`
- `KERNEL32!FormatMessageW` at `0x181360c9b`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x181360d42`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x181360d42`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x181360d62`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x181360d62`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x181360d8f`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x181360d8f`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x181360dea`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x181360dea`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x181360dba`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x181360dba`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x181360e04`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x181360e04`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x181360d4d`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x181360d4d`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813603eb`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181360406`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181360421`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18136043c`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813603eb`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181360406`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x181360421`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18136043c`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e1a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e61`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e85`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e1a`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e61`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181360e85`
- `Mso20Win32Client!__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x181360608`
- `Mso20Win32Client!__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x181360608`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360881`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360894`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813608a8`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360881`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360894`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x1813608a8`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x181360cb0`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x181360cb0`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360839`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360963`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360bbe`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360cf2`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360839`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360963`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360bbe`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360cf2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813604a2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813604b9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360715`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360af1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b05`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b39`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b4d`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813604a2`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813604b9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360715`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360af1`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b05`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b39`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360b4d`
- `VCRUNTIME140!wcschr` at `0x18136099b`
- `VCRUNTIME140!wcschr` at `0x181360c59`
- `VCRUNTIME140!wcschr` at `0x18136099b`
- `VCRUNTIME140!wcschr` at `0x181360c59`
- `VCRUNTIME140!wcsrchr` at `0x181360399`
- `VCRUNTIME140!wcsrchr` at `0x181360399`
- `ole32!CoTaskMemFree` at `0x181360a14`
- `ole32!CoTaskMemFree` at `0x181360a4a`
- `ole32!CoTaskMemFree` at `0x181360a9f`
- `ole32!CoTaskMemFree` at `0x181360abf`
- `ole32!CoTaskMemFree` at `0x181360a14`
- `ole32!CoTaskMemFree` at `0x181360a4a`
- `ole32!CoTaskMemFree` at `0x181360a9f`
- `ole32!CoTaskMemFree` at `0x181360abf`
- `ADVAPI32!RegQueryValueExW` at `0x181360531`
- `ADVAPI32!RegQueryValueExW` at `0x18136056c`
- `ADVAPI32!RegQueryValueExW` at `0x1813605b1`
- `ADVAPI32!RegQueryValueExW` at `0x181360531`
- `ADVAPI32!RegQueryValueExW` at `0x18136056c`
- `ADVAPI32!RegQueryValueExW` at `0x1813605b1`
- `ADVAPI32!RegCloseKey` at `0x181360653`
- `ADVAPI32!RegCloseKey` at `0x18136066b`
- `ADVAPI32!RegCloseKey` at `0x181360688`
- `ADVAPI32!RegCloseKey` at `0x181360698`
- `ADVAPI32!RegCloseKey` at `0x181360653`
- `ADVAPI32!RegCloseKey` at `0x18136066b`
- `ADVAPI32!RegCloseKey` at `0x181360688`
- `ADVAPI32!RegCloseKey` at `0x181360698`
- `ADVAPI32!RegQueryValueW` at `0x181360482`
- `ADVAPI32!RegQueryValueW` at `0x181360482`
- `ADVAPI32!RegQueryValueExA` at `0x1813605f3`
- `ADVAPI32!RegQueryValueExA` at `0x18136063d`
- `ADVAPI32!RegQueryValueExA` at `0x1813605f3`
- `ADVAPI32!RegQueryValueExA` at `0x18136063d`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813609fb`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360a31`
- `SHELL32!SHGetSpecialFolderLocation` at `0x1813609fb`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360a31`
- `SHELL32!SHGetPathFromIDListEx` at `0x181360a94`
- `SHELL32!SHGetPathFromIDListEx` at `0x181360ab4`
- `SHELL32!SHGetPathFromIDListEx` at `0x181360a94`
- `SHELL32!SHGetPathFromIDListEx` at `0x181360ab4`

## string_xrefs

- `0x181360364`: `HrCreateNewFileAHL`
- `0x1813605a5`: `Command`

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
  HKEY v17; // rcx
  unsigned int v18; // r9d
  const char *const near *v19; // rsi
  int v20; // edi
  const wchar_t **i; // r15
  void *v22; // r14
  __int64 v23; // rdi
  void *v24; // rax
  unsigned int v25; // esi
  __int64 v26; // rax
  __int64 v27; // rax
  void *v28; // rax
  void *v29; // rsi
  int v30; // esi
  va_list v31; // rdi
  wchar_t *v32; // rax
  void *FileW; // rax
  HINSTANCE v34; // rax
  __int64 ResourceString; // rax
  int v36; // edx
  int v37; // edx
  Mso::Alerts *v38; // rcx
  const struct MsoReserveTag *TelemetryNamespace; // rax
  const struct Mso::Alerts::AlertParam *v40; // r9
  unsigned int v42; // r9d
  signed int LastError; // eax
  unsigned int v44; // edi
  char v45; // [rsp+42h] [rbp-BEh]
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-A8h] BYREF
  const char *v50; // [rsp+60h] [rbp-A0h] BYREF
  HKEY v51; // [rsp+68h] [rbp-98h] BYREF
  HWND v52; // [rsp+70h] [rbp-90h]
  _BYTE v53[16]; // [rsp+78h] [rbp-88h] BYREF
  LONG cbData; // [rsp+88h] [rbp-78h] BYREF
  DWORD lpcbData; // [rsp+8Ch] [rbp-74h] BYREF
  DWORD v56; // [rsp+90h] [rbp-70h] BYREF
  int *v57; // [rsp+98h] [rbp-68h]
  wchar_t *v58; // [rsp+A0h] [rbp-60h]
  va_list Arguments[4]; // [rsp+A8h] [rbp-58h] BYREF
  char v60[24]; // [rsp+C8h] [rbp-38h] BYREF
  char Source[48]; // [rsp+E0h] [rbp-20h] BYREF
  _WORD v62[24]; // [rsp+110h] [rbp+10h] BYREF
  struct _SHELLEXECUTEINFOW Dst; // [rsp+140h] [rbp+40h] BYREF
  char v64; // [rsp+1B8h] [rbp+B8h]
  char v65[160]; // [rsp+350h] [rbp+250h] BYREF
  wchar_t lpData[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR Data[272]; // [rsp+600h] [rbp+500h] BYREF
  WCHAR Destination[264]; // [rsp+820h] [rbp+720h] BYREF
  WCHAR Buffer[264]; // [rsp+A30h] [rbp+930h] BYREF
  wchar_t v70[264]; // [rsp+C40h] [rbp+B40h] BYREF

  v6 = a4;
  ppidl = a4;
  v58 = a3;
  v7 = a2;
  v52 = a1;
  v57 = a6;
  LOBYTE(a2) = 2;
  v8 = Mso::Telemetry::EventFlags::EventFlags(Arguments, a2, 2);
  v50 = "HrCreateNewFileAHL";
  v9 = Office::FileIO::MSO::EventName(v60, &v50);
  LOBYTE(v10) = 2;
  Mso::Telemetry::Activity::Activity(v53, v9, v10, v8);
  v11 = wcsrchr(v7, 0x2Eu);
  v12 = 0;
  v51 = 0;
  hKey = 0;
  v45 = 0;
  LODWORD(v50) = 0;
  v13 = 0;
  v14 = 0;
  Type = 0;
  lpcbData = 520;
  v56 = 520;
  NumberOfBytesWritten = 0;
  cbData = 520;
  if ( !v11 )
  {
LABEL_34:
    if ( a5 && (unsigned int)sub_181361790() != 6 )
    {
      v12 = -2147467260;
      Mso::Telemetry::SetActivityResultHr(
        (Mso::Telemetry *)v53,
        (struct Mso::Telemetry::Activity *)0x80004004LL,
        504443682,
        v18);
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
      if ( (unsigned int)MsoRegOpenKeyExW(HKEY_CLASSES_ROOT, v11, 0x20019u, &v51) )
      {
        v17 = v51;
LABEL_28:
        if ( v17 )
          RegCloseKey(v17);
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
            (unsigned int)MsoRegOpenKeyExW(v51, Data, 0x20019u, &hKey)) )
      {
        MsoWzCopy(L"ShellNew", Data, 270);
      }
      if ( (unsigned int)MsoRegOpenKeyExW(v51, Data, 0x20019u, &hKey) )
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
          RegCloseKey(v51);
          v17 = 0;
          v51 = 0;
          goto LABEL_57;
        }
        if ( RegQueryValueExW(hKey, L"Command", 0, &Type, (LPBYTE)v70, &v56) || Type - 1 > 1 )
        {
          if ( !RegQueryValueExA(hKey, "Data", 0, &Type, 0, &NumberOfBytesWritten) )
          {
            v14 = operator new[](
                    NumberOfBytesWritten,
                    (const struct Mso::Memory::NoThrow::MarkingLeak_t *)&Mso::Memory::NoThrow::MarkingLeak);
            if ( !v14 )
              goto LABEL_109;
            RegQueryValueExA(hKey, "Data", 0, &Type, (LPBYTE)v14, &NumberOfBytesWritten);
            v45 = 1;
          }
        }
        else
        {
          LODWORD(v50) = 1;
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
  strcpy((char *)v62, "<html>\r\n<head>\r\n<meta name=\"ProgId\" content=\"");
  strcpy(v60, "\">\r\n</head>\r\n</html>");
  v19 = 0;
  v20 = 0;
  for ( i = (const wchar_t **)&rgwchAppName; (__int64)i < (__int64)L"Microsoft PowerPoint"; ++i )
  {
    if ( Mso::StringExact::Equal(v58, *i) )
    {
      v19 = (&rgchHtmlProgId)[v20];
      break;
    }
    ++v20;
  }
  if ( v20 < 6 && v19 )
  {
    if ( v13 && (unsigned int)(v20 - 3) <= 2 )
      v19 = rgchHtmlProgId;
    v22 = (void *)MsoCreateFileW(Buffer, 0x40000000, 0, 0, 2, 128, 0);
    v23 = -1;
    if ( v22 == (void *)-1LL )
      goto LABEL_104;
    v65[0] = 0;
    if ( v13 )
      MsoSzCopy(Source, v65, 149);
    MsoSzAppend(v62, v65, 149);
    MsoSzAppend(v19, v65, 149);
    MsoSzAppend(v60, v65, 149);
    do
      ++v23;
    while ( v65[v23] );
    NumberOfBytesWritten = v23;
    WriteFile(v22, v65, v23, &NumberOfBytesWritten, 0);
    CloseHandle(v22);
    if ( !(unsigned int)sub_181360220(Buffer, v7, a5, *(unsigned int *)&ppidl->mkid.cb) )
      goto LABEL_104;
    *v57 = 0;
    Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v53, 1);
LABEL_108:
    Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v53);
    return v12;
  }
  v17 = v51;
  v6 = ppidl;
  v15 = 0;
  v16 = 0;
LABEL_57:
  if ( v15 )
  {
    v24 = (void *)MsoCreateFileW(v7, 0x40000000, 0, 0, (unsigned int)(*(_DWORD *)&v6->mkid.cb != 0) + 1, 128, 0);
    if ( v24 != (void *)-1LL )
    {
      CloseHandle(v24);
      goto LABEL_95;
    }
    goto LABEL_102;
  }
  if ( !v16 )
  {
    if ( v45 )
    {
      v28 = (void *)MsoCreateFileW(v7, 0x40000000, 0, 0, (unsigned int)(*(_DWORD *)&v6->mkid.cb != 0) + 1, 128, 0);
      v29 = v28;
      if ( v28 != (void *)-1LL )
      {
        WriteFile(v28, v14, NumberOfBytesWritten, &NumberOfBytesWritten, 0);
        CloseHandle(v29);
        operator delete(v14);
        goto LABEL_95;
      }
      goto LABEL_102;
    }
    v30 = (int)v50;
    if ( (_DWORD)v50 )
    {
      memset_0(&Dst, 0, sizeof(Dst));
      wcscpy((wchar_t *)&Dst, L"p");
      Dst.fMask = 512;
      v31 = (va_list)v52;
      Dst.hwnd = v52;
      Dst.nShow = 10;
      Dst.lpFile = v70;
      v32 = wcschr(v70, 0x20u);
      if ( v32 )
      {
        *v32 = 0;
        Arguments[0] = v31;
        Arguments[1] = (va_list)v7;
        FormatMessageW(0x2400u, v32 + 1, 0, 0, Destination, 0x104u, Arguments);
        v32 = Destination;
      }
      Dst.lpParameters = v32;
      MsoShellExecuteExW(&Dst);
      if ( Dst.hInstApp <= HINSTANCE_ERROR )
        goto LABEL_102;
LABEL_100:
      *v57 = v30;
LABEL_115:
      Mso::Telemetry::Activity::SetSuccess((Mso::Telemetry::Activity *)v53, 1);
      Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v53);
      return 0;
    }
    goto LABEL_28;
  }
  v25 = 0;
  if ( wcschr(lpData, 0x5Cu) )
    goto LABEL_63;
  MsoWzCopy(lpData, Destination, 260);
  do
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( v25 < 2 )
        {
          ppidl = 0;
          if ( SHGetSpecialFolderLocation(0, v25 != 0 ? 45 : 21, &ppidl) >= 0 && ppidl )
          {
            SHGetPathFromIDListEx(ppidl, (PWSTR)&Dst, 0x104u, 2);
            CoTaskMemFree(ppidl);
            goto LABEL_85;
          }
          if ( ppidl )
            CoTaskMemFree(ppidl);
          ++v25;
        }
        if ( v25 != 2 )
          break;
        ppidl = 0;
        if ( SHGetSpecialFolderLocation(0, 36, &ppidl) >= 0 && ppidl )
        {
          SHGetPathFromIDListEx(ppidl, (PWSTR)&Dst, 0x104u, 2);
          CoTaskMemFree(ppidl);
          v26 = -1;
          do
            ++v26;
          while ( *((_WORD *)&Dst.cbSize + v26) );
          if ( v62[(int)v26 + 23] != 92 )
            MsoWzAppend(L"\\", &Dst, 260);
          MsoWzAppend(L"ShellNew\\", &Dst, 260);
          goto LABEL_85;
        }
        if ( ppidl )
          CoTaskMemFree(ppidl);
        v25 = 3;
      }
      if ( v25 != 3 )
        goto LABEL_102;
      if ( ExpandEnvironmentStringsW(L"%windir%\\ShellNew\\", (LPWSTR)&Dst, 0x103u) )
        break;
      v25 = 4;
    }
LABEL_85:
    ++v25;
    v27 = -1;
    do
      ++v27;
    while ( *((_WORD *)&Dst.cbSize + v27) );
    if ( v62[(int)v27 + 23] != 92 )
      MsoWzAppend(L"\\", &Dst, 260);
    MsoWzAppend(Destination, &Dst, 260);
    MsoWzCopy((const wchar_t *)&Dst, lpData, 260);
LABEL_63:
    ;
  }
  while ( GetFileAttributesW(lpData) == -1 );
  if ( (unsigned int)sub_181360220(lpData, v7, a5, *(unsigned int *)&v6->mkid.cb) )
  {
LABEL_95:
    v30 = (int)v50;
    goto LABEL_100;
  }
LABEL_102:
  if ( v14 )
    operator delete(v14);
LABEL_104:
  if ( a5 && GetLastError() != 183 && GetLastError() != 80 )
  {
    Mso::Alerts::CreateDefaultAlertParam(&Dst);
    v34 = MsoLocLibraryFromAlias(0xF902F7ED);
    ResourceString = Mso::Strings::LoadResourceString(Arguments, v34, 327726);
    std::wstring::operator=(&Dst.lpParameters, ResourceString);
    std::basic_string<char16_t>::~basic_string<char16_t>(Arguments);
    std::wstring::operator=(&Dst.lpIDList, &Dst.lpParameters);
    LODWORD(Dst.hIcon) = Mso::Alerts::GetAlertIdFromMsoIds((Mso::Alerts *)0x5002E, v36);
    BYTE4(Dst.hMonitor) = 1;
    *(_WORD *)((char *)&Dst.hMonitor + 5) = *(_WORD *)((char *)&v52 + 5);
    HIBYTE(Dst.hMonitor) = HIBYTE(v52);
    LODWORD(Dst.hProcess) = Mso::Alerts::GetWatsonAlertIdFromMsoIds((Mso::Alerts *)0x5002E, v37);
    BYTE4(Dst.hProcess) = 1;
    *(_WORD *)((char *)&Dst.hProcess + 5) = *(_WORD *)((char *)&v52 + 5);
    HIBYTE(Dst.hProcess) = HIBYTE(v52);
    v64 = 1;
    TelemetryNamespace = Mso::Alerts::GetTelemetryNamespace(v38);
    LODWORD(v50) = 504443681;
    v12 = Mso::Alerts::ShowAlert(
            (Mso::Alerts *)&v50,
            TelemetryNamespace,
            (const struct Mso::Telemetry::TelemetryNamespace *)&Dst,
            v40);
    std::pair<std::wstring const,Mso::History::FileInfo>::~pair<std::wstring const,Mso::History::FileInfo>(&Dst);
    goto LABEL_108;
  }
LABEL_109:
  if ( GetLastError() )
  {
    LastError = GetLastError();
    v44 = LastError;
    if ( LastError > 0 )
      v44 = (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    v44 = -2147467259;
  }
  Mso::Telemetry::SetActivityResultHr((Mso::Telemetry *)v53, (struct Mso::Telemetry::Activity *)v44, 504443680, v42);
  Mso::Telemetry::Activity::~Activity((Mso::Telemetry::Activity *)v53);
  return v44;
}

```

## disassembly

```asm
0x181360300  mov     [rsp-8+arg_18], rbx
0x181360305  push    rbp
0x181360306  push    rsi
0x181360307  push    rdi
0x181360308  push    r12
0x18136030a  push    r13
0x18136030c  push    r14
0x18136030e  push    r15
0x181360310  lea     rbp, [rsp-0D60h]
0x181360318  sub     rsp, 0E60h
0x18136031f  mov     rax, cs:__security_cookie
0x181360326  xor     rax, rsp
0x181360329  mov     [rbp+0D90h+var_40], rax
0x181360330  mov     r15, r9
0x181360333  mov     [rsp+0E90h+ppidl], r9
0x181360338  mov     [rbp+0D90h+var_DF0], r8
0x18136033c  mov     r13, rdx
0x18136033f  mov     [rsp+0E90h+var_E20], rcx
0x181360344  mov     rax, [rbp+0D90h+arg_28]
0x18136034b  mov     [rbp+0D90h+var_DF8], rax
0x18136034f  mov     r8d, 2
0x181360355  mov     dl, r8b
0x181360358  lea     rcx, [rbp+0D90h+var_DE8]
0x18136035c  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories)
0x181360361  mov     rbx, rax
0x181360364  lea     rax, aHrcreatenewfil; "HrCreateNewFileAHL"
0x18136036b  mov     [rsp+0E90h+var_E30], rax
0x181360370  lea     rdx, [rsp+0E90h+var_E30]
0x181360375  lea     rcx, [rbp+0D90h+var_DC8]
0x181360379  call    ?EventName@MSO@FileIO@Office@@YA?AU0Telemetry@Mso@@AEBUValidEventName@45@@Z; Office::FileIO::MSO::EventName(Mso::Telemetry::ValidEventName const &)
0x18136037e  mov     r9, rbx
0x181360381  mov     r8b, 2
0x181360384  mov     rdx, rax
0x181360387  lea     rcx, [rsp+0E90h+var_E18]
0x18136038c  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@W4ActivityAggregationMode@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::ActivityAggregationMode,Mso::Telemetry::EventFlags const &)
0x181360391  mov     edx, 2Eh ; '.'; Ch
0x181360396  mov     rcx, r13; Str
0x181360399  call    cs:__imp_wcsrchr
0x18136039f  mov     rdi, rax
0x1813603a2  xor     ebx, ebx
0x1813603a4  mov     [rsp+0E90h+var_E28], rbx
0x1813603a9  mov     [rsp+0E90h+hKey], rbx
0x1813603ae  mov     [rsp+0E90h+var_E4E], bl
0x1813603b2  mov     dword ptr [rsp+0E90h+var_E30], ebx
0x1813603b6  mov     r12d, ebx
0x1813603b9  mov     r14d, ebx
0x1813603bc  mov     [rsp+0E90h+Type], ebx
0x1813603c0  mov     eax, 208h
0x1813603c5  mov     [rbp+0D90h+var_E04], eax
0x1813603c8  mov     [rbp+0D90h+var_E00], eax
0x1813603cb  mov     [rsp+0E90h+NumberOfBytesWritten], ebx
0x1813603cf  mov     [rbp+0D90h+cbData], eax
0x1813603d2  lea     esi, [rbx+1]
0x1813603d5  test    rdi, rdi
0x1813603d8  jz      loc_1813606AE
0x1813603de  mov     r8d, esi
0x1813603e1  lea     rdx, ?vcwzHtmExt@@3QB_WB; ".htm"
0x1813603e8  mov     rcx, rdi
0x1813603eb  call    cs:__imp_MsoFWzEqual
0x1813603f1  test    eax, eax
0x1813603f3  jnz     loc_1813606E7
0x1813603f9  mov     r8d, esi
0x1813603fc  lea     rdx, ?vcwzHtmlExt@@3QB_WB; ".html"
0x181360403  mov     rcx, rdi
0x181360406  call    cs:__imp_MsoFWzEqual
0x18136040c  test    eax, eax
0x18136040e  jnz     loc_1813606E7
0x181360414  mov     r8d, esi
0x181360417  lea     rdx, ?vcwzMhtExt@@3QB_WB; ".mht"
0x18136041e  mov     rcx, rdi
0x181360421  call    cs:__imp_MsoFWzEqual
0x181360427  test    eax, eax
0x181360429  jnz     loc_1813606E4
0x18136042f  mov     r8d, esi
0x181360432  lea     rdx, ?vcwzMhtmlExt@@3QB_WB; ".mhtml"
0x181360439  mov     rcx, rdi
0x18136043c  call    cs:__imp_MsoFWzEqual
0x181360442  test    eax, eax
0x181360444  jnz     loc_1813606E4
0x18136044a  lea     r9, [rsp+0E90h+var_E28]; HKEY *
0x18136044f  mov     esi, 20019h
0x181360454  mov     r8d, esi; unsigned int
0x181360457  mov     rdx, rdi; lpSubKey
0x18136045a  mov     r12, 0FFFFFFFF80000000h
0x181360461  mov     rcx, r12; hKey
0x181360464  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x181360469  test    eax, eax
0x18136046b  jnz     loc_18136067E
0x181360471  lea     r9, [rbp+0D90h+cbData]; lpcbData
0x181360475  lea     r8, [rbp+0D90h+Data]; lpData
0x18136047c  mov     rdx, rdi; lpSubKey
0x18136047f  mov     rcx, r12; hKey
0x181360482  call    cs:__imp_RegQueryValueW
0x181360488  mov     edi, 10Eh
0x18136048d  test    eax, eax
0x18136048f  jnz     short loc_1813604DC
0x181360491  mov     r8d, edi
0x181360494  lea     rdx, [rbp+0D90h+Data]
0x18136049b  lea     rcx, SubBlock; "\\"
0x1813604a2  call    cs:__imp_MsoWzAppend
0x1813604a8  mov     r8d, edi
0x1813604ab  lea     rdx, [rbp+0D90h+Data]
0x1813604b2  lea     rcx, aShellnew_0; "ShellNew"
0x1813604b9  call    cs:__imp_MsoWzAppend
0x1813604bf  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x1813604c4  mov     r8d, esi; unsigned int
0x1813604c7  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x1813604ce  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x1813604d3  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x1813604d8  test    eax, eax
0x1813604da  jz      short loc_1813604F2
0x1813604dc  mov     r8d, edi; int
0x1813604df  lea     rdx, [rbp+0D90h+Data]; Destination
0x1813604e6  lea     rcx, aShellnew_0; "ShellNew"
0x1813604ed  call    ?MsoWzCopy@@YAPEA_WPEB_WPEA_WH@Z; MsoWzCopy(wchar_t const *,wchar_t *,int)
0x1813604f2  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x1813604f7  mov     r8d, esi; unsigned int
0x1813604fa  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x181360501  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360506  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x18136050b  test    eax, eax
0x18136050d  jnz     loc_181360660
0x181360513  mov     [rsp+0E90h+lpcbData], rbx; lpcbData
0x181360518  mov     [rsp+0E90h+lpData], rbx; lpData
0x18136051d  lea     r9, [rsp+0E90h+Type]; lpType
0x181360522  xor     r8d, r8d; lpReserved
0x181360525  lea     rdx, aNullfile; "NullFile"
0x18136052c  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360531  call    cs:__imp_RegQueryValueExW
0x181360537  test    eax, eax
0x181360539  jnz     short loc_181360543
0x18136053b  mov     dil, 1
0x18136053e  jmp     loc_18136064B
0x181360543  lea     rax, [rbp+0D90h+var_E04]
0x181360547  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x18136054c  lea     rax, [rbp+0D90h+var_AA0]
0x181360553  mov     [rsp+0E90h+lpData], rax; lpData
0x181360558  lea     r9, [rsp+0E90h+Type]; lpType
0x18136055d  xor     r8d, r8d; lpReserved
0x181360560  lea     rdx, aFilename_4; "FileName"
0x181360567  mov     rcx, [rsp+0E90h+hKey]; hKey
0x18136056c  call    cs:__imp_RegQueryValueExW
0x181360572  test    eax, eax
0x181360574  jnz     short loc_181360588
0x181360576  cmp     [rsp+0E90h+Type], 1
0x18136057b  jnz     short loc_181360588
0x18136057d  mov     sil, 1
0x181360580  mov     dil, bl
0x181360583  jmp     loc_18136064E
0x181360588  lea     rax, [rbp+0D90h+var_E00]
0x18136058c  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360591  lea     rax, [rbp+0D90h+var_250]
0x181360598  mov     [rsp+0E90h+lpData], rax; lpData
0x18136059d  lea     r9, [rsp+0E90h+Type]; lpType
0x1813605a2  xor     r8d, r8d; lpReserved
0x1813605a5  lea     rdx, aCommand_5; "Command"
0x1813605ac  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813605b1  call    cs:__imp_RegQueryValueExW
0x1813605b7  test    eax, eax
0x1813605b9  jnz     short loc_1813605D0
0x1813605bb  mov     eax, [rsp+0E90h+Type]
0x1813605bf  dec     eax
0x1813605c1  cmp     eax, 1
0x1813605c4  ja      short loc_1813605D0
0x1813605c6  mov     dword ptr [rsp+0E90h+var_E30], 1
0x1813605ce  jmp     short loc_181360648
0x1813605d0  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x1813605d5  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x1813605da  mov     [rsp+0E90h+lpData], rbx; lpData
0x1813605df  lea     r9, [rsp+0E90h+Type]; lpType
0x1813605e4  xor     r8d, r8d; lpReserved
0x1813605e7  lea     rdx, aData_6; "Data"
0x1813605ee  mov     rcx, [rsp+0E90h+hKey]; hKey
0x1813605f3  call    cs:__imp_RegQueryValueExA
0x1813605f9  test    eax, eax
0x1813605fb  jnz     short loc_181360648
0x1813605fd  mov     ecx, [rsp+0E90h+NumberOfBytesWritten]
0x181360601  lea     rdx, ?MarkingLeak@NoThrow@Memory@Mso@@3UMarkingLeak_t@123@B; Mso::Memory::NoThrow::MarkingLeak_t const Mso::Memory::NoThrow::MarkingLeak
0x181360608  call    cs:__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new[](unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x18136060e  mov     r14, rax
0x181360611  test    rax, rax
0x181360614  jz      loc_181360E24
0x18136061a  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x18136061f  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360624  mov     [rsp+0E90h+lpData], r14; lpData
0x181360629  lea     r9, [rsp+0E90h+Type]; lpType
0x18136062e  xor     r8d, r8d; lpReserved
0x181360631  lea     rdx, aData_6; "Data"
0x181360638  mov     rcx, [rsp+0E90h+hKey]; hKey
0x18136063d  call    cs:__imp_RegQueryValueExA
0x181360643  mov     [rsp+0E90h+var_E4E], 1
0x181360648  mov     dil, bl
0x18136064b  mov     sil, bl
0x18136064e  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360653  call    cs:__imp_RegCloseKey
0x181360659  mov     [rsp+0E90h+hKey], rbx
0x18136065e  jmp     short loc_181360666
0x181360660  mov     dil, bl
0x181360663  mov     sil, bl
0x181360666  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x18136066b  call    cs:__imp_RegCloseKey
0x181360671  mov     rcx, rbx
0x181360674  mov     [rsp+0E90h+var_E28], rbx
0x181360679  jmp     loc_181360934
0x18136067e  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360683  test    rcx, rcx
0x181360686  jz      short loc_18136068E
0x181360688  call    cs:__imp_RegCloseKey
0x18136068e  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360693  test    rcx, rcx
0x181360696  jz      short loc_18136069E
0x181360698  call    cs:__imp_RegCloseKey
0x18136069e  test    r14, r14
0x1813606a1  jz      short loc_1813606AE
0x1813606a3  mov     rcx, r14; void *
0x1813606a6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1813606ab  mov     r14, rbx
0x1813606ae  cmp     [rbp+0D90h+arg_20], ebx
0x1813606b4  jz      loc_181360CC8
0x1813606ba  call    sub_181361790
0x1813606bf  cmp     eax, 6
0x1813606c2  jz      loc_181360CC8
0x1813606c8  mov     ebx, 80004004h
0x1813606cd  mov     r8d, 1E113322h; int
0x1813606d3  mov     edx, ebx; struct Mso::Telemetry::Activity *
0x1813606d5  lea     rcx, [rsp+0E90h+var_E18]; this
0x1813606da  call    ?SetActivityResultHr@Telemetry@Mso@@YAXAEAUActivity@12@JI@Z; Mso::Telemetry::SetActivityResultHr(Mso::Telemetry::Activity &,long,uint)
0x1813606df  jmp     loc_181360E15
0x1813606e4  mov     r12d, esi
0x1813606e7  lea     rdx, [rbp+0D90h+Buffer]; lpBuffer
0x1813606ee  mov     ecx, 104h; nBufferLength
0x1813606f3  call    cs:__imp_GetTempPathW
0x1813606f9  test    eax, eax
0x1813606fb  jz      loc_181360D12
0x181360701  mov     r8d, 105h
0x181360707  lea     rdx, [rbp+0D90h+Buffer]
0x18136070e  lea     rcx, aMsohdinhTmp; "msohdinh.tmp"
0x181360715  call    cs:__imp_MsoWzAppend
0x18136071b  movups  xmm0, xmmword ptr cs:aMimeVersion10C; "MIME-Version: 1.0\r\nContent-Type: text"...
0x181360722  movups  xmmword ptr [rbp+0D90h+Source], xmm0
0x181360726  movups  xmm1, xmmword ptr cs:aMimeVersion10C+10h; "0\r\nContent-Type: text/html\r\n\r\n"
0x18136072d  movups  [rbp+0D90h+var_DA0], xmm1
0x181360731  movsd   xmm0, qword ptr cs:aMimeVersion10C+20h; " text/html\r\n\r\n"
0x181360739  movsd   [rbp+0D90h+var_D90], xmm0
0x18136073e  mov     eax, dword ptr cs:aMimeVersion10C+28h; "ml\r\n\r\n"
0x181360744  mov     [rbp+0D90h+var_D88], eax
0x181360747  movzx   eax, word ptr cs:aMimeVersion10C+2Ch; "\r\n"
0x18136074e  mov     [rbp+0D90h+var_D84], ax
0x181360752  mov     al, byte ptr cs:aMimeVersion10C+2Eh; ""
0x181360758  mov     [rbp+0D90h+var_D82], al
0x18136075b  movups  xmm0, xmmword ptr cs:aHtmlHeadMetaNa; "<html>\r\n<head>\r\n<meta name=\"ProgId"...
0x181360762  movups  xmmword ptr [rbp+0D90h+var_D80], xmm0
0x181360766  movups  xmm1, xmmword ptr cs:aHtmlHeadMetaNa+10h; "<meta name=\"ProgId\" content=\""
0x18136076d  movups  xmmword ptr [rbp+0D90h+var_D80+10h], xmm1
0x181360771  movsd   xmm0, qword ptr cs:aHtmlHeadMetaNa+20h; "Id\" content=\""
0x181360779  movsd   qword ptr [rbp+0D90h+var_D80+20h], xmm0
0x18136077e  mov     eax, dword ptr cs:aHtmlHeadMetaNa+28h; "ent=\""
0x181360784  mov     dword ptr [rbp+0D90h+var_D80+28h], eax
0x181360787  movzx   eax, word ptr cs:aHtmlHeadMetaNa+2Ch; "\""
0x18136078e  mov     word ptr [rbp+0D90h+var_D80+2Ch], ax
0x181360792  movups  xmm0, xmmword ptr cs:aHeadHtml; "\">\r\n</head>\r\n</html>"
0x181360799  movups  xmmword ptr [rbp+0D90h+var_DC8], xmm0
0x18136079d  mov     eax, dword ptr cs:aHeadHtml+10h; "tml>"
0x1813607a3  mov     dword ptr [rbp+0D90h+var_DC8+10h], eax
0x1813607a6  mov     al, byte ptr cs:aHeadHtml+14h; ""
0x1813607ac  mov     [rbp+0D90h+var_DC8+14h], al
0x1813607af  mov     rsi, rbx
0x1813607b2  mov     edi, ebx
0x1813607b4  lea     r15, ?rgwchAppName@@3QBQEB_WB; wchar_t const * const near * const rgwchAppName
0x1813607bb  lea     rax, aMicrosoftPower; "Microsoft PowerPoint"
0x1813607c2  cmp     r15, rax
0x1813607c5  jge     short loc_1813607ED
0x1813607c7  mov     rdx, [r15]; wchar_t *
0x1813607ca  mov     rcx, [rbp+0D90h+var_DF0]; wchar_t *
0x1813607ce  call    ?Equal@StringExact@Mso@@SA_NPEB_W0@Z; Mso::StringExact::Equal(wchar_t const *,wchar_t const *)
0x1813607d3  test    al, al
0x1813607d5  jnz     short loc_1813607DF
0x1813607d7  inc     edi
0x1813607d9  add     r15, 8
0x1813607dd  jmp     short loc_1813607BB
0x1813607df  movsxd  rax, edi
0x1813607e2  lea     rsi, ?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x1813607e9  mov     rsi, [rsi+rax*8]
0x1813607ed  cmp     edi, 6
0x1813607f0  jge     loc_181360924
0x1813607f6  test    rsi, rsi
0x1813607f9  jz      loc_181360924
0x1813607ff  test    r12d, r12d
0x181360802  jz      short loc_181360812
0x181360804  lea     eax, [rdi-3]
0x181360807  cmp     eax, 2
0x18136080a  cmovbe  rsi, cs:?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x181360812  mov     [rsp+0E90h+Arguments], rbx
0x181360817  mov     dword ptr [rsp+0E90h+lpcbData], 80h
0x18136081f  mov     dword ptr [rsp+0E90h+lpData], 2
0x181360827  xor     r9d, r9d
0x18136082a  xor     r8d, r8d
0x18136082d  mov     edx, 40000000h
0x181360832  lea     rcx, [rbp+0D90h+Buffer]
0x181360839  call    cs:__imp_MsoCreateFileW
  ... truncated ...
```
