# SaveRestoreInfo(ushort const *,ushort const *,ushort const *,ulong)

- ea: `0x18000e060`
- end: `0x18000ec92`
- name: `?SaveRestoreInfo@@YAJPEBG00K@Z`
- size: `3122`
- prototype: `__int64 __fastcall(const unsigned __int16 *, BYTE *lpAppName, PCWSTR SourceRootPath, char)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, installer_update, broker_com_uri`

## callers

- `0x180004880`

## callees

- `0x1800022bc`
- `0x180002c74`
- `0x18000521c`
- `0x180007454`
- `0x1800082f0`
- `0x180008c88`
- `0x180009110`
- `0x18000c574`
- `0x18000c760`
- `0x18000ced8`
- `0x18000d184`
- `0x18000d564`
- `0x18000d6cc`
- `0x18000d7ac`
- `0x18000e060`
- `0x18000ec98`
- `0x180012f48`
- `0x180017d98`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18000e25c`
- `KERNEL32!GetLastError` at `0x18000e25c`
- `KERNEL32!LocalFree` at `0x18000ec3d`
- `KERNEL32!LocalFree` at `0x18000ec3d`
- `KERNEL32!DeleteFileW` at `0x18000e59a`
- `KERNEL32!DeleteFileW` at `0x18000ea4b`
- `KERNEL32!DeleteFileW` at `0x18000ea9c`
- `KERNEL32!DeleteFileW` at `0x18000ead7`
- `KERNEL32!DeleteFileW` at `0x18000e59a`
- `KERNEL32!DeleteFileW` at `0x18000ea4b`
- `KERNEL32!DeleteFileW` at `0x18000ea9c`
- `KERNEL32!DeleteFileW` at `0x18000ead7`
- `KERNEL32!GetShortPathNameW` at `0x18000e4a0`
- `KERNEL32!GetShortPathNameW` at `0x18000e4a0`
- `KERNEL32!SetFileAttributesW` at `0x18000e590`
- `KERNEL32!SetFileAttributesW` at `0x18000ea41`
- `KERNEL32!SetFileAttributesW` at `0x18000ea92`
- `KERNEL32!SetFileAttributesW` at `0x18000eacd`
- `KERNEL32!SetFileAttributesW` at `0x18000e590`
- `KERNEL32!SetFileAttributesW` at `0x18000ea41`
- `KERNEL32!SetFileAttributesW` at `0x18000ea92`
- `KERNEL32!SetFileAttributesW` at `0x18000eacd`
- `ADVAPI32!RegUnLoadKeyW` at `0x18000e50e`
- `ADVAPI32!RegUnLoadKeyW` at `0x18000e71d`
- `ADVAPI32!RegUnLoadKeyW` at `0x18000e50e`
- `ADVAPI32!RegUnLoadKeyW` at `0x18000e71d`
- `ADVAPI32!RegLoadKeyW` at `0x18000e531`
- `ADVAPI32!RegLoadKeyW` at `0x18000e5ec`
- `ADVAPI32!RegLoadKeyW` at `0x18000e531`
- `ADVAPI32!RegLoadKeyW` at `0x18000e5ec`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e1e9`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e252`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e579`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e658`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e1e9`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e252`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e579`
- `ADVAPI32!RegCreateKeyExW` at `0x18000e658`
- `ADVAPI32!RegQueryValueExW` at `0x18000e2b3`
- `ADVAPI32!RegQueryValueExW` at `0x18000e2b3`
- `ADVAPI32!RegCloseKey` at `0x18000e5b9`
- `ADVAPI32!RegCloseKey` at `0x18000e704`
- `ADVAPI32!RegCloseKey` at `0x18000eb60`
- `ADVAPI32!RegCloseKey` at `0x18000eb70`
- `ADVAPI32!RegCloseKey` at `0x18000ebe2`
- `ADVAPI32!RegCloseKey` at `0x18000ec2b`
- `ADVAPI32!RegCloseKey` at `0x18000e5b9`
- `ADVAPI32!RegCloseKey` at `0x18000e704`
- `ADVAPI32!RegCloseKey` at `0x18000eb60`
- `ADVAPI32!RegCloseKey` at `0x18000eb70`
- `ADVAPI32!RegCloseKey` at `0x18000ebe2`
- `ADVAPI32!RegCloseKey` at `0x18000ec2b`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec0d`
- `ADVAPI32!RegOpenKeyExW` at `0x18000ec0d`
- `ADVAPI32!RegSetValueExW` at `0x18000e775`
- `ADVAPI32!RegSetValueExW` at `0x18000e7af`
- `ADVAPI32!RegSetValueExW` at `0x18000e8a7`
- `ADVAPI32!RegSetValueExW` at `0x18000e8d2`
- `ADVAPI32!RegSetValueExW` at `0x18000e914`
- `ADVAPI32!RegSetValueExW` at `0x18000e949`
- `ADVAPI32!RegSetValueExW` at `0x18000e97f`
- `ADVAPI32!RegSetValueExW` at `0x18000e9ba`
- `ADVAPI32!RegSetValueExW` at `0x18000ea25`
- `ADVAPI32!RegSetValueExW` at `0x18000eb12`
- `ADVAPI32!RegSetValueExW` at `0x18000eb3a`
- `ADVAPI32!RegSetValueExW` at `0x18000e775`
- `ADVAPI32!RegSetValueExW` at `0x18000e7af`
- `ADVAPI32!RegSetValueExW` at `0x18000e8a7`
- `ADVAPI32!RegSetValueExW` at `0x18000e8d2`
- `ADVAPI32!RegSetValueExW` at `0x18000e914`
- `ADVAPI32!RegSetValueExW` at `0x18000e949`
- `ADVAPI32!RegSetValueExW` at `0x18000e97f`
- `ADVAPI32!RegSetValueExW` at `0x18000e9ba`
- `ADVAPI32!RegSetValueExW` at `0x18000ea25`
- `ADVAPI32!RegSetValueExW` at `0x18000eb12`
- `ADVAPI32!RegSetValueExW` at `0x18000eb3a`
- `ADVAPI32!RegSaveKeyW` at `0x18000e5ac`
- `ADVAPI32!RegSaveKeyW` at `0x18000e5ac`
- `ADVAPI32!RegFlushKey` at `0x18000e6f9`
- `ADVAPI32!RegFlushKey` at `0x18000e6f9`
- `ADVAPI32!RegDeleteValueW` at `0x18000ea5d`
- `ADVAPI32!RegDeleteValueW` at `0x18000ea6f`
- `ADVAPI32!RegDeleteValueW` at `0x18000eb4c`
- `ADVAPI32!RegDeleteValueW` at `0x18000ea5d`
- `ADVAPI32!RegDeleteValueW` at `0x18000ea6f`
- `ADVAPI32!RegDeleteValueW` at `0x18000eb4c`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ebc5`
- `ADVAPI32!RegQueryInfoKeyW` at `0x18000ebc5`

