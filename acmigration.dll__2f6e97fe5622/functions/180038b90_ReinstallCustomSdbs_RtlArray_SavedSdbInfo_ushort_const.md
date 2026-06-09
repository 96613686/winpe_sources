# ReinstallCustomSdbs(RtlArray<_SavedSdbInfo> &,ushort const *)

- ea: `0x180038b90`
- end: `0x1800390f5`
- name: `?ReinstallCustomSdbs@@YAJAEAV?$RtlArray@U_SavedSdbInfo@@@@PEBG@Z`
- size: `1381`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800382f0`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x18000a51c`
- `0x18000a654`
- `0x180038200`
- `0x1800385d8`
- `0x18003862c`
- `0x180038b90`
- `0x1800392b4`
- `0x18004fec8`
- `0x1800543c0`
- `0x180060954`
- `0x1800650c0`

## import_xrefs

- `KERNEL32!CreateProcessW` at `0x180038e8f`
- `KERNEL32!CreateProcessW` at `0x180038f88`
- `KERNEL32!CreateProcessW` at `0x180038e8f`
- `KERNEL32!CreateProcessW` at `0x180038f88`
- `KERNEL32!CloseHandle` at `0x180039015`
- `KERNEL32!CloseHandle` at `0x18003902a`
- `KERNEL32!CloseHandle` at `0x1800390ac`
- `KERNEL32!CloseHandle` at `0x1800390c1`
- `KERNEL32!CloseHandle` at `0x180039015`
- `KERNEL32!CloseHandle` at `0x18003902a`
- `KERNEL32!CloseHandle` at `0x1800390ac`
- `KERNEL32!CloseHandle` at `0x1800390c1`
- `KERNEL32!GetLastError` at `0x180038e99`
- `KERNEL32!GetLastError` at `0x180038eed`
- `KERNEL32!GetLastError` at `0x180038f92`
- `KERNEL32!GetLastError` at `0x180038fce`
- `KERNEL32!GetLastError` at `0x18003904a`
- `KERNEL32!GetLastError` at `0x180038e99`
- `KERNEL32!GetLastError` at `0x180038eed`
- `KERNEL32!GetLastError` at `0x180038f92`
- `KERNEL32!GetLastError` at `0x180038fce`
- `KERNEL32!GetLastError` at `0x18003904a`
- `KERNEL32!WaitForSingleObject` at `0x180038ede`
- `KERNEL32!WaitForSingleObject` at `0x180038fbf`
- `KERNEL32!WaitForSingleObject` at `0x180038ede`
- `KERNEL32!WaitForSingleObject` at `0x180038fbf`
- `ADVAPI32!RegOpenKeyExW` at `0x180038c95`
- `ADVAPI32!RegOpenKeyExW` at `0x180038c95`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180038cd0`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180038cd0`

## string_xrefs

- `0x180038c29`: `\InstalledSDB`
- `0x180039078`: `Failed to open installed sdb key: 0x%x`
- `0x180038d9e`: `ReinstallCustomSdbs`
- `0x180038ec1`: `ReinstallCustomSdbs`
- `0x180038f19`: `ReinstallCustomSdbs`
- `0x180038ffa`: `ReinstallCustomSdbs`
- `0x180039091`: `ReinstallCustomSdbs`
- `0x180038c5a`: `%WINDIR%\system32\sdbinst.exe`
- `0x180038d42`: `Cannot reinstall sdb without temporary path: 0x%x`
- `0x180038eb0`: `Failed to create uninstall process: 0x%x`
- `0x180038f08`: `Failed to wait for uninstall process: 0x%x`
- `0x180038fa9`: `Failed to create install process: 0x%x`
- `0x180038fe9`: `Failed to wait for install process: 0x%x`

## pseudocode

