# WinReSetupCleanupWinRE

- ea: `0x18002eca0`
- end: `0x18002f072`
- name: `WinReSetupCleanupWinRE`
- size: `978`
- prototype: ``
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update`

## callees

- `0x1800055c8`
- `0x180005694`
- `0x1800059fc`
- `0x18000f044`
- `0x18000fe58`
- `0x18000ffcc`
- `0x1800103f4`
- `0x18001ee2c`
- `0x18001f0c0`
- `0x18001f218`
- `0x18001f47c`
- `0x18002eca0`
- `0x18005cee2`
- `0x18005cf30`
- `0x18005cff0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002edae`
- `KERNEL32!GetLastError` at `0x18002eee7`
- `KERNEL32!GetLastError` at `0x18002ef1c`
- `KERNEL32!GetLastError` at `0x18002efd2`
- `KERNEL32!GetLastError` at `0x18002edae`
- `KERNEL32!GetLastError` at `0x18002eee7`
- `KERNEL32!GetLastError` at `0x18002ef1c`
- `KERNEL32!GetLastError` at `0x18002efd2`
- `KERNEL32!CreateFileW` at `0x18002ef99`
- `KERNEL32!CreateFileW` at `0x18002ef99`
- `KERNEL32!CloseHandle` at `0x18002efca`
- `KERNEL32!CloseHandle` at `0x18002efca`
- `KERNEL32!GetFileAttributesW` at `0x18002ed51`
- `KERNEL32!GetFileAttributesW` at `0x18002ed51`
- `KERNEL32!DeleteFileW` at `0x18002eedd`
- `KERNEL32!DeleteFileW` at `0x18002eedd`
- `KERNEL32!GetVolumePathNameW` at `0x18002ef12`
- `KERNEL32!GetVolumePathNameW` at `0x18002ef12`
- `ole32!CoTaskMemFree` at `0x18002f018`
- `ole32!CoTaskMemFree` at `0x18002f018`

## string_xrefs

- `0x18002ee51`: `failed to allocate path`
- `0x18002eeed`: `failed to delete file`
- `0x18002ee3d`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002eea4`: `base\diagnosis\srt\reagent2\reagent\setup.cpp`
- `0x18002ef22`: `GetVolumePathName failed. Error: 0X%X`
- `0x18002efb3`: `Marker file %s created`
- `0x18002efe6`: `Unable to create the marker file %s. Error: 0X%X`
- `0x18002ed5c`: `target Windows directory does not exist, skip cleanup`
- `0x18002ed7a`: `target Windows is not a directory, skip cleanup`
- `0x18002edb7`: `failed to get winre config, assuming WinRE is disabled: 0x%x`
- `0x18002efff`: `No WinRE installed location available, skip cleanup`
- `0x18002edf2`: `WinRE install location: %s`
- `0x18002ee9d`: `failed to add winre.wim to directory`
- `0x18002eecc`: `Delete installed WinRE: %s`

## pseudocode