## string_xrefs

- `0x18000e96d`: `InstallINFSection`
- `0x18000e0ed`: `ComponentName`
- `0x18000e119`: `CompName=%1 pszInf=%2 Sec=%3\n`
- `0x18000e28b`: `BackupPath`
- `0x18000e2da`: `BackupPath`
- `0x18000e8fb`: `BackupPath`
- `0x18000e31e`: `Uninstall Information`
- `0x18000e32a`: `Uninstall Information`
- `0x18000e937`: `InstallINFFile`
- `0x18000e9a3`: `BackupRegistry`
- `0x18000eb28`: `BackupRegistry`
- `0x18000e9c9`: `ComponentVersion`
- `0x18000ea0f`: `ComponentVersion`
- `0x18000eb45`: `ComponentVersion`
- `0x18000e75f`: `BackupRegPathName`
- `0x18000ea56`: `BackupRegPathName`

## pseudocode

```c
__int64 __fastcall SaveRestoreInfo(const unsigned __int16 *a1, BYTE *lpAppName, PCWSTR SourceRootPath, char a4)
{
  signed int v4; // ebx
  int v9; // r15d
  WCHAR *v10; // rdi
  const WCHAR *v11; // rdi
  signed int LastError; // eax
  __int64 v13; // r8
  WCHAR *v14; // rbx
  int v15; // esi
  const WCHAR *v16; // r8
  BYTE *v17; // r13
  __int64 v18; // r8
  int v19; // eax
  int v20; // r8d
  WCHAR *v21; // rbx
  LSTATUS v22; // ebx
  HKEY v23; // rcx
  int v24; // eax
  __int64 v25; // rdi
  int v26; // r8d
  __int64 v27; // rax
  const WCHAR *v28; // rsi
  __int64 v29; // rax
  unsigned __int16 *v30; // rsi
  int v31; // r11d
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rax
  const BYTE *v36; // rax
  ULONG dwFlags; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsa; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsb; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsc; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagsd; // [rsp+20h] [rbp-E0h]
  ULONG dwFlagse; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *samDesired; // [rsp+28h] [rbp-D8h]
  DWORD dwDisposition; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  DWORD cValues; // [rsp+70h] [rbp-90h] BYREF
  DWORD cSubKeys; // [rsp+74h] [rbp-8Ch] BYREF
  HKEY v49; // [rsp+78h] [rbp-88h] BYREF
  HKEY phkResult; // [rsp+80h] [rbp-80h] BYREF
  int v51; // [rsp+88h] [rbp-78h]
  unsigned __int16 v52[2]; // [rsp+8Ch] [rbp-74h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp-70h]
  unsigned int v54[10]; // [rsp+98h] [rbp-68h] BYREF
  WCHAR pszPathOut[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR Data[264]; // [rsp+2D0h] [rbp+1D0h] BYREF
  WCHAR pszMore[264]; // [rsp+4E0h] [rbp+3E0h] BYREF
  WCHAR v58[264]; // [rsp+6F0h] [rbp+5F0h] BYREF

  lpData = lpAppName;
  dwDisposition = 0;
  v4 = 0;
  hKey = 0;
  v49 = 0;
  phkResult = 0;
  cValues = 0;
  v9 = 1;
  if ( (unsigned int)NeedBackupData(a1, (LPCWSTR)lpAppName) )
  {
    AdvWriteToLog(L"SaveRestoreInfo: ");
    if ( (int)GetTranslatedString(a1, (LPCWSTR)lpAppName, L"ComponentName", pszMore, 0x104u, 0) >= 0 )
    {
      AdvWriteToLog(L"CompName=%1 pszInf=%2 Sec=%3\r\n", pszMore, a1, lpAppName);
      StringCchCopyW(pszPathOut, 0x104u, L"Software\\Microsoft\\Advanced INF Setup");
      v51 = a4 & 8;
      if ( (a4 & 8) != 0 )
      {
        CleanRegLogFile(L"RegSaveLogFile");
        CleanRegLogFile(L"RegRestoreLogFile");
      }
      v10 = pszMore;
      if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
      {
        do
          ++v10;
        while ( *v10 == 92 );
      }
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v10, dwFlags);
      if ( !RegCreateKeyExW(HKEY_LOCAL_MACHINE, pszPathOut, 0, 0, 0, 0x2001Fu, 0, &hKey, &dwDisposition) )
      {
        v11 = L"RegBackup";
        PathIsUnc2(L"RegBackup");
        PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, L"RegBackup", dwFlagsa);
        if ( RegCreateKeyExW(HKEY_CURRENT_USER, pszPathOut, 0, 0, 0, 0x2001Fu, 0, &phkResult, 0) )
          goto LABEL_11;
        dwDisposition = 520;
        Data[0] = 0;
        RegQueryValueExW(hKey, L"BackupPath", 0, 0, (LPBYTE)Data, &dwDisposition);
        if ( !Data[0]
          && ((int)GetTranslatedString(a1, (LPCWSTR)lpData, L"BackupPath", Data, 0x104u, (unsigned int *)v52) < 0
           || !IsFullPath(Data)) )
        {
          GetProgramFilesDir(Data, 0x104u);
          PathIsUnc2(L"Uninstall Information");
          PathCchCombineEx(Data, 0x104u, Data, L"Uninstall Information", dwFlagsb);
          CreateFullPath(Data, 1);
          v14 = pszMore;
          if ( !(unsigned int)PathIsUnc2(pszMore) && !IsExtendedLengthDosDevicePath(pszMore) && pszMore[0] == 92 )
          {
            do
              ++v14;
            while ( *v14 == 92 );
          }
          PathCchCombineEx(Data, 0x104u, Data, v14, dwFlagsc);
        }
        cSubKeys = a4 & 0x10;
        v15 = a4 & 0x40;
        *(_DWORD *)v52 = cSubKeys != 0;
        dwDisposition = *(_DWORD *)v52 | (v15 != 0 ? 272 : 16);
        GetUniBackupName(hKey, v58, v13, Data, pszMore);
        v16 = SourceRootPath;
        v17 = lpData;
        v4 = ProcessAllFiles(hWnd, (PCWSTR)lpData, v16, Data, v58, samDesired, dwDisposition);
        if ( v4 >= 0 )
        {
          if ( ctx )
            goto LABEL_34;
          v19 = dword_180025A10;
          if ( dword_180025A10 )
          {
LABEL_36:
            v11 = &word_180025A14;
LABEL_37:
            v23 = hKey;
            if ( v19 )
              v23 = HKEY_LOCAL_MACHINE;
            if ( RegCreateKeyExW(v23, v11, 0, 0, 0, 0x2001Fu, 0, &v49, 0) )
              goto LABEL_11;
            dwDisposition = *(_DWORD *)v52 | (v15 != 0 ? 0x100 : 0);
            if ( cSubKeys )
            {
              v4 = RegRestoreAllEx(v49);
              v24 = RegRestoreAllEx(phkResult);
              if ( v24 < 0 )
                v4 = v24;
            }
            else
            {
              v4 = ProcessAllRegSec(
                     hWnd,
                     0,
                     a1,
                     (const unsigned __int16 *)v17,
                     v49,
                     phkResult,
                     *(_DWORD *)v52 | (v15 != 0 ? 0x100 : 0),
                     (int *)&cValues);
            }
            v25 = -1;
            if ( !ctx && dword_180025A10 )
            {
              dword_180025A10 = 0;
              RegFlushKey(v49);
              RegCloseKey(v49);
              v49 = 0;
              RegUnLoadKeyW(HKEY_LOCAL_MACHINE, &word_180025A14);
              SetPathForRegHiveUse(Data, v54, v26, 0);
              if ( !v51 )
              {
                if ( v4 < 0 )
                  goto LABEL_79;
                SetFileAttributesW(pszPathOut, 0x80u);
                DeleteFileW(pszPathOut);
                RegDeleteValueW(hKey, L"BackupRegPathName");
                RegDeleteValueW(hKey, L"BackupRegSize");
                goto LABEL_52;
              }
              v27 = -1;
              do
                ++v27;
              while ( pszPathOut[v27] );
              RegSetValueExW(hKey, L"BackupRegPathName", 0, 1u, (const BYTE *)pszPathOut, 2 * v27 + 2);
              dwDisposition = MyFileSize(pszPathOut);
              RegSetValueExW(hKey, L"BackupRegSize", 0, 4u, (const BYTE *)&dwDisposition, 4u);
            }
            if ( v4 < 0 )
              goto LABEL_79;
LABEL_52:
            StringCchCopyW(pszPathOut, 0x104u, Data);
            v28 = v58;
            if ( !(unsigned int)PathIsUnc2(v58) && !IsExtendedLengthDosDevicePath(v58) && v58[0] == 92 )
            {
              do
                ++v28;
              while ( *v28 == 92 );
            }
            PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v28, dwFlagse);
            v29 = -1;
            do
              ++v29;
            while ( pszPathOut[v29] );
            v30 = &pszPathOut[v29];
            StringCchCopyW(v30, 260 - v29, L".DAT");
            if ( v51 == v31 )
            {
              if ( cSubKeys != v31 )
              {
                SetFileAttributesW(pszPathOut, 0x80u);
                DeleteFileW(pszPathOut);
                do
                  ++v25;
                while ( pszPathOut[v25] );
                StringCchCopyW(v30, 260 - v25, L".INI");
                SetFileAttributesW(pszPathOut, 0x80u);
                DeleteFileW(pszPathOut);
                MyRemoveDirectory(Data);
                dwDisposition = 0;
                RegSetValueExW(hKey, L"BackupFileSize", 0, 4u, (const BYTE *)&dwDisposition, 4u);
                RegSetValueExW(hKey, L"BackupRegistry", 0, 1u, L"n", 4u);
                RegDeleteValueW(hKey, L"ComponentVersion");
              }
            }
            else
            {
              dwDisposition = MyFileSize(pszPathOut);
              v32 = -1;
              do
                ++v32;
              while ( pszPathOut[v32] );
              RegSetValueExW(hKey, L"BackupFileName", 0, 1u, (const BYTE *)pszPathOut, 2 * v32 + 2);
              RegSetValueExW(hKey, L"BackupFileSize", 0, 4u, (const BYTE *)&dwDisposition, 4u);
              v33 = -1;
              do
                ++v33;
              while ( Data[v33] );
              RegSetValueExW(hKey, L"BackupPath", 0, 1u, (const BYTE *)Data, 2 * v33 + 2);
              v34 = -1;
              do
                ++v34;
              while ( a1[v34] );
              RegSetValueExW(hKey, L"InstallINFFile", 0, 1u, (const BYTE *)a1, 2 * v34 + 2);
              v35 = -1;
              do
                ++v35;
              while ( *(_WORD *)&v17[2 * v35] );
              RegSetValueExW(hKey, L"InstallINFSection", 0, 1u, v17, 2 * v35 + 2);
              v36 = (const BYTE *)L"y";
              if ( !cValues )
                v36 = L"n";
              RegSetValueExW(hKey, L"BackupRegistry", 0, 1u, v36, 4u);
              if ( (int)GetTranslatedString(a1, (LPCWSTR)v17, L"ComponentVersion", pszPathOut, 0x104u, 0) >= 0
                && pszPathOut[0] )
              {
                do
                  ++v25;
                while ( pszPathOut[v25] );
                RegSetValueExW(hKey, L"ComponentVersion", 0, 1u, (const BYTE *)pszPathOut, 2 * v25 + 2);
              }
            }
            goto LABEL_79;
          }
          GetUniHiveKeyName(hKey, &word_180025A14, v18, Data);
          StringCchCopyW(pszPathOut, 0x104u, Data);
          SetPathForRegHiveUse(pszPathOut, v54, v20, 1);
          GetShortPathNameW(pszPathOut, pszPathOut, 0x104u);
          v21 = &word_180025A14;
          if ( !(unsigned int)PathIsUnc2(&word_180025A14)
            && !IsExtendedLengthDosDevicePath(&word_180025A14)
            && word_180025A14 == 92 )
          {
            do
              ++v21;
            while ( *v21 == 92 );
          }
          PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v21, dwFlagsd);
          RegUnLoadKeyW(HKEY_LOCAL_MACHINE, &word_180025A14);
          RegDeleteKeyRecursivelyW(-2147483646, &word_180025A14);
          if ( !RegLoadKeyW(HKEY_LOCAL_MACHINE, &word_180025A14, pszPathOut) )
          {
            v19 = 1;
            dword_180025A10 = 1;
            goto LABEL_36;
          }
          if ( RegCreateKeyExW(hKey, L"RegBackup", 0, 0, 0, 0x2001Fu, 0, &v49, 0) )
          {
LABEL_11:
            LastError = GetLastError();
            v4 = LastError;
            if ( LastError > 0 )
              v4 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_79;
          }
          SetFileAttributesW(pszPathOut, 0x80u);
          DeleteFileW(pszPathOut);
          v22 = RegSaveKeyW(v49, pszPathOut, 0);
          RegCloseKey(v49);
          v49 = 0;
          if ( v22
            || (RegDeleteKeyRecursivelyW(hKey, L"RegBackup"),
                RegLoadKeyW(HKEY_LOCAL_MACHINE, &word_180025A14, pszPathOut)) )
          {
LABEL_34:
            v19 = dword_180025A10;
          }
          else
          {
            v19 = 1;
            dword_180025A10 = 1;
          }
          if ( !v19 )
            goto LABEL_37;
          goto LABEL_36;
        }
      }
    }
  }
LABEL_79:
  if ( v49 )
    RegCloseKey(v49);
  if ( hKey )
    RegCloseKey(hKey);
  if ( phkResult )
  {
    cSubKeys = 0;
    cValues = 0;
    if ( !RegQueryInfoKeyW(phkResult, 0, 0, 0, &cSubKeys, 0, 0, &cValues, 0, 0, 0, 0) && (cSubKeys || cValues) )
      v9 = 0;
    RegCloseKey(phkResult);
    if ( v9 && !RegOpenKeyExW(HKEY_CURRENT_USER, L"Software\\Microsoft\\Advanced INF Setup", 0, 0x2001Fu, &phkResult) )
    {
      RegDeleteKeyRecursivelyW(phkResult, pszMore);
      RegCloseKey(phkResult);
    }
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
    qword_180032320 = 0;
  }
  AdvWriteToLog(L"SaveRestoreInfo: End hr=0x%1!x! %2\r\n", (unsigned int)v4, pszMore);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000e060  mov     [rsp-8+arg_18], rbx
0x18000e065  push    rbp
0x18000e066  push    rsi
0x18000e067  push    rdi
0x18000e068  push    r12
0x18000e06a  push    r13
0x18000e06c  push    r14
0x18000e06e  push    r15
0x18000e070  lea     rbp, [rsp-810h]
0x18000e078  sub     rsp, 910h
0x18000e07f  mov     rax, cs:__security_cookie
0x18000e086  xor     rax, rsp
0x18000e089  mov     [rbp+840h+var_40], rax
0x18000e090  xor     r14d, r14d
0x18000e093  mov     [rbp+840h+lpData], rdx
0x18000e097  mov     [rsp+940h+dwDisposition], r14d
0x18000e09c  mov     ebx, r14d
0x18000e09f  mov     [rsp+940h+hKey], r14
0x18000e0a4  mov     esi, r9d
0x18000e0a7  mov     [rsp+940h+var_8C8], r14
0x18000e0ac  mov     r13, r8
0x18000e0af  mov     [rbp+840h+var_8C0], r14
0x18000e0b3  mov     rdi, rdx
0x18000e0b6  mov     [rsp+940h+cValues], r14d
0x18000e0bb  mov     r12, rcx
0x18000e0be  call    ?NeedBackupData@@YAHPEBG0@Z; NeedBackupData(ushort const *,ushort const *)
0x18000e0c3  lea     r15d, [r14+1]
0x18000e0c7  test    eax, eax
0x18000e0c9  jz      loc_18000EB54
0x18000e0cf  lea     rcx, aSaverestoreinf; "SaveRestoreInfo: "
0x18000e0d6  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000e0db  mov     qword ptr [rsp+940h+samDesired], r14; unsigned int *
0x18000e0e0  lea     r9, [rbp+840h+pszMore]; unsigned __int16 *
0x18000e0e7  mov     r14d, 104h
0x18000e0ed  lea     r8, KeyName; "ComponentName"
0x18000e0f4  mov     rdx, rdi; lpAppName
0x18000e0f7  mov     [rsp+940h+dwFlags], r14d; unsigned int
0x18000e0fc  mov     rcx, r12; unsigned __int16 *
0x18000e0ff  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000e104  test    eax, eax
0x18000e106  js      loc_18000EB54
0x18000e10c  mov     r9, rdi
0x18000e10f  lea     rdx, [rbp+840h+pszMore]
0x18000e116  mov     r8, r12
0x18000e119  lea     rcx, aCompname1Pszin; "CompName=%1 pszInf=%2 Sec=%3\r\n"
0x18000e120  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x18000e125  lea     r8, aSoftwareMicros_2; "Software\\Microsoft\\Advanced INF Setup"
0x18000e12c  mov     edx, r14d; unsigned __int64
0x18000e12f  lea     rcx, [rbp+840h+pszPathOut]; unsigned __int16 *
0x18000e133  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e138  mov     eax, esi
0x18000e13a  and     eax, 8
0x18000e13d  mov     [rbp+840h+var_8B8], eax
0x18000e140  jz      short loc_18000E15A
0x18000e142  lea     rcx, aRegsavelogfile; "RegSaveLogFile"
0x18000e149  call    ?CleanRegLogFile@@YAXPEBG@Z; CleanRegLogFile(ushort const *)
0x18000e14e  lea     rcx, aRegrestorelogf; "RegRestoreLogFile"
0x18000e155  call    ?CleanRegLogFile@@YAXPEBG@Z; CleanRegLogFile(ushort const *)
0x18000e15a  lea     r8, IsBackslash
0x18000e161  xor     edx, edx
0x18000e163  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x18000e16a  lea     rdi, [rbp+840h+pszMore]
0x18000e171  call    PathIsUnc2
0x18000e176  test    eax, eax
0x18000e178  jnz     short loc_18000E19E
0x18000e17a  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x18000e181  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000e186  test    al, al
0x18000e188  jnz     short loc_18000E19E
0x18000e18a  cmp     [rbp+840h+pszMore], 5Ch ; '\'
0x18000e192  jnz     short loc_18000E19E
0x18000e194  add     rdi, 2
0x18000e198  cmp     word ptr [rdi], 5Ch ; '\'
0x18000e19c  jz      short loc_18000E194
0x18000e19e  mov     r9, rdi; pszMore
0x18000e1a1  lea     r8, [rbp+840h+pszPathOut]; pszPathIn
0x18000e1a5  mov     rdx, r14; cchPathOut
0x18000e1a8  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000e1ac  call    PathCchCombineEx
0x18000e1b1  lea     rax, [rsp+940h+dwDisposition]
0x18000e1b6  xor     edi, edi
0x18000e1b8  mov     [rsp+940h+lpdwDisposition], rax; lpdwDisposition
0x18000e1bd  lea     rdx, [rbp+840h+pszPathOut]; lpSubKey
0x18000e1c1  lea     rax, [rsp+940h+hKey]
0x18000e1c6  xor     r9d, r9d; lpClass
0x18000e1c9  mov     [rsp+940h+phkResult], rax; phkResult
0x18000e1ce  xor     r8d, r8d; Reserved
0x18000e1d1  mov     [rsp+940h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18000e1d6  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000e1dd  mov     [rsp+940h+samDesired], 2001Fh; samDesired
0x18000e1e5  mov     [rsp+940h+dwFlags], edi; dwFlags
0x18000e1e9  call    cs:__imp_RegCreateKeyExW
0x18000e1ef  test    eax, eax
0x18000e1f1  jnz     loc_18000EB54
0x18000e1f7  lea     rdi, aRegbackup; "RegBackup"
0x18000e1fe  xor     edx, edx
0x18000e200  mov     rcx, rdi; unsigned __int16 *
0x18000e203  lea     r8, IsBackslash
0x18000e20a  call    PathIsUnc2
0x18000e20f  mov     r9, rdi; pszMore
0x18000e212  lea     r8, [rbp+840h+pszPathOut]; pszPathIn
0x18000e216  mov     rdx, r14; cchPathOut
0x18000e219  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000e21d  call    PathCchCombineEx
0x18000e222  mov     [rsp+940h+lpdwDisposition], rbx; lpdwDisposition
0x18000e227  lea     rax, [rbp+840h+var_8C0]
0x18000e22b  mov     [rsp+940h+phkResult], rax; phkResult
0x18000e230  lea     rdx, [rbp+840h+pszPathOut]; lpSubKey
0x18000e234  mov     [rsp+940h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18000e239  xor     r9d, r9d; lpClass
0x18000e23c  mov     [rsp+940h+samDesired], 2001Fh; samDesired
0x18000e244  xor     r8d, r8d; Reserved
0x18000e247  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000e24e  mov     [rsp+940h+dwFlags], ebx; dwOptions
0x18000e252  call    cs:__imp_RegCreateKeyExW
0x18000e258  test    eax, eax
0x18000e25a  jz      short loc_18000E27C
0x18000e25c  call    cs:__imp_GetLastError
0x18000e262  xor     esi, esi
0x18000e264  mov     ebx, eax
0x18000e266  test    eax, eax
0x18000e268  jle     loc_18000EB56
0x18000e26e  movzx   ebx, ax
0x18000e271  or      ebx, 80070000h
0x18000e277  jmp     loc_18000EB56
0x18000e27c  mov     rcx, [rsp+940h+hKey]; hKey
0x18000e281  lea     rax, [rsp+940h+dwDisposition]
0x18000e286  mov     qword ptr [rsp+940h+samDesired], rax; lpcbData
0x18000e28b  lea     rdx, aBackuppath; "BackupPath"
0x18000e292  lea     rax, [rbp+840h+Data]
0x18000e299  mov     [rsp+940h+dwDisposition], 208h
0x18000e2a1  xor     r9d, r9d; lpType
0x18000e2a4  mov     qword ptr [rsp+940h+dwFlags], rax; lpData
0x18000e2a9  xor     r8d, r8d; lpReserved
0x18000e2ac  mov     [rbp+840h+Data], bx
0x18000e2b3  call    cs:__imp_RegQueryValueExW
0x18000e2b9  cmp     [rbp+840h+Data], bx
0x18000e2c0  jnz     loc_18000E3B5
0x18000e2c6  mov     rdx, [rbp+840h+lpData]; lpAppName
0x18000e2ca  lea     rax, [rbp+840h+var_8B4]
0x18000e2ce  mov     qword ptr [rsp+940h+samDesired], rax; unsigned __int16 *
0x18000e2d3  lea     r9, [rbp+840h+Data]; unsigned __int16 *
0x18000e2da  lea     r8, aBackuppath; "BackupPath"
0x18000e2e1  mov     [rsp+940h+dwFlags], r14d; unsigned int
0x18000e2e6  mov     rcx, r12; unsigned __int16 *
0x18000e2e9  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x18000e2ee  test    eax, eax
0x18000e2f0  js      short loc_18000E306
0x18000e2f2  lea     rcx, [rbp+840h+Data]; unsigned __int16 *
0x18000e2f9  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18000e2fe  test    eax, eax
0x18000e300  jnz     loc_18000E3B5
0x18000e306  mov     edx, r14d; unsigned int
0x18000e309  lea     rcx, [rbp+840h+Data]; unsigned __int16 *
0x18000e310  call    ?GetProgramFilesDir@@YAHPEAGK@Z; GetProgramFilesDir(ushort *,ulong)
0x18000e315  lea     r8, IsBackslash
0x18000e31c  xor     edx, edx
0x18000e31e  lea     rcx, aUninstallInfor; "Uninstall Information"
0x18000e325  call    PathIsUnc2
0x18000e32a  lea     r9, aUninstallInfor; "Uninstall Information"
0x18000e331  mov     rdx, r14; cchPathOut
0x18000e334  lea     r8, [rbp+840h+Data]; pszPathIn
0x18000e33b  lea     rcx, [rbp+840h+Data]; pszPathOut
0x18000e342  call    PathCchCombineEx
0x18000e347  mov     edx, r15d; int
0x18000e34a  lea     rcx, [rbp+840h+Data]; unsigned __int16 *
0x18000e351  call    ?CreateFullPath@@YAJPEBGH@Z; CreateFullPath(ushort const *,int)
0x18000e356  lea     r8, IsBackslash
0x18000e35d  xor     edx, edx
0x18000e35f  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x18000e366  lea     rbx, [rbp+840h+pszMore]
0x18000e36d  call    PathIsUnc2
0x18000e372  test    eax, eax
0x18000e374  jnz     short loc_18000E39A
0x18000e376  lea     rcx, [rbp+840h+pszMore]; unsigned __int16 *
0x18000e37d  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000e382  test    al, al
0x18000e384  jnz     short loc_18000E39A
0x18000e386  cmp     [rbp+840h+pszMore], 5Ch ; '\'
0x18000e38e  jnz     short loc_18000E39A
0x18000e390  add     rbx, 2
0x18000e394  cmp     word ptr [rbx], 5Ch ; '\'
0x18000e398  jz      short loc_18000E390
0x18000e39a  mov     r9, rbx; pszMore
0x18000e39d  lea     r8, [rbp+840h+Data]; pszPathIn
0x18000e3a4  mov     rdx, r14; cchPathOut
0x18000e3a7  lea     rcx, [rbp+840h+Data]; pszPathOut
0x18000e3ae  call    PathCchCombineEx
0x18000e3b3  xor     ebx, ebx
0x18000e3b5  mov     edx, ebx
0x18000e3b7  lea     r9, [rbp+840h+Data]; unsigned __int16 *
0x18000e3be  mov     eax, esi
0x18000e3c0  and     eax, 10h
0x18000e3c3  mov     [rsp+940h+cSubKeys], eax
0x18000e3c7  setnz   dl
0x18000e3ca  and     esi, 40h
0x18000e3cd  mov     eax, esi
0x18000e3cf  mov     dword ptr [rbp+840h+var_8B4], edx
0x18000e3d2  neg     eax
0x18000e3d4  lea     rax, [rbp+840h+pszMore]
0x18000e3db  sbb     ecx, ecx
0x18000e3dd  mov     qword ptr [rsp+940h+dwFlags], rax; unsigned __int16 *
0x18000e3e2  and     ecx, 100h
0x18000e3e8  add     ecx, 10h
0x18000e3eb  or      ecx, edx
0x18000e3ed  lea     rdx, [rbp+840h+var_250]; unsigned __int16 *
0x18000e3f4  mov     [rsp+940h+dwDisposition], ecx
0x18000e3f8  mov     rcx, [rsp+940h+hKey]; HKEY
0x18000e3fd  call    ?GetUniBackupName@@YAHPEAUHKEY__@@PEAGKPEBG2@Z; GetUniBackupName(HKEY__ *,ushort *,ulong,ushort const *,ushort const *)
0x18000e402  mov     eax, [rsp+940h+dwDisposition]
0x18000e406  lea     r9, [rbp+840h+Data]; lpDir
0x18000e40d  mov     rcx, cs:hWnd; hWnd
0x18000e414  mov     r8, r13; SourceRootPath
0x18000e417  mov     r13, [rbp+840h+lpData]
0x18000e41b  mov     dword ptr [rsp+940h+lpSecurityAttributes], eax; DWORD
0x18000e41f  mov     rdx, r13; SectionName
0x18000e422  lea     rax, [rbp+840h+var_250]
0x18000e429  mov     qword ptr [rsp+940h+dwFlags], rax; lpBaseName
0x18000e42e  call    ?ProcessAllFiles@@YAJPEAUHWND__@@PEBG1111K@Z; ProcessAllFiles(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x18000e433  xor     edx, edx
0x18000e435  mov     ebx, eax
0x18000e437  test    eax, eax
0x18000e439  js      loc_18000EB54
0x18000e43f  cmp     cs:?ctx@@3UADVCONTEXTW@@A, dx; ADVCONTEXTW ctx
0x18000e446  jnz     loc_18000E603
0x18000e44c  mov     eax, cs:dword_180025A10
0x18000e452  test    eax, eax
0x18000e454  jnz     loc_18000E616
0x18000e45a  mov     rcx, [rsp+940h+hKey]; HKEY
0x18000e45f  lea     r9, [rbp+840h+Data]; unsigned __int16 *
0x18000e466  lea     rdx, word_180025A14; unsigned __int16 *
0x18000e46d  call    ?GetUniHiveKeyName@@YAHPEAUHKEY__@@PEAGKPEBG@Z; GetUniHiveKeyName(HKEY__ *,ushort *,ulong,ushort const *)
0x18000e472  lea     r8, [rbp+840h+Data]; unsigned __int16 *
0x18000e479  mov     rdx, r14; unsigned __int64
0x18000e47c  lea     rcx, [rbp+840h+pszPathOut]; unsigned __int16 *
0x18000e480  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000e485  mov     r9d, r15d; int
0x18000e488  lea     rdx, [rbp+840h+var_8A8]; unsigned int *
0x18000e48c  lea     rcx, [rbp+840h+pszPathOut]; unsigned __int16 *
0x18000e490  call    ?SetPathForRegHiveUse@@YAXPEBGPEAKHH@Z; SetPathForRegHiveUse(ushort const *,ulong *,int,int)
0x18000e495  mov     r8d, r14d; cchBuffer
0x18000e498  lea     rdx, [rbp+840h+pszPathOut]; lpszShortPath
0x18000e49c  lea     rcx, [rbp+840h+pszPathOut]; lpszLongPath
0x18000e4a0  call    cs:__imp_GetShortPathNameW
0x18000e4a6  lea     r8, IsBackslash
0x18000e4ad  xor     edx, edx
0x18000e4af  lea     rcx, word_180025A14; unsigned __int16 *
0x18000e4b6  lea     rbx, word_180025A14
0x18000e4bd  call    PathIsUnc2
0x18000e4c2  test    eax, eax
0x18000e4c4  jnz     short loc_18000E4EA
0x18000e4c6  lea     rcx, word_180025A14; unsigned __int16 *
0x18000e4cd  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18000e4d2  test    al, al
0x18000e4d4  jnz     short loc_18000E4EA
0x18000e4d6  cmp     cs:word_180025A14, 5Ch ; '\'
0x18000e4de  jnz     short loc_18000E4EA
0x18000e4e0  add     rbx, 2
0x18000e4e4  cmp     word ptr [rbx], 5Ch ; '\'
0x18000e4e8  jz      short loc_18000E4E0
0x18000e4ea  mov     r9, rbx; pszMore
0x18000e4ed  lea     r8, [rbp+840h+pszPathOut]; pszPathIn
0x18000e4f1  mov     rdx, r14; cchPathOut
0x18000e4f4  lea     rcx, [rbp+840h+pszPathOut]; pszPathOut
0x18000e4f8  call    PathCchCombineEx
0x18000e4fd  mov     rbx, 0FFFFFFFF80000002h
0x18000e504  lea     rdx, word_180025A14; lpSubKey
0x18000e50b  mov     rcx, rbx; hKey
0x18000e50e  call    cs:__imp_RegUnLoadKeyW
0x18000e514  lea     rdx, word_180025A14
0x18000e51b  mov     rcx, rbx
0x18000e51e  call    RegDeleteKeyRecursivelyW
0x18000e523  lea     r8, [rbp+840h+pszPathOut]; lpFile
0x18000e527  mov     rcx, rbx; hKey
0x18000e52a  lea     rdx, word_180025A14; lpSubKey
0x18000e531  call    cs:__imp_RegLoadKeyW
0x18000e537  xor     edx, edx
0x18000e539  test    eax, eax
0x18000e53b  jnz     short loc_18000E54B
0x18000e53d  mov     eax, r15d
0x18000e540  mov     cs:dword_180025A10, eax
0x18000e546  jmp     loc_18000E61D
0x18000e54b  mov     rcx, [rsp+940h+hKey]; hKey
0x18000e550  lea     rax, [rsp+940h+var_8C8]
0x18000e555  mov     [rsp+940h+lpdwDisposition], rdx; lpdwDisposition
0x18000e55a  xor     r9d, r9d; lpClass
0x18000e55d  mov     [rsp+940h+phkResult], rax; phkResult
0x18000e562  xor     r8d, r8d; Reserved
0x18000e565  mov     [rsp+940h+lpSecurityAttributes], rdx; lpSecurityAttributes
0x18000e56a  mov     [rsp+940h+samDesired], 2001Fh; samDesired
0x18000e572  mov     [rsp+940h+dwFlags], edx; dwOptions
0x18000e576  mov     rdx, rdi; lpSubKey
0x18000e579  call    cs:__imp_RegCreateKeyExW
0x18000e57f  test    eax, eax
0x18000e581  jnz     loc_18000E25C
0x18000e587  mov     edx, 80h; dwFileAttributes
0x18000e58c  lea     rcx, [rbp+840h+pszPathOut]; lpFileName
0x18000e590  call    cs:__imp_SetFileAttributesW
0x18000e596  lea     rcx, [rbp+840h+pszPathOut]; lpFileName
0x18000e59a  call    cs:__imp_DeleteFileW
  ... truncated ...
```
