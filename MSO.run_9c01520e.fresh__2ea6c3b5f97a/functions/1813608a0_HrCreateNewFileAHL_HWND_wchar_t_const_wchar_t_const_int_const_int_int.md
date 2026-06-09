# HrCreateNewFileAHL(HWND__ *,wchar_t const *,wchar_t const *,int const *,int,int *)

- ea: `0x1813608a0`
- end: `0x181361457`
- name: `?HrCreateNewFileAHL@@YAJPEAUHWND__@@PEB_W1PEBHHPEAH@Z`
- size: `2999`
- prototype: `int(HWND, const wchar_t *, const wchar_t *, const int *, int, int *)`
- caller_count: `2`
- callee_count: `19`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1813617d0`
- `0x1813687a4`

## callees

- `0x180003890`
- `0x18001aea0`
- `0x18001d310`
- `0x180029700`
- `0x18002ae88`
- `0x18003bb80`
- `0x18006fa70`
- `0x180073e90`
- `0x180074410`
- `0x1800b6ef4`
- `0x1800c1808`
- `0x18012dd10`
- `0x18016eca0`
- `0x180187168`
- `0x1802b1c04`
- `0x18074b31c`
- `0x1813607c0`
- `0x1813608a0`
- `0x181361d30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1813612be`
- `KERNEL32!GetLastError` at `0x1813612cf`
- `KERNEL32!GetLastError` at `0x1813613c4`
- `KERNEL32!GetLastError` at `0x1813613ce`
- `KERNEL32!GetLastError` at `0x1813612be`
- `KERNEL32!GetLastError` at `0x1813612cf`
- `KERNEL32!GetLastError` at `0x1813613c4`
- `KERNEL32!GetLastError` at `0x1813613ce`
- `KERNEL32!GetFileAttributesW` at `0x181360f6f`
- `KERNEL32!GetFileAttributesW` at `0x181360f6f`
- `KERNEL32!WriteFile` at `0x181360e78`
- `KERNEL32!WriteFile` at `0x181361189`
- `KERNEL32!WriteFile` at `0x181360e78`
- `KERNEL32!WriteFile` at `0x181361189`
- `KERNEL32!CloseHandle` at `0x181360e81`
- `KERNEL32!CloseHandle` at `0x181360f19`
- `KERNEL32!CloseHandle` at `0x181361192`
- `KERNEL32!CloseHandle` at `0x18136140e`
- `KERNEL32!CloseHandle` at `0x181360e81`
- `KERNEL32!CloseHandle` at `0x181360f19`
- `KERNEL32!CloseHandle` at `0x181361192`
- `KERNEL32!CloseHandle` at `0x18136140e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x181361011`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x181361011`
- `KERNEL32!GetTempPathW` at `0x181360c93`
- `KERNEL32!GetTempPathW` at `0x181360c93`
- `KERNEL32!FormatMessageW` at `0x18136123b`
- `KERNEL32!FormatMessageW` at `0x18136123b`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1813612e2`
- `Mso30Win32Client!__imp_?CreateDefaultAlertParam@Alerts@Mso@@YA?AUAlertParam@12@XZ` at `0x1813612e2`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x181361302`
- `Mso30Win32Client!__imp_?LoadResourceString@Strings@Mso@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEAUHINSTANCE__@@I@Z` at `0x181361302`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18136132f`
- `Mso30Win32Client!__imp_?GetAlertIdFromMsoIds@Alerts@Mso@@YAHH@Z` at `0x18136132f`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x18136138a`
- `Mso30Win32Client!__imp_?GetTelemetryNamespace@Alerts@Mso@@YAPEBUTelemetryNamespace@Telemetry@2@XZ` at `0x18136138a`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x18136135a`
- `Mso30Win32Client!__imp_?GetWatsonAlertIdFromMsoIds@Alerts@Mso@@YAIH@Z` at `0x18136135a`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1813613a4`
- `Mso30Win32Client!__imp_?ShowAlert@Alerts@Mso@@YAHAEBVMsoReserveTag@@PEBUTelemetryNamespace@Telemetry@2@AEBUAlertParam@12@@Z` at `0x1813613a4`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1813612ed`
- `Mso30Win32Client!__imp_?MsoLocLibraryFromAlias@@YAPEAUHINSTANCE__@@K@Z` at `0x1813612ed`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18136098b`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609a6`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609c1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609dc`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x18136098b`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609a6`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609c1`
- `Mso30Win32Client!__imp_MsoFWzEqual` at `0x1813609dc`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813613ba`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181361401`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181361425`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x1813613ba`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181361401`
- `Mso20Win32Client!__imp_??1Activity@Telemetry@Mso@@QEAA@XZ` at `0x181361425`
- `Mso20Win32Client!__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x181360ba8`
- `Mso20Win32Client!__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z` at `0x181360ba8`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e21`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e34`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e48`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e21`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e34`
- `Mso20Win32Client!__imp_MsoSzAppend` at `0x181360e48`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x181361250`
- `Mso20Win32Client!__imp_?MsoShellExecuteExW@@YAHPEAU_SHELLEXECUTEINFOW@@@Z` at `0x181361250`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360dd9`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360f03`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18136115e`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181361292`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360dd9`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181360f03`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x18136115e`
- `Mso20Win32Client!__imp_MsoCreateFileW` at `0x181361292`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360a42`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360a59`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360cb5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181361091`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610a5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610d9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610ed`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360a42`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360a59`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181360cb5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x181361091`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610a5`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610d9`
- `Mso20Win32Client!__imp_MsoWzAppend` at `0x1813610ed`
- `VCRUNTIME140!wcschr` at `0x181360f3b`
- `VCRUNTIME140!wcschr` at `0x1813611f9`
- `VCRUNTIME140!wcschr` at `0x181360f3b`
- `VCRUNTIME140!wcschr` at `0x1813611f9`
- `VCRUNTIME140!wcsrchr` at `0x181360939`
- `VCRUNTIME140!wcsrchr` at `0x181360939`
- `ole32!CoTaskMemFree` at `0x181360fb4`
- `ole32!CoTaskMemFree` at `0x181360fea`
- `ole32!CoTaskMemFree` at `0x18136103f`
- `ole32!CoTaskMemFree` at `0x18136105f`
- `ole32!CoTaskMemFree` at `0x181360fb4`
- `ole32!CoTaskMemFree` at `0x181360fea`
- `ole32!CoTaskMemFree` at `0x18136103f`
- `ole32!CoTaskMemFree` at `0x18136105f`
- `ADVAPI32!RegQueryValueExW` at `0x181360ad1`
- `ADVAPI32!RegQueryValueExW` at `0x181360b0c`
- `ADVAPI32!RegQueryValueExW` at `0x181360b51`
- `ADVAPI32!RegQueryValueExW` at `0x181360ad1`
- `ADVAPI32!RegQueryValueExW` at `0x181360b0c`
- `ADVAPI32!RegQueryValueExW` at `0x181360b51`
- `ADVAPI32!RegCloseKey` at `0x181360bf3`
- `ADVAPI32!RegCloseKey` at `0x181360c0b`
- `ADVAPI32!RegCloseKey` at `0x181360c28`
- `ADVAPI32!RegCloseKey` at `0x181360c38`
- `ADVAPI32!RegCloseKey` at `0x181360bf3`
- `ADVAPI32!RegCloseKey` at `0x181360c0b`
- `ADVAPI32!RegCloseKey` at `0x181360c28`
- `ADVAPI32!RegCloseKey` at `0x181360c38`
- `ADVAPI32!RegQueryValueW` at `0x181360a22`
- `ADVAPI32!RegQueryValueW` at `0x181360a22`
- `ADVAPI32!RegQueryValueExA` at `0x181360b93`
- `ADVAPI32!RegQueryValueExA` at `0x181360bdd`
- `ADVAPI32!RegQueryValueExA` at `0x181360b93`
- `ADVAPI32!RegQueryValueExA` at `0x181360bdd`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360f9b`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360fd1`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360f9b`
- `SHELL32!SHGetSpecialFolderLocation` at `0x181360fd1`
- `SHELL32!SHGetPathFromIDListEx` at `0x181361034`
- `SHELL32!SHGetPathFromIDListEx` at `0x181361054`
- `SHELL32!SHGetPathFromIDListEx` at `0x181361034`
- `SHELL32!SHGetPathFromIDListEx` at `0x181361054`

## string_xrefs

- `0x181360904`: `HrCreateNewFileAHL`
- `0x181360b45`: `Command`

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
    if ( a5 && (unsigned int)sub_181361D30() != 6 )
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
    if ( !(unsigned int)sub_1813607C0(Buffer, v7, a5, *(unsigned int *)&ppidl->mkid.cb) )
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
  if ( (unsigned int)sub_1813607C0(lpData, v7, a5, *(unsigned int *)&v6->mkid.cb) )
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
0x1813608a0  mov     [rsp-8+arg_18], rbx
0x1813608a5  push    rbp
0x1813608a6  push    rsi
0x1813608a7  push    rdi
0x1813608a8  push    r12
0x1813608aa  push    r13
0x1813608ac  push    r14
0x1813608ae  push    r15
0x1813608b0  lea     rbp, [rsp-0D60h]
0x1813608b8  sub     rsp, 0E60h
0x1813608bf  mov     rax, cs:__security_cookie
0x1813608c6  xor     rax, rsp
0x1813608c9  mov     [rbp+0D90h+var_40], rax
0x1813608d0  mov     r15, r9
0x1813608d3  mov     [rsp+0E90h+ppidl], r9
0x1813608d8  mov     [rbp+0D90h+var_DF0], r8
0x1813608dc  mov     r13, rdx
0x1813608df  mov     [rsp+0E90h+var_E20], rcx
0x1813608e4  mov     rax, [rbp+0D90h+arg_28]
0x1813608eb  mov     [rbp+0D90h+var_DF8], rax
0x1813608ef  mov     r8d, 2
0x1813608f5  mov     dl, r8b
0x1813608f8  lea     rcx, [rbp+0D90h+var_DE8]
0x1813608fc  call    ??0EventFlags@Telemetry@Mso@@QEAA@W4SamplingPolicy@12@W4DataCategories@12@@Z; Mso::Telemetry::EventFlags::EventFlags(Mso::Telemetry::SamplingPolicy,Mso::Telemetry::DataCategories)
0x181360901  mov     rbx, rax
0x181360904  lea     rax, aHrcreatenewfil; "HrCreateNewFileAHL"
0x18136090b  mov     [rsp+0E90h+var_E30], rax
0x181360910  lea     rdx, [rsp+0E90h+var_E30]
0x181360915  lea     rcx, [rbp+0D90h+var_DC8]
0x181360919  call    ?EventName@MSO@FileIO@Office@@YA?AU0Telemetry@Mso@@AEBUValidEventName@45@@Z; Office::FileIO::MSO::EventName(Mso::Telemetry::ValidEventName const &)
0x18136091e  mov     r9, rbx
0x181360921  mov     r8b, 2
0x181360924  mov     rdx, rax
0x181360927  lea     rcx, [rsp+0E90h+var_E18]
0x18136092c  call    ??0Activity@Telemetry@Mso@@QEAA@AEBUEventName@12@W4ActivityAggregationMode@12@AEBUEventFlags@12@@Z; Mso::Telemetry::Activity::Activity(Mso::Telemetry::EventName const &,Mso::Telemetry::ActivityAggregationMode,Mso::Telemetry::EventFlags const &)
0x181360931  mov     edx, 2Eh ; '.'; Ch
0x181360936  mov     rcx, r13; Str
0x181360939  call    cs:__imp_wcsrchr
0x18136093f  mov     rdi, rax
0x181360942  xor     ebx, ebx
0x181360944  mov     [rsp+0E90h+var_E28], rbx
0x181360949  mov     [rsp+0E90h+hKey], rbx
0x18136094e  mov     [rsp+0E90h+var_E4E], bl
0x181360952  mov     dword ptr [rsp+0E90h+var_E30], ebx
0x181360956  mov     r12d, ebx
0x181360959  mov     r14d, ebx
0x18136095c  mov     [rsp+0E90h+Type], ebx
0x181360960  mov     eax, 208h
0x181360965  mov     [rbp+0D90h+var_E04], eax
0x181360968  mov     [rbp+0D90h+var_E00], eax
0x18136096b  mov     [rsp+0E90h+NumberOfBytesWritten], ebx
0x18136096f  mov     [rbp+0D90h+cbData], eax
0x181360972  lea     esi, [rbx+1]
0x181360975  test    rdi, rdi
0x181360978  jz      loc_181360C4E
0x18136097e  mov     r8d, esi
0x181360981  lea     rdx, ?vcwzHtmExt@@3QB_WB; ".htm"
0x181360988  mov     rcx, rdi
0x18136098b  call    cs:__imp_MsoFWzEqual
0x181360991  test    eax, eax
0x181360993  jnz     loc_181360C87
0x181360999  mov     r8d, esi
0x18136099c  lea     rdx, ?vcwzHtmlExt@@3QB_WB; ".html"
0x1813609a3  mov     rcx, rdi
0x1813609a6  call    cs:__imp_MsoFWzEqual
0x1813609ac  test    eax, eax
0x1813609ae  jnz     loc_181360C87
0x1813609b4  mov     r8d, esi
0x1813609b7  lea     rdx, ?vcwzMhtExt@@3QB_WB; ".mht"
0x1813609be  mov     rcx, rdi
0x1813609c1  call    cs:__imp_MsoFWzEqual
0x1813609c7  test    eax, eax
0x1813609c9  jnz     loc_181360C84
0x1813609cf  mov     r8d, esi
0x1813609d2  lea     rdx, ?vcwzMhtmlExt@@3QB_WB; ".mhtml"
0x1813609d9  mov     rcx, rdi
0x1813609dc  call    cs:__imp_MsoFWzEqual
0x1813609e2  test    eax, eax
0x1813609e4  jnz     loc_181360C84
0x1813609ea  lea     r9, [rsp+0E90h+var_E28]; HKEY *
0x1813609ef  mov     esi, 20019h
0x1813609f4  mov     r8d, esi; unsigned int
0x1813609f7  mov     rdx, rdi; lpSubKey
0x1813609fa  mov     r12, 0FFFFFFFF80000000h
0x181360a01  mov     rcx, r12; hKey
0x181360a04  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x181360a09  test    eax, eax
0x181360a0b  jnz     loc_181360C1E
0x181360a11  lea     r9, [rbp+0D90h+cbData]; lpcbData
0x181360a15  lea     r8, [rbp+0D90h+Data]; lpData
0x181360a1c  mov     rdx, rdi; lpSubKey
0x181360a1f  mov     rcx, r12; hKey
0x181360a22  call    cs:__imp_RegQueryValueW
0x181360a28  mov     edi, 10Eh
0x181360a2d  test    eax, eax
0x181360a2f  jnz     short loc_181360A7C
0x181360a31  mov     r8d, edi
0x181360a34  lea     rdx, [rbp+0D90h+Data]
0x181360a3b  lea     rcx, SubBlock; "\\"
0x181360a42  call    cs:__imp_MsoWzAppend
0x181360a48  mov     r8d, edi
0x181360a4b  lea     rdx, [rbp+0D90h+Data]
0x181360a52  lea     rcx, aShellnew_0; "ShellNew"
0x181360a59  call    cs:__imp_MsoWzAppend
0x181360a5f  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x181360a64  mov     r8d, esi; unsigned int
0x181360a67  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x181360a6e  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360a73  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x181360a78  test    eax, eax
0x181360a7a  jz      short loc_181360A92
0x181360a7c  mov     r8d, edi; int
0x181360a7f  lea     rdx, [rbp+0D90h+Data]; Destination
0x181360a86  lea     rcx, aShellnew_0; "ShellNew"
0x181360a8d  call    ?MsoWzCopy@@YAPEA_WPEB_WPEA_WH@Z; MsoWzCopy(wchar_t const *,wchar_t *,int)
0x181360a92  lea     r9, [rsp+0E90h+hKey]; HKEY *
0x181360a97  mov     r8d, esi; unsigned int
0x181360a9a  lea     rdx, [rbp+0D90h+Data]; lpSubKey
0x181360aa1  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360aa6  call    ?MsoRegOpenKeyExW@@YAJPEAUHKEY__@@PEB_WKPEAPEAU1@@Z; MsoRegOpenKeyExW(HKEY__ *,wchar_t const *,ulong,HKEY__ * *)
0x181360aab  test    eax, eax
0x181360aad  jnz     loc_181360C00
0x181360ab3  mov     [rsp+0E90h+lpcbData], rbx; lpcbData
0x181360ab8  mov     [rsp+0E90h+lpData], rbx; lpData
0x181360abd  lea     r9, [rsp+0E90h+Type]; lpType
0x181360ac2  xor     r8d, r8d; lpReserved
0x181360ac5  lea     rdx, aNullfile; "NullFile"
0x181360acc  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360ad1  call    cs:__imp_RegQueryValueExW
0x181360ad7  test    eax, eax
0x181360ad9  jnz     short loc_181360AE3
0x181360adb  mov     dil, 1
0x181360ade  jmp     loc_181360BEB
0x181360ae3  lea     rax, [rbp+0D90h+var_E04]
0x181360ae7  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360aec  lea     rax, [rbp+0D90h+var_AA0]
0x181360af3  mov     [rsp+0E90h+lpData], rax; lpData
0x181360af8  lea     r9, [rsp+0E90h+Type]; lpType
0x181360afd  xor     r8d, r8d; lpReserved
0x181360b00  lea     rdx, aFilename_4; "FileName"
0x181360b07  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360b0c  call    cs:__imp_RegQueryValueExW
0x181360b12  test    eax, eax
0x181360b14  jnz     short loc_181360B28
0x181360b16  cmp     [rsp+0E90h+Type], 1
0x181360b1b  jnz     short loc_181360B28
0x181360b1d  mov     sil, 1
0x181360b20  mov     dil, bl
0x181360b23  jmp     loc_181360BEE
0x181360b28  lea     rax, [rbp+0D90h+var_E00]
0x181360b2c  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360b31  lea     rax, [rbp+0D90h+var_250]
0x181360b38  mov     [rsp+0E90h+lpData], rax; lpData
0x181360b3d  lea     r9, [rsp+0E90h+Type]; lpType
0x181360b42  xor     r8d, r8d; lpReserved
0x181360b45  lea     rdx, aCommand_5; "Command"
0x181360b4c  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360b51  call    cs:__imp_RegQueryValueExW
0x181360b57  test    eax, eax
0x181360b59  jnz     short loc_181360B70
0x181360b5b  mov     eax, [rsp+0E90h+Type]
0x181360b5f  dec     eax
0x181360b61  cmp     eax, 1
0x181360b64  ja      short loc_181360B70
0x181360b66  mov     dword ptr [rsp+0E90h+var_E30], 1
0x181360b6e  jmp     short loc_181360BE8
0x181360b70  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x181360b75  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360b7a  mov     [rsp+0E90h+lpData], rbx; lpData
0x181360b7f  lea     r9, [rsp+0E90h+Type]; lpType
0x181360b84  xor     r8d, r8d; lpReserved
0x181360b87  lea     rdx, aData_6; "Data"
0x181360b8e  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360b93  call    cs:__imp_RegQueryValueExA
0x181360b99  test    eax, eax
0x181360b9b  jnz     short loc_181360BE8
0x181360b9d  mov     ecx, [rsp+0E90h+NumberOfBytesWritten]
0x181360ba1  lea     rdx, ?MarkingLeak@NoThrow@Memory@Mso@@3UMarkingLeak_t@123@B; Mso::Memory::NoThrow::MarkingLeak_t const Mso::Memory::NoThrow::MarkingLeak
0x181360ba8  call    cs:__imp_??_U@YAPEAX_KAEBUMarkingLeak_t@NoThrow@Memory@Mso@@@Z; operator new[](unsigned __int64,Mso::Memory::NoThrow::MarkingLeak_t const &)
0x181360bae  mov     r14, rax
0x181360bb1  test    rax, rax
0x181360bb4  jz      loc_1813613C4
0x181360bba  lea     rax, [rsp+0E90h+NumberOfBytesWritten]
0x181360bbf  mov     [rsp+0E90h+lpcbData], rax; lpcbData
0x181360bc4  mov     [rsp+0E90h+lpData], r14; lpData
0x181360bc9  lea     r9, [rsp+0E90h+Type]; lpType
0x181360bce  xor     r8d, r8d; lpReserved
0x181360bd1  lea     rdx, aData_6; "Data"
0x181360bd8  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360bdd  call    cs:__imp_RegQueryValueExA
0x181360be3  mov     [rsp+0E90h+var_E4E], 1
0x181360be8  mov     dil, bl
0x181360beb  mov     sil, bl
0x181360bee  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360bf3  call    cs:__imp_RegCloseKey
0x181360bf9  mov     [rsp+0E90h+hKey], rbx
0x181360bfe  jmp     short loc_181360C06
0x181360c00  mov     dil, bl
0x181360c03  mov     sil, bl
0x181360c06  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360c0b  call    cs:__imp_RegCloseKey
0x181360c11  mov     rcx, rbx
0x181360c14  mov     [rsp+0E90h+var_E28], rbx
0x181360c19  jmp     loc_181360ED4
0x181360c1e  mov     rcx, [rsp+0E90h+var_E28]; hKey
0x181360c23  test    rcx, rcx
0x181360c26  jz      short loc_181360C2E
0x181360c28  call    cs:__imp_RegCloseKey
0x181360c2e  mov     rcx, [rsp+0E90h+hKey]; hKey
0x181360c33  test    rcx, rcx
0x181360c36  jz      short loc_181360C3E
0x181360c38  call    cs:__imp_RegCloseKey
0x181360c3e  test    r14, r14
0x181360c41  jz      short loc_181360C4E
0x181360c43  mov     rcx, r14; void *
0x181360c46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x181360c4b  mov     r14, rbx
0x181360c4e  cmp     [rbp+0D90h+arg_20], ebx
0x181360c54  jz      loc_181361268
0x181360c5a  call    sub_181361D30
0x181360c5f  cmp     eax, 6
0x181360c62  jz      loc_181361268
0x181360c68  mov     ebx, 80004004h
0x181360c6d  mov     r8d, 1E113322h; int
0x181360c73  mov     edx, ebx; struct Mso::Telemetry::Activity *
0x181360c75  lea     rcx, [rsp+0E90h+var_E18]; this
0x181360c7a  call    ?SetActivityResultHr@Telemetry@Mso@@YAXAEAUActivity@12@JI@Z; Mso::Telemetry::SetActivityResultHr(Mso::Telemetry::Activity &,long,uint)
0x181360c7f  jmp     loc_1813613B5
0x181360c84  mov     r12d, esi
0x181360c87  lea     rdx, [rbp+0D90h+Buffer]; lpBuffer
0x181360c8e  mov     ecx, 104h; nBufferLength
0x181360c93  call    cs:__imp_GetTempPathW
0x181360c99  test    eax, eax
0x181360c9b  jz      loc_1813612B2
0x181360ca1  mov     r8d, 105h
0x181360ca7  lea     rdx, [rbp+0D90h+Buffer]
0x181360cae  lea     rcx, aMsohdinhTmp; "msohdinh.tmp"
0x181360cb5  call    cs:__imp_MsoWzAppend
0x181360cbb  movups  xmm0, xmmword ptr cs:aMimeVersion10C; "MIME-Version: 1.0\r\nContent-Type: text"...
0x181360cc2  movups  xmmword ptr [rbp+0D90h+Source], xmm0
0x181360cc6  movups  xmm1, xmmword ptr cs:aMimeVersion10C+10h; "0\r\nContent-Type: text/html\r\n\r\n"
0x181360ccd  movups  [rbp+0D90h+var_DA0], xmm1
0x181360cd1  movsd   xmm0, qword ptr cs:aMimeVersion10C+20h; " text/html\r\n\r\n"
0x181360cd9  movsd   [rbp+0D90h+var_D90], xmm0
0x181360cde  mov     eax, dword ptr cs:aMimeVersion10C+28h; "ml\r\n\r\n"
0x181360ce4  mov     [rbp+0D90h+var_D88], eax
0x181360ce7  movzx   eax, word ptr cs:aMimeVersion10C+2Ch; "\r\n"
0x181360cee  mov     [rbp+0D90h+var_D84], ax
0x181360cf2  mov     al, byte ptr cs:aMimeVersion10C+2Eh; ""
0x181360cf8  mov     [rbp+0D90h+var_D82], al
0x181360cfb  movups  xmm0, xmmword ptr cs:aHtmlHeadMetaNa; "<html>\r\n<head>\r\n<meta name=\"ProgId"...
0x181360d02  movups  xmmword ptr [rbp+0D90h+var_D80], xmm0
0x181360d06  movups  xmm1, xmmword ptr cs:aHtmlHeadMetaNa+10h; "<meta name=\"ProgId\" content=\""
0x181360d0d  movups  xmmword ptr [rbp+0D90h+var_D80+10h], xmm1
0x181360d11  movsd   xmm0, qword ptr cs:aHtmlHeadMetaNa+20h; "Id\" content=\""
0x181360d19  movsd   qword ptr [rbp+0D90h+var_D80+20h], xmm0
0x181360d1e  mov     eax, dword ptr cs:aHtmlHeadMetaNa+28h; "ent=\""
0x181360d24  mov     dword ptr [rbp+0D90h+var_D80+28h], eax
0x181360d27  movzx   eax, word ptr cs:aHtmlHeadMetaNa+2Ch; "\""
0x181360d2e  mov     word ptr [rbp+0D90h+var_D80+2Ch], ax
0x181360d32  movups  xmm0, xmmword ptr cs:aHeadHtml; "\">\r\n</head>\r\n</html>"
0x181360d39  movups  xmmword ptr [rbp+0D90h+var_DC8], xmm0
0x181360d3d  mov     eax, dword ptr cs:aHeadHtml+10h; "tml>"
0x181360d43  mov     dword ptr [rbp+0D90h+var_DC8+10h], eax
0x181360d46  mov     al, byte ptr cs:aHeadHtml+14h; ""
0x181360d4c  mov     [rbp+0D90h+var_DC8+14h], al
0x181360d4f  mov     rsi, rbx
0x181360d52  mov     edi, ebx
0x181360d54  lea     r15, ?rgwchAppName@@3QBQEB_WB; wchar_t const * const near * const rgwchAppName
0x181360d5b  lea     rax, aMicrosoftPower; "Microsoft PowerPoint"
0x181360d62  cmp     r15, rax
0x181360d65  jge     short loc_181360D8D
0x181360d67  mov     rdx, [r15]; wchar_t *
0x181360d6a  mov     rcx, [rbp+0D90h+var_DF0]; wchar_t *
0x181360d6e  call    ?Equal@StringExact@Mso@@SA_NPEB_W0@Z; Mso::StringExact::Equal(wchar_t const *,wchar_t const *)
0x181360d73  test    al, al
0x181360d75  jnz     short loc_181360D7F
0x181360d77  inc     edi
0x181360d79  add     r15, 8
0x181360d7d  jmp     short loc_181360D5B
0x181360d7f  movsxd  rax, edi
0x181360d82  lea     rsi, ?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x181360d89  mov     rsi, [rsi+rax*8]
0x181360d8d  cmp     edi, 6
0x181360d90  jge     loc_181360EC4
0x181360d96  test    rsi, rsi
0x181360d99  jz      loc_181360EC4
0x181360d9f  test    r12d, r12d
0x181360da2  jz      short loc_181360DB2
0x181360da4  lea     eax, [rdi-3]
0x181360da7  cmp     eax, 2
0x181360daa  cmovbe  rsi, cs:?rgchHtmlProgId@@3QBQEBDB; char const * const near * const rgchHtmlProgId
0x181360db2  mov     [rsp+0E90h+Arguments], rbx
0x181360db7  mov     dword ptr [rsp+0E90h+lpcbData], 80h
0x181360dbf  mov     dword ptr [rsp+0E90h+lpData], 2
0x181360dc7  xor     r9d, r9d
0x181360dca  xor     r8d, r8d
0x181360dcd  mov     edx, 40000000h
0x181360dd2  lea     rcx, [rbp+0D90h+Buffer]
0x181360dd9  call    cs:__imp_MsoCreateFileW
  ... truncated ...
```