```c
__int64 __fastcall WinReSetupCleanupWinRE(const WCHAR *a1)
{
  WCHAR *v2; // rsi
  const unsigned __int16 *v3; // r8
  DWORD FileAttributesW; // eax
  const wchar_t *v5; // rdx
  unsigned int v6; // edi
  DWORD LastError; // eax
  unsigned int v8; // eax
  DWORD v9; // eax
  const wchar_t *v10; // r8
  DWORD v11; // eax
  unsigned __int64 v12; // rax
  __int64 v13; // rcx
  const WCHAR *v14; // rcx
  HANDLE FileW; // r14
  LPCWSTR *v16; // r8
  DWORD v17; // eax
  LPCWSTR *v18; // r8
  const wchar_t *v19; // r8
  __int64 v20; // rdx
  DWORD dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  LPCWSTR lpFileName; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v24[3]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v25; // [rsp+60h] [rbp-A0h]
  __int64 v26; // [rsp+70h] [rbp-90h] BYREF
  int v27; // [rsp+78h] [rbp-88h]
  WCHAR szFileName[1556]; // [rsp+2E8h] [rbp+1E8h] BYREF
  WCHAR szVolumePathName; // [rsp+F10h] [rbp+E10h] BYREF
  _BYTE v30[526]; // [rsp+F12h] [rbp+E12h] BYREF

  memset_0(&v26, 0, 0xEA0u);
  v2 = 0;
  szVolumePathName = 0;
  lpFileName = 0;
  memset_0(v30, 0, 0x206u);
  v25 = 7;
  LOWORD(v24[0]) = 0;
  v24[2] = 0;
  UnattendInitializeLogEx2(0);
  UnattendLogW(0, L"Enter WinReSetupCleanupWinRE");
  v3 = a1;
  if ( !a1 )
    v3 = L"NULL";
  UnattendLogW(0, L"targetWinDir: %s", v3);
  FileAttributesW = GetFileAttributesW(a1);
  if ( FileAttributesW == -1 )
  {
    v5 = L"target Windows directory does not exist, skip cleanup";
LABEL_5:
    UnattendLogW(0, v5);
LABEL_6:
    v6 = 1;
    goto LABEL_37;
  }
  if ( (FileAttributesW & 0x10) == 0 )
  {
    UnattendLogW(0, L"target Windows is not a directory, skip cleanup");
    goto LABEL_6;
  }
  v6 = 0;
  UnattendLogW(0, L"Looking for winre.wim");
  v26 = 3744;
  if ( !(unsigned int)WinReGetConfigInternal(a1, 1, &v26) )
  {
    LastError = GetLastError();
    UnattendLogW(2, L"failed to get winre config, assuming WinRE is disabled: 0x%x", LastError);
    goto LABEL_37;
  }
  if ( !v27 )
  {
    v5 = L"WinRE is not available, skip cleanup";
    goto LABEL_5;
  }
  if ( szFileName[0] )
  {
    UnattendLogW(0, L"WinRE install location: %s", szFileName);
    if ( !(unsigned int)winreDoesFileExist(szFileName, L"Winre.wim") )
    {
      UnattendLogW(0, L"WinRE doesn't exist in %s, skip cleanup", szFileName);
      goto LABEL_6;
    }
    v8 = winreAllocPath(&lpFileName);
    if ( v8 )
    {
      UnattendLogW(
        2,
        L"WinReSetupCleanupWinRE %s (0x%x) in file %S line %d",
        L"failed to allocate path",
        v8,
        "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
        1330);
      v2 = (WCHAR *)lpFileName;
    }
    else
    {
      v2 = (WCHAR *)lpFileName;
      v9 = winreAddFileToDirPath(szFileName, L"Winre.wim", (unsigned __int16 *)lpFileName);
      if ( v9 )
      {
        dwFlagsAndAttributes = 1333;
        v10 = L"failed to add winre.wim to directory";
      }
      else
      {
        UnattendLogW(0, L"Delete installed WinRE: %s", v2);
        if ( DeleteFileW(v2) )
        {
          if ( GetVolumePathNameW(szFileName, &szVolumePathName, 0x104u) )
          {
            std::wstring::assign(v24, &szVolumePathName);
            v12 = std::char_traits<unsigned short>::length(L"$WINRE_BACKUP_PARTITION.MARKER");
            std::wstring::append(v24, v13, v12);
            v14 = (const WCHAR *)v24;
            if ( v25 >= 8 )
              v14 = v24[0];
            FileW = CreateFileW(v14, 0x40000000u, 0, 0, 2u, 2u, 0);
            if ( FileW == (HANDLE)-1LL )
            {
              v17 = GetLastError();
              v18 = v24;
              if ( v25 >= 8 )
                v18 = (LPCWSTR *)v24[0];
              UnattendLogW(2, L"Unable to create the marker file %s. Error: 0X%X", v18, v17);
            }
            else
            {
              v16 = v24;
              if ( v25 >= 8 )
                v16 = (LPCWSTR *)v24[0];
              UnattendLogW(0, L"Marker file %s created", v16);
              CloseHandle(FileW);
            }
          }
          else
          {
            v11 = GetLastError();
            UnattendLogW(2, L"GetVolumePathName failed. Error: 0X%X", v11);
          }
          goto LABEL_35;
        }
        v9 = GetLastError();
        v10 = L"failed to delete file";
        dwFlagsAndAttributes = 1336;
      }
      UnattendLogW(
        2,
        L"WinReSetupCleanupWinRE %s (0x%x) in file %S line %d",
        v10,
        v9,
        "base\\diagnosis\\srt\\reagent2\\reagent\\setup.cpp",
        dwFlagsAndAttributes);
    }
  }
  else
  {
    UnattendLogW(0, L"No WinRE installed location available, skip cleanup");
    v6 = 1;
  }
LABEL_35:
  if ( v2 )
    CoTaskMemFree(v2);
LABEL_37:
  v19 = L"TRUE";
  if ( !v6 )
    v19 = L"FALSE";
  UnattendLogW(0, L" (WinRE)WinReSetupCleanupWinRE() returning %s", v19);
  UnattendFinalizeLog();
  LOBYTE(v20) = 1;
  std::wstring::_Tidy(v24, v20, 0);
  return v6;
}

```