```c
__int64 __fastcall ReinstallCustomSdbs(unsigned __int64 *a1, const WCHAR *a2)
{
  unsigned int v4; // edx
  const unsigned __int16 *v5; // r8
  const unsigned __int16 *v6; // r9
  int PersistedLocation; // eax
  signed int v8; // ebx
  HRESULT v9; // eax
  unsigned int v10; // edx
  LSTATUS v11; // eax
  __int64 v12; // rdx
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r14
  unsigned __int64 v15; // rbx
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // rcx
  int v18; // eax
  size_t v19; // rdx
  signed int LastError; // eax
  bool v21; // sf
  DWORD v22; // eax
  signed int v23; // eax
  bool v24; // sf
  signed int v25; // eax
  bool v26; // sf
  const char *v27; // r9
  __int64 v28; // r8
  DWORD v29; // eax
  bool v30; // sf
  signed int v31; // eax
  int phkResult; // [rsp+20h] [rbp-E0h]
  PHKEY phkResulta; // [rsp+20h] [rbp-E0h]
  PHKEY phkResultb; // [rsp+20h] [rbp-E0h]
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+50h] [rbp-B0h] BYREF
  HKEY v37; // [rsp+68h] [rbp-98h] BYREF
  __int128 v38; // [rsp+70h] [rbp-90h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+80h] [rbp-80h] BYREF
  wchar_t pszDest[264]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR pszPath[264]; // [rsp+300h] [rbp+200h] BYREF
  WCHAR Dst[264]; // [rsp+510h] [rbp+410h] BYREF
  unsigned __int16 v43[264]; // [rsp+720h] [rbp+620h] BYREF
  WCHAR pszPathOut[264]; // [rsp+930h] [rbp+830h] BYREF
  wchar_t CommandLine[520]; // [rsp+B40h] [rbp+A40h] BYREF
  wchar_t v46[520]; // [rsp+F50h] [rbp+E50h] BYREF

  v38 = 0;
  memset_0(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v37 = 0;
  PersistedLocation = Windows::Compat::Shared::Registry::GetPersistedLocation(pszDest, v4, v5, v6, phkResult);
  v8 = PersistedLocation;
  if ( PersistedLocation < 0 )
  {
    LODWORD(phkResulta) = PersistedLocation;
    AslLogCallPrintf(1, "ReinstallCustomSdbs", 1263, "Failed to get persisted reg key location: 0x%x", phkResulta);
    goto LABEL_74;
  }
  v9 = StringCchCatW(pszDest, 0x104u, L"\\InstalledSDB");
  v8 = v9;
  if ( v9 < 0 )
  {
    LODWORD(phkResulta) = v9;
    AslLogCallPrintf(1, "ReinstallCustomSdbs", 1270, "Failed to concat string: 0x%x", phkResulta);
    goto LABEL_74;
  }
  v8 = ExpandDirectory(Dst, v10, L"%WINDIR%\\system32\\sdbinst.exe");
  if ( v8 < 0 )
    goto LABEL_74;
  v11 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, pszDest, 0, 0x20119u, &v37);
  v8 = v11;
  if ( v11 )
  {
    if ( v11 > 0 )
      v8 = (unsigned __int16)v11 | 0x80070000;
    goto LABEL_71;
  }
  if ( !v37 )
  {
LABEL_71:
    if ( v8 >= 0 )
      v8 = -2147467259;
    LODWORD(phkResultb) = v8;
    AslLogCallPrintf(1, "ReinstallCustomSdbs", 1288, "Failed to open installed sdb key: 0x%x", phkResultb);
    goto LABEL_74;
  }
  if ( (unsigned int)SdbGetPathCustomSdb(pszPath, v12, &v38) && PathRemoveFileSpecW(pszPath) )
  {
    v13 = a1[2];
    if ( v13 )
    {
      v14 = 0;
      while ( 1 )
      {
        v15 = 0;
        if ( v14 < v13 )
        {
          v16 = a1[1] * v14;
          if ( !is_mul_ok(a1[1], v14) || (v17 = a1[5], v15 = v17 + v16, v17 + v16 < v17) )
            v15 = 0;
        }
        if ( !*(_QWORD *)v15 || !*(_QWORD *)(v15 + 32) || !*(_DWORD *)(v15 + 8) )
          goto LABEL_58;
        if ( !*(_DWORD *)(v15 + 24) )
          break;
        if ( CopySdbToNewLocation((struct _SavedSdbInfo *)v15, a2, pszPath, v43, (unsigned __int64)phkResultb) >= 0 )
        {
          v18 = ReregisterSdb(v37, *(const unsigned __int16 **)v15, v43);
          if ( v18 >= 0 )
          {
            phkResultb = *(PHKEY *)v15;
            if ( StringCchPrintfW(CommandLine, 0x208u, L"%ls -q -u -g %ls", Dst) >= 0
              && PathCchCombineEx(pszPathOut, v19, a2, *(PCWSTR *)(v15 + 32), (ULONG)phkResultb) >= 0 )
            {
              phkResultb = (PHKEY)pszPathOut;
              if ( StringCchPrintfW(v46, 0x208u, L"%ls -q %ls", Dst) >= 0 )
              {
                memset_0(&StartupInfo.cb + 1, 0, 0x64u);
                StartupInfo.cb = 104;
                memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                if ( !CreateProcessW(0, CommandLine, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                {
                  LastError = GetLastError();
                  v21 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v21 = LastError < 0;
                  }
                  if ( !v21 )
                    LastError = -2147467259;
                  AslLogCallPrintf(
                    1,
                    "ReinstallCustomSdbs",
                    1398,
                    "Failed to create uninstall process: 0x%x",
                    LastError);
                }
                v22 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
                if ( v22 )
                {
                  if ( v22 == -1 )
                  {
                    v23 = GetLastError();
                    v24 = v23 < 0;
                    if ( v23 > 0 )
                    {
                      v23 = (unsigned __int16)v23 | 0x80070000;
                      v24 = v23 < 0;
                    }
                    if ( !v24 )
                      v23 = -2147467259;
                  }
                  else
                  {
                    v23 = -2147467259;
                  }
                  AslLogCallPrintf(1, "ReinstallCustomSdbs", 1412, "Failed to wait for uninstall process: 0x%x", v23);
                }
                memset_0(&StartupInfo.cb + 1, 0, 0x64u);
                StartupInfo.cb = 104;
                memset(&ProcessInformation, 0, sizeof(ProcessInformation));
                if ( !CreateProcessW(0, v46, 0, 0, 0, 8u, 0, 0, &StartupInfo, &ProcessInformation) )
                {
                  v25 = GetLastError();
                  v26 = v25 < 0;
                  if ( v25 > 0 )
                  {
                    v25 = (unsigned __int16)v25 | 0x80070000;
                    v26 = v25 < 0;
                  }
                  if ( !v26 )
                    v25 = -2147467259;
                  v27 = "Failed to create install process: 0x%x";
                  v28 = 1436;
                  goto LABEL_57;
                }
                v29 = WaitForSingleObject(ProcessInformation.hProcess, 0xEA60u);
                if ( v29 )
                {
                  if ( v29 == -1 )
                  {
                    v25 = GetLastError();
                    v30 = v25 < 0;
                    if ( v25 > 0 )
                    {
                      v25 = (unsigned __int16)v25 | 0x80070000;
                      v30 = v25 < 0;
                    }
                    if ( !v30 )
                      v25 = -2147467259;
                  }
                  else
                  {
                    v25 = -2147467259;
                  }
                  v27 = "Failed to wait for install process: 0x%x";
                  v28 = 1451;
LABEL_57:
                  LODWORD(phkResultb) = v25;
                  AslLogCallPrintf(1, "ReinstallCustomSdbs", v28, v27, phkResultb);
                }
              }
            }
LABEL_58:
            if ( ProcessInformation.hProcess )
            {
              CloseHandle(ProcessInformation.hProcess);
              ProcessInformation.hProcess = 0;
            }
            if ( ProcessInformation.hThread )
            {
              CloseHandle(ProcessInformation.hThread);
              ProcessInformation.hThread = 0;
            }
            goto LABEL_62;
          }
          AslLogCallPrintf(1, "ReinstallCustomSdbs", 1351, "Failed to reregister sdb: 0x%x", v18);
        }
LABEL_62:
        v13 = a1[2];
        if ( ++v14 >= v13 )
          goto LABEL_63;
      }
      LODWORD(phkResultb) = -2147019873;
      AslLogCallPrintf(1, "ReinstallCustomSdbs", 1330, "Cannot reinstall sdb without temporary path: 0x%x", phkResultb);
      goto LABEL_58;
    }
LABEL_63:
    v8 = 0;
  }
  else
  {
    v31 = GetLastError();
    v8 = v31;
    if ( v31 > 0 )
      v8 = (unsigned __int16)v31 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
  }
LABEL_74:
  if ( ProcessInformation.hProcess )
  {
    CloseHandle(ProcessInformation.hProcess);
    ProcessInformation.hProcess = 0;
  }
  if ( ProcessInformation.hThread )
    CloseHandle(ProcessInformation.hThread);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180038b90  mov     [rsp-8+arg_10], rbx
0x180038b95  mov     [rsp-8+arg_18], rdi
0x180038b9a  push    rbp
0x180038b9b  push    r12
0x180038b9d  push    r13
0x180038b9f  push    r14
0x180038ba1  push    r15
0x180038ba3  lea     rbp, [rsp-1270h]
0x180038bab  mov     eax, 1370h
0x180038bb0  call    _alloca_probe
0x180038bb5  sub     rsp, rax
0x180038bb8  mov     rax, cs:__security_cookie
0x180038bbf  xor     rax, rsp
0x180038bc2  mov     [rbp+1290h+var_30], rax
0x180038bc9  mov     r12, rdx
0x180038bcc  mov     r15, rcx
0x180038bcf  xor     edx, edx; Val
0x180038bd1  lea     rcx, [rbp+1290h+StartupInfo+4]; void *
0x180038bd5  xorps   xmm0, xmm0
0x180038bd8  movups  [rsp+1390h+var_1320], xmm0
0x180038bdd  lea     r8d, [rdx+64h]; Size
0x180038be1  call    memset_0
0x180038be6  xorps   xmm0, xmm0
0x180038be9  mov     [rbp+1290h+StartupInfo.cb], 68h ; 'h'
0x180038bf0  xor     eax, eax
0x180038bf2  lea     rcx, [rbp+1290h+pszDest]; unsigned __int16 *
0x180038bf6  xor     r13d, r13d
0x180038bf9  mov     qword ptr [rsp+1390h+ProcessInformation.dwProcessId], rax
0x180038bfe  movups  xmmword ptr [rsp+1390h+ProcessInformation.hProcess], xmm0
0x180038c03  mov     [rsp+1390h+var_1328], r13
0x180038c08  call    ?GetPersistedLocation@Registry@Shared@Compat@Windows@@SAJPEAGKQEBG1H@Z; Windows::Compat::Shared::Registry::GetPersistedLocation(ushort *,ulong,ushort const * const,ushort const * const,int)
0x180038c0d  mov     ebx, eax
0x180038c0f  test    eax, eax
0x180038c11  jns     short loc_180038C29
0x180038c13  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038c17  lea     r9, aFailedToGetPer; "Failed to get persisted reg key locatio"...
0x180038c1e  mov     r8d, 4EFh
0x180038c24  jmp     loc_180039091
0x180038c29  lea     r8, aInstalledsdb; "\\InstalledSDB"
0x180038c30  mov     edx, 104h; cchDest
0x180038c35  lea     rcx, [rbp+1290h+pszDest]; pszDest
0x180038c39  call    StringCchCatW
0x180038c3e  mov     ebx, eax
0x180038c40  test    eax, eax
0x180038c42  jns     short loc_180038C5A
0x180038c44  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038c48  lea     r9, aFailedToConcat; "Failed to concat string: 0x%x"
0x180038c4f  mov     r8d, 4F6h
0x180038c55  jmp     loc_180039091
0x180038c5a  lea     r8, aWindirSystem32_6; "%WINDIR%\\system32\\sdbinst.exe"
0x180038c61  lea     rcx, [rbp+1290h+Dst]; lpDst
0x180038c68  call    ?ExpandDirectory@@YAJPEAGKPEBG@Z; ExpandDirectory(ushort *,ulong,ushort const *)
0x180038c6d  mov     ebx, eax
0x180038c6f  test    eax, eax
0x180038c71  js      loc_1800390A2
0x180038c77  lea     rax, [rsp+1390h+var_1328]
0x180038c7c  mov     r9d, 20119h; samDesired
0x180038c82  xor     r8d, r8d; ulOptions
0x180038c85  mov     [rsp+1390h+phkResult], rax; unsigned __int64
0x180038c8a  lea     rdx, [rbp+1290h+pszDest]; lpSubKey
0x180038c8e  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180038c95  call    cs:__imp_RegOpenKeyExW
0x180038c9b  mov     ebx, eax
0x180038c9d  test    eax, eax
0x180038c9f  jnz     loc_18003906B
0x180038ca5  cmp     [rsp+1390h+var_1328], r13
0x180038caa  jz      loc_180039076
0x180038cb0  lea     r8, [rsp+1390h+var_1320]
0x180038cb5  lea     rcx, [rbp+1290h+pszPath]
0x180038cbc  call    SdbGetPathCustomSdb
0x180038cc1  test    eax, eax
0x180038cc3  jz      loc_18003904A
0x180038cc9  lea     rcx, [rbp+1290h+pszPath]; pszPath
0x180038cd0  call    cs:__imp_PathRemoveFileSpecW
0x180038cd6  test    eax, eax
0x180038cd8  jz      loc_18003904A
0x180038cde  mov     rax, [r15+10h]
0x180038ce2  test    rax, rax
0x180038ce5  jz      loc_180039045
0x180038ceb  mov     r14, r13
0x180038cee  mov     edi, 80004005h
0x180038cf3  mov     rbx, r13
0x180038cf6  cmp     r14, rax
0x180038cf9  jnb     short loc_180038D17
0x180038cfb  mov     rax, r14
0x180038cfe  mul     qword ptr [r15+8]
0x180038d02  test    rdx, rdx
0x180038d05  jnz     short loc_180038D14
0x180038d07  mov     rcx, [r15+28h]
0x180038d0b  lea     rbx, [rcx+rax]
0x180038d0f  cmp     rbx, rcx
0x180038d12  jnb     short loc_180038D17
0x180038d14  mov     rbx, r13
0x180038d17  cmp     [rbx], r13
0x180038d1a  jz      loc_18003900B
0x180038d20  cmp     [rbx+20h], r13
0x180038d24  jz      loc_18003900B
0x180038d2a  cmp     [rbx+8], r13d
0x180038d2e  jz      loc_18003900B
0x180038d34  cmp     [rbx+18h], r13d
0x180038d38  jnz     short loc_180038D54
0x180038d3a  mov     dword ptr [rsp+1390h+phkResult], 8007139Fh
0x180038d42  lea     r9, aCannotReinstal; "Cannot reinstall sdb without temporary "...
0x180038d49  mov     r8d, 532h
0x180038d4f  jmp     loc_180038FFA
0x180038d54  lea     r9, [rbp+1290h+var_C70]; unsigned __int16 *
0x180038d5b  mov     rdx, r12; unsigned __int16 *
0x180038d5e  lea     r8, [rbp+1290h+pszPath]; unsigned __int16 *
0x180038d65  mov     rcx, rbx; struct _SavedSdbInfo *
0x180038d68  call    ?CopySdbToNewLocation@@YAJPEAU_SavedSdbInfo@@PEBG1PEAG_K@Z; CopySdbToNewLocation(_SavedSdbInfo *,ushort const *,ushort const *,ushort *,unsigned __int64)
0x180038d6d  test    eax, eax
0x180038d6f  js      loc_180039035
0x180038d75  mov     rdx, [rbx]; unsigned __int16 *
0x180038d78  lea     r8, [rbp+1290h+var_C70]; unsigned __int16 *
0x180038d7f  mov     rcx, [rsp+1390h+var_1328]; HKEY
0x180038d84  call    ?ReregisterSdb@@YAJPEAUHKEY__@@PEBG1@Z; ReregisterSdb(HKEY__ *,ushort const *,ushort const *)
0x180038d89  test    eax, eax
0x180038d8b  jns     short loc_180038DB4
0x180038d8d  lea     r9, aFailedToReregi_0; "Failed to reregister sdb: 0x%x"
0x180038d94  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038d98  mov     r8d, 547h
0x180038d9e  lea     rdx, aReinstallcusto; "ReinstallCustomSdbs"
0x180038da5  mov     ecx, 1
0x180038daa  call    AslLogCallPrintf
0x180038daf  jmp     loc_180039035
0x180038db4  mov     rax, [rbx]
0x180038db7  lea     r9, [rbp+1290h+Dst]
0x180038dbe  lea     r8, aLsQUGLs; "%ls -q -u -g %ls"
0x180038dc5  mov     [rsp+1390h+phkResult], rax; dwFlags
0x180038dca  mov     edx, 208h; cchDest
0x180038dcf  lea     rcx, [rbp+1290h+CommandLine]; pszDest
0x180038dd6  call    StringCchPrintfW
0x180038ddb  test    eax, eax
0x180038ddd  js      loc_18003900B
0x180038de3  mov     r9, [rbx+20h]; pszMore
0x180038de7  lea     rcx, [rbp+1290h+pszPathOut]; pszPathOut
0x180038dee  mov     r8, r12; pszPathIn
0x180038df1  call    PathCchCombineEx
0x180038df6  test    eax, eax
0x180038df8  js      loc_18003900B
0x180038dfe  lea     rax, [rbp+1290h+pszPathOut]
0x180038e05  mov     edx, 208h; cchDest
0x180038e0a  lea     r9, [rbp+1290h+Dst]
0x180038e11  mov     [rsp+1390h+phkResult], rax
0x180038e16  lea     r8, aLsQLs; "%ls -q %ls"
0x180038e1d  lea     rcx, [rbp+1290h+var_440]; pszDest
0x180038e24  call    StringCchPrintfW
0x180038e29  test    eax, eax
0x180038e2b  js      loc_18003900B
0x180038e31  xor     edx, edx; Val
0x180038e33  lea     rcx, [rbp+1290h+StartupInfo+4]; void *
0x180038e37  lea     r8d, [rdx+64h]; Size
0x180038e3b  call    memset_0
0x180038e40  xor     eax, eax
0x180038e42  mov     [rbp+1290h+StartupInfo.cb], 68h ; 'h'
0x180038e49  mov     qword ptr [rsp+1390h+ProcessInformation.dwProcessId], rax
0x180038e4e  lea     rdx, [rbp+1290h+CommandLine]; lpCommandLine
0x180038e55  lea     rax, [rsp+1390h+ProcessInformation]
0x180038e5a  xorps   xmm0, xmm0
0x180038e5d  mov     [rsp+1390h+lpProcessInformation], rax; lpProcessInformation
0x180038e62  xor     r9d, r9d; lpThreadAttributes
0x180038e65  lea     rax, [rbp+1290h+StartupInfo]
0x180038e69  xor     r8d, r8d; lpProcessAttributes
0x180038e6c  mov     [rsp+1390h+lpStartupInfo], rax; lpStartupInfo
0x180038e71  xor     ecx, ecx; lpApplicationName
0x180038e73  mov     [rsp+1390h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180038e78  mov     [rsp+1390h+lpEnvironment], r13; lpEnvironment
0x180038e7d  mov     [rsp+1390h+dwCreationFlags], 8; dwCreationFlags
0x180038e85  mov     dword ptr [rsp+1390h+phkResult], r13d; bInheritHandles
0x180038e8a  movups  xmmword ptr [rsp+1390h+ProcessInformation.hProcess], xmm0
0x180038e8f  call    cs:__imp_CreateProcessW
0x180038e95  test    eax, eax
0x180038e97  jnz     short loc_180038ED2
0x180038e99  call    cs:__imp_GetLastError
0x180038e9f  test    eax, eax
0x180038ea1  jle     short loc_180038EAD
0x180038ea3  movzx   eax, ax
0x180038ea6  or      eax, 80070000h
0x180038eab  test    eax, eax
0x180038ead  cmovns  eax, edi
0x180038eb0  lea     r9, aFailedToCreate_7; "Failed to create uninstall process: 0x%"...
0x180038eb7  mov     r8d, 576h
0x180038ebd  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038ec1  lea     rdx, aReinstallcusto; "ReinstallCustomSdbs"
0x180038ec8  mov     ecx, 1
0x180038ecd  call    AslLogCallPrintf
0x180038ed2  mov     rcx, [rsp+1390h+ProcessInformation.hProcess]; hHandle
0x180038ed7  mov     ebx, 0EA60h
0x180038edc  mov     edx, ebx; dwMilliseconds
0x180038ede  call    cs:__imp_WaitForSingleObject
0x180038ee4  test    eax, eax
0x180038ee6  jz      short loc_180038F2A
0x180038ee8  cmp     eax, 0FFFFFFFFh
0x180038eeb  jnz     short loc_180038F06
0x180038eed  call    cs:__imp_GetLastError
0x180038ef3  test    eax, eax
0x180038ef5  jle     short loc_180038F01
0x180038ef7  movzx   eax, ax
0x180038efa  or      eax, 80070000h
0x180038eff  test    eax, eax
0x180038f01  cmovns  eax, edi
0x180038f04  jmp     short loc_180038F08
0x180038f06  mov     eax, edi
0x180038f08  lea     r9, aFailedToWaitFo; "Failed to wait for uninstall process: 0"...
0x180038f0f  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038f13  mov     r8d, 584h
0x180038f19  lea     rdx, aReinstallcusto; "ReinstallCustomSdbs"
0x180038f20  mov     ecx, 1
0x180038f25  call    AslLogCallPrintf
0x180038f2a  xor     edx, edx; Val
0x180038f2c  lea     rcx, [rbp+1290h+StartupInfo+4]; void *
0x180038f30  lea     r8d, [rdx+64h]; Size
0x180038f34  call    memset_0
0x180038f39  xor     eax, eax
0x180038f3b  mov     [rbp+1290h+StartupInfo.cb], 68h ; 'h'
0x180038f42  mov     qword ptr [rsp+1390h+ProcessInformation.dwProcessId], rax
0x180038f47  lea     rdx, [rbp+1290h+var_440]; lpCommandLine
0x180038f4e  lea     rax, [rsp+1390h+ProcessInformation]
0x180038f53  xorps   xmm0, xmm0
0x180038f56  mov     [rsp+1390h+lpProcessInformation], rax; lpProcessInformation
0x180038f5b  xor     r9d, r9d; lpThreadAttributes
0x180038f5e  lea     rax, [rbp+1290h+StartupInfo]
0x180038f62  xor     r8d, r8d; lpProcessAttributes
0x180038f65  mov     [rsp+1390h+lpStartupInfo], rax; lpStartupInfo
0x180038f6a  xor     ecx, ecx; lpApplicationName
0x180038f6c  mov     [rsp+1390h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180038f71  mov     [rsp+1390h+lpEnvironment], r13; lpEnvironment
0x180038f76  mov     [rsp+1390h+dwCreationFlags], 8; dwCreationFlags
0x180038f7e  mov     dword ptr [rsp+1390h+phkResult], r13d; bInheritHandles
0x180038f83  movups  xmmword ptr [rsp+1390h+ProcessInformation.hProcess], xmm0
0x180038f88  call    cs:__imp_CreateProcessW
0x180038f8e  test    eax, eax
0x180038f90  jnz     short loc_180038FB8
0x180038f92  call    cs:__imp_GetLastError
0x180038f98  test    eax, eax
0x180038f9a  jle     short loc_180038FA6
0x180038f9c  movzx   eax, ax
0x180038f9f  or      eax, 80070000h
0x180038fa4  test    eax, eax
0x180038fa6  cmovns  eax, edi
0x180038fa9  lea     r9, aFailedToCreate_2; "Failed to create install process: 0x%x"
0x180038fb0  mov     r8d, 59Ch
0x180038fb6  jmp     short loc_180038FF6
0x180038fb8  mov     rcx, [rsp+1390h+ProcessInformation.hProcess]; hHandle
0x180038fbd  mov     edx, ebx; dwMilliseconds
0x180038fbf  call    cs:__imp_WaitForSingleObject
0x180038fc5  test    eax, eax
0x180038fc7  jz      short loc_18003900B
0x180038fc9  cmp     eax, 0FFFFFFFFh
0x180038fcc  jnz     short loc_180038FE7
0x180038fce  call    cs:__imp_GetLastError
0x180038fd4  test    eax, eax
0x180038fd6  jle     short loc_180038FE2
0x180038fd8  movzx   eax, ax
0x180038fdb  or      eax, 80070000h
0x180038fe0  test    eax, eax
0x180038fe2  cmovns  eax, edi
0x180038fe5  jmp     short loc_180038FE9
0x180038fe7  mov     eax, edi
0x180038fe9  lea     r9, aFailedToWaitFo_0; "Failed to wait for install process: 0x%"...
0x180038ff0  mov     r8d, 5ABh
0x180038ff6  mov     dword ptr [rsp+1390h+phkResult], eax
0x180038ffa  lea     rdx, aReinstallcusto; "ReinstallCustomSdbs"
0x180039001  mov     ecx, 1
0x180039006  call    AslLogCallPrintf
0x18003900b  mov     rcx, [rsp+1390h+ProcessInformation.hProcess]; hObject
0x180039010  test    rcx, rcx
0x180039013  jz      short loc_180039020
0x180039015  call    cs:__imp_CloseHandle
0x18003901b  mov     [rsp+1390h+ProcessInformation.hProcess], r13
0x180039020  mov     rcx, [rsp+1390h+ProcessInformation.hThread]; hObject
0x180039025  test    rcx, rcx
0x180039028  jz      short loc_180039035
0x18003902a  call    cs:__imp_CloseHandle
0x180039030  mov     [rsp+1390h+ProcessInformation.hThread], r13
0x180039035  mov     rax, [r15+10h]
0x180039039  inc     r14
0x18003903c  cmp     r14, rax
0x18003903f  jb      loc_180038CF3
0x180039045  mov     ebx, r13d
0x180039048  jmp     short loc_1800390A2
0x18003904a  call    cs:__imp_GetLastError
0x180039050  mov     ebx, eax
0x180039052  test    eax, eax
0x180039054  jle     short loc_18003905F
0x180039056  movzx   ebx, ax
0x180039059  or      ebx, 80070000h
0x18003905f  test    ebx, ebx
0x180039061  mov     edi, 80004005h
0x180039066  cmovns  ebx, edi
0x180039069  jmp     short loc_1800390A2
0x18003906b  jle     short loc_180039076
0x18003906d  movzx   ebx, ax
0x180039070  or      ebx, 80070000h
0x180039076  test    ebx, ebx
0x180039078  lea     r9, aFailedToOpenIn_0; "Failed to open installed sdb key: 0x%x"
0x18003907f  mov     edi, 80004005h
0x180039084  mov     r8d, 508h
0x18003908a  cmovns  ebx, edi
0x18003908d  mov     dword ptr [rsp+1390h+phkResult], ebx
  ... truncated ...
```