## disassembly

```asm
0x18002eca0  push    rbp
0x18002eca2  push    rsi
0x18002eca3  push    rdi
0x18002eca4  push    r14
0x18002eca6  lea     rbp, [rsp-1038h]
0x18002ecae  mov     eax, 1138h
0x18002ecb3  call    _alloca_probe
0x18002ecb8  sub     rsp, rax
0x18002ecbb  mov     rax, cs:__security_cookie
0x18002ecc2  xor     rax, rsp
0x18002ecc5  mov     [rbp+1050h+var_30], rax
0x18002eccc  mov     r14, rcx
0x18002eccf  xor     edx, edx; Val
0x18002ecd1  lea     rcx, [rsp+1150h+var_10E0]; void *
0x18002ecd6  mov     r8d, 0EA0h; Size
0x18002ecdc  call    memset_0
0x18002ece1  xor     eax, eax
0x18002ece3  lea     rcx, [rbp+1050h+var_23E]; void *
0x18002ecea  xor     esi, esi
0x18002ecec  mov     [rbp+1050h+szVolumePathName], ax
0x18002ecf3  xor     edx, edx; Val
0x18002ecf5  mov     [rsp+1150h+lpFileName], rsi
0x18002ecfa  mov     r8d, 206h; Size
0x18002ed00  call    memset_0
0x18002ed05  xor     eax, eax
0x18002ed07  mov     [rsp+1150h+var_10F0], 7
0x18002ed10  xor     ecx, ecx
0x18002ed12  mov     word ptr [rsp+1150h+var_1108], ax
0x18002ed17  mov     [rsp+1150h+var_10F8], rsi
0x18002ed1c  call    UnattendInitializeLogEx2
0x18002ed21  lea     rdx, aEnterWinresetu_0; "Enter WinReSetupCleanupWinRE"
0x18002ed28  xor     ecx, ecx
0x18002ed2a  call    UnattendLogW
0x18002ed2f  lea     rax, aNull_0; "NULL"
0x18002ed36  test    r14, r14
0x18002ed39  mov     r8, r14
0x18002ed3c  lea     rdx, aTargetwindirS; "targetWinDir: %s"
0x18002ed43  cmovz   r8, rax
0x18002ed47  xor     ecx, ecx
0x18002ed49  call    UnattendLogW
0x18002ed4e  mov     rcx, r14; lpFileName
0x18002ed51  call    cs:__imp_GetFileAttributesW
0x18002ed57  cmp     eax, 0FFFFFFFFh
0x18002ed5a  jnz     short loc_18002ED74
0x18002ed5c  lea     rdx, aTargetWindowsD; "target Windows directory does not exist"...
0x18002ed63  xor     ecx, ecx
0x18002ed65  call    UnattendLogW
0x18002ed6a  mov     edi, 1
0x18002ed6f  jmp     loc_18002F01E
0x18002ed74  xor     ecx, ecx
0x18002ed76  test    al, 10h
0x18002ed78  jnz     short loc_18002ED83
0x18002ed7a  lea     rdx, aTargetWindowsI; "target Windows is not a directory, skip"...
0x18002ed81  jmp     short loc_18002ED65
0x18002ed83  lea     rdx, aLookingForWinr; "Looking for winre.wim"
0x18002ed8a  xor     edi, edi
0x18002ed8c  call    UnattendLogW
0x18002ed91  lea     r8, [rsp+1150h+var_10E0]
0x18002ed96  mov     [rsp+1150h+var_10E0], 0EA0h
0x18002ed9f  lea     edx, [rdi+1]
0x18002eda2  mov     rcx, r14
0x18002eda5  call    WinReGetConfigInternal
0x18002edaa  test    eax, eax
0x18002edac  jnz     short loc_18002EDCB
0x18002edae  call    cs:__imp_GetLastError
0x18002edb4  mov     r8d, eax
0x18002edb7  lea     rdx, aFailedToGetWin_8; "failed to get winre config, assuming Wi"...
0x18002edbe  lea     ecx, [rdi+2]
0x18002edc1  call    UnattendLogW
0x18002edc6  jmp     loc_18002F01E
0x18002edcb  cmp     [rsp+1150h+var_10D8], esi
0x18002edcf  jnz     short loc_18002EDDA
0x18002edd1  lea     rdx, aWinreIsNotAvai; "WinRE is not available, skip cleanup"
0x18002edd8  jmp     short loc_18002ED63
0x18002edda  xor     eax, eax
0x18002eddc  xor     ecx, ecx
0x18002edde  cmp     ax, [rbp+1050h+szFileName]
0x18002ede5  jz      loc_18002EFFF
0x18002edeb  lea     r8, [rbp+1050h+szFileName]
0x18002edf2  lea     rdx, aWinreInstallLo; "WinRE install location: %s"
0x18002edf9  call    UnattendLogW
0x18002edfe  lea     rdx, aWinreWim; "Winre.wim"
0x18002ee05  lea     rcx, [rbp+1050h+szFileName]; unsigned __int16 *
0x18002ee0c  call    winreDoesFileExist
0x18002ee11  test    eax, eax
0x18002ee13  jnz     short loc_18002EE2F
0x18002ee15  lea     r8, [rbp+1050h+szFileName]
0x18002ee1c  xor     ecx, ecx
0x18002ee1e  lea     rdx, aWinreDoesnTExi; "WinRE doesn't exist in %s, skip cleanup"
0x18002ee25  call    UnattendLogW
0x18002ee2a  jmp     loc_18002ED6A
0x18002ee2f  lea     rcx, [rsp+1150h+lpFileName]
0x18002ee34  call    winreAllocPath
0x18002ee39  test    eax, eax
0x18002ee3b  jz      short loc_18002EE76
0x18002ee3d  lea     rcx, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002ee44  mov     [rsp+1150h+dwFlagsAndAttributes], 532h
0x18002ee4c  mov     qword ptr [rsp+1150h+dwCreationDisposition], rcx
0x18002ee51  lea     r8, aFailedToAlloca_4; "failed to allocate path"
0x18002ee58  mov     ecx, 2
0x18002ee5d  lea     rdx, aWinresetupclea_0; "WinReSetupCleanupWinRE %s (0x%x) in fil"...
0x18002ee64  mov     r9d, eax
0x18002ee67  call    UnattendLogW
0x18002ee6c  mov     rsi, [rsp+1150h+lpFileName]
0x18002ee71  jmp     loc_18002F010
0x18002ee76  mov     rsi, [rsp+1150h+lpFileName]
0x18002ee7b  lea     rdx, aWinreWim; "Winre.wim"
0x18002ee82  mov     r8, rsi; unsigned __int16 *
0x18002ee85  lea     rcx, [rbp+1050h+szFileName]; unsigned __int16 *
0x18002ee8c  call    winreAddFileToDirPath
0x18002ee91  test    eax, eax
0x18002ee93  jz      short loc_18002EEC9
0x18002ee95  mov     [rsp+1150h+dwFlagsAndAttributes], 535h
0x18002ee9d  lea     r8, aFailedToAddWin; "failed to add winre.wim to directory"
0x18002eea4  lea     rcx, aBaseDiagnosisS_5; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18002eeab  mov     r9d, eax
0x18002eeae  mov     qword ptr [rsp+1150h+dwCreationDisposition], rcx
0x18002eeb3  lea     rdx, aWinresetupclea_0; "WinReSetupCleanupWinRE %s (0x%x) in fil"...
0x18002eeba  mov     ecx, 2
0x18002eebf  call    UnattendLogW
0x18002eec4  jmp     loc_18002F010
0x18002eec9  mov     r8, rsi
0x18002eecc  lea     rdx, aDeleteInstalle; "Delete installed WinRE: %s"
0x18002eed3  xor     ecx, ecx
0x18002eed5  call    UnattendLogW
0x18002eeda  mov     rcx, rsi; lpFileName
0x18002eedd  call    cs:__imp_DeleteFileW
0x18002eee3  test    eax, eax
0x18002eee5  jnz     short loc_18002EEFE
0x18002eee7  call    cs:__imp_GetLastError
0x18002eeed  lea     r8, aFailedToDelete_10; "failed to delete file"
0x18002eef4  mov     [rsp+1150h+dwFlagsAndAttributes], 538h
0x18002eefc  jmp     short loc_18002EEA4
0x18002eefe  mov     r8d, 104h; cchBufferLength
0x18002ef04  lea     rdx, [rbp+1050h+szVolumePathName]; lpszVolumePathName
0x18002ef0b  lea     rcx, [rbp+1050h+szFileName]; lpszFileName
0x18002ef12  call    cs:__imp_GetVolumePathNameW
0x18002ef18  test    eax, eax
0x18002ef1a  jnz     short loc_18002EF3B
0x18002ef1c  call    cs:__imp_GetLastError
0x18002ef22  lea     rdx, aGetvolumepathn; "GetVolumePathName failed. Error: 0X%X"
0x18002ef29  mov     ecx, 2
0x18002ef2e  mov     r8d, eax
0x18002ef31  call    UnattendLogW
0x18002ef36  jmp     loc_18002F010
0x18002ef3b  lea     rdx, [rbp+1050h+szVolumePathName]
0x18002ef42  lea     rcx, [rsp+1150h+var_1108]
0x18002ef47  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x18002ef4c  lea     rcx, aWinreBackupPar; "$WINRE_BACKUP_PARTITION.MARKER"
0x18002ef53  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18002ef58  mov     rdx, rcx
0x18002ef5b  mov     r8, rax
0x18002ef5e  lea     rcx, [rsp+1150h+var_1108]
0x18002ef63  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18002ef68  cmp     [rsp+1150h+var_10F0], 8
0x18002ef6e  lea     rcx, [rsp+1150h+var_1108]
0x18002ef73  mov     [rsp+1150h+hTemplateFile], rdi; hTemplateFile
0x18002ef78  mov     edx, 40000000h; dwDesiredAccess
0x18002ef7d  cmovnb  rcx, [rsp+1150h+var_1108]; lpFileName
0x18002ef83  xor     r9d, r9d; lpSecurityAttributes
0x18002ef86  xor     r8d, r8d; dwShareMode
0x18002ef89  mov     [rsp+1150h+dwFlagsAndAttributes], 2; dwFlagsAndAttributes
0x18002ef91  mov     [rsp+1150h+dwCreationDisposition], 2; dwCreationDisposition
0x18002ef99  call    cs:__imp_CreateFileW
0x18002ef9f  mov     r14, rax
0x18002efa2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18002efa6  jz      short loc_18002EFD2
0x18002efa8  cmp     [rsp+1150h+var_10F0], 8
0x18002efae  lea     r8, [rsp+1150h+var_1108]
0x18002efb3  lea     rdx, aMarkerFileSCre; "Marker file %s created"
0x18002efba  cmovnb  r8, [rsp+1150h+var_1108]
0x18002efc0  xor     ecx, ecx
0x18002efc2  call    UnattendLogW
0x18002efc7  mov     rcx, r14; hObject
0x18002efca  call    cs:__imp_CloseHandle
0x18002efd0  jmp     short loc_18002F010
0x18002efd2  call    cs:__imp_GetLastError
0x18002efd8  cmp     [rsp+1150h+var_10F0], 8
0x18002efde  lea     r8, [rsp+1150h+var_1108]
0x18002efe3  mov     r9d, eax
0x18002efe6  lea     rdx, aUnableToCreate; "Unable to create the marker file %s. Er"...
0x18002efed  cmovnb  r8, [rsp+1150h+var_1108]
0x18002eff3  mov     ecx, 2
0x18002eff8  call    UnattendLogW
0x18002effd  jmp     short loc_18002F010
0x18002efff  lea     rdx, aNoWinreInstall_0; "No WinRE installed location available, "...
0x18002f006  call    UnattendLogW
0x18002f00b  mov     edi, 1
0x18002f010  test    rsi, rsi
0x18002f013  jz      short loc_18002F01E
0x18002f015  mov     rcx, rsi; pv
0x18002f018  call    cs:__imp_CoTaskMemFree
0x18002f01e  lea     rax, aFalse_0; "FALSE"
0x18002f025  test    edi, edi
0x18002f027  lea     r8, aTrue_0; "TRUE"
0x18002f02e  cmovz   r8, rax
0x18002f032  lea     rdx, aWinreWinresetu_2; " (WinRE)WinReSetupCleanupWinRE() return"...
0x18002f039  xor     ecx, ecx
0x18002f03b  call    UnattendLogW
0x18002f040  call    UnattendFinalizeLog
0x18002f045  xor     r8d, r8d
0x18002f048  lea     rcx, [rsp+1150h+var_1108]
0x18002f04d  mov     dl, 1
0x18002f04f  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18002f054  mov     eax, edi
0x18002f056  mov     rcx, [rbp+1050h+var_30]
0x18002f05d  xor     rcx, rsp; StackCookie
0x18002f060  call    __security_check_cookie
0x18002f065  add     rsp, 1138h
0x18002f06c  pop     r14
0x18002f06e  pop     rdi
0x18002f06f  pop     rsi
0x18002f070  pop     rbp
0x18002f071  retn
```
