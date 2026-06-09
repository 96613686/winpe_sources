# RecLoadKey(ushort const *,HKEY__ *,ushort const *,ulong,int,HKEY__ * *)

- ea: `0x18003fc08`
- end: `0x18003feb8`
- name: `?RecLoadKey@@YAHPEBGPEAUHKEY__@@0KHPEAPEAU1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(const char *lpFile, HKEY, const unsigned __int16 *, __int64, int, HKEY *phkResult)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18003fec0`

## callees

- `0x180009e04`
- `0x18003aa28`
- `0x18003fc08`
- `0x1800401c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fe26`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18003fe26`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18003fd6c`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x18003fd6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fd7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fe3c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fd7a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003fe3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fc3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fcec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fd80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003fe42`
- `WDSCORE!CurrentIP` at `0x18003fc47`
- `WDSCORE!CurrentIP` at `0x18003fcf4`
- `WDSCORE!CurrentIP` at `0x18003fd88`
- `WDSCORE!CurrentIP` at `0x18003fe4a`
- `WDSCORE!CurrentIP` at `0x18003fc47`
- `WDSCORE!CurrentIP` at `0x18003fcf4`
- `WDSCORE!CurrentIP` at `0x18003fd88`
- `WDSCORE!CurrentIP` at `0x18003fe4a`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fca6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fd56`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fca6`
- `WDSCORE!WdsSetupLogMessageW` at `0x18003fd56`

## string_xrefs

- `0x18003fd98`: `RegLoadKeyW failed to mount %s at %s. Error %d`
- `0x18003fe53`: `RegOpenKeyExW failed to open %s`

## pseudocode

```c
__int64 __fastcall RecLoadKey(
        const char *lpFile,
        HKEY a2,
        const unsigned __int16 *a3,
        __int64 a4,
        int a5,
        HKEY *phkResult)
{
  DWORD LastError; // edi
  __int64 v9; // rbx
  struct tagLOG_PARTIAL_MSG *v10; // rax
  HKEY v11; // rcx
  signed int v12; // eax
  bool v13; // sf
  signed int v14; // eax
  unsigned int v15; // esi
  DWORD v16; // edi
  __int64 v17; // rbx
  struct tagLOG_PARTIAL_MSG *v18; // rax
  LSTATUS KeyW; // eax
  LSTATUS v21; // ebp
  DWORD v22; // edi
  __int64 v23; // rbx
  struct tagLOG_PARTIAL_MSG *v24; // rax
  HKEY v25; // rcx
  LSTATUS Key; // ebx
  DWORD v27; // edi
  __int64 v28; // rbx
  struct tagLOG_PARTIAL_MSG *v29; // rax

  if ( (unsigned int)RegExists(-2147483646, a3, 0) )
  {
    LastError = GetLastError();
    v9 = CurrentIP();
    v10 = ConstructPartialMsgW(
            50331648,
            "RecLoadKey: Found previously loaded hive [%s], possibly from ungraceful exit. Unloading it",
            lpFile);
    WdsSetupLogMessageW(
      v10,
      0,
      L"D",
      0,
      556,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecLoadKey",
      v9,
      LastError,
      0,
      0);
    if ( !(unsigned int)RecUnloadKey(v11, a3) )
    {
      v12 = GetLastError();
      v13 = v12 < 0;
      if ( v12 > 0 )
        v13 = 1;
      if ( v13 )
      {
        v14 = GetLastError();
        v15 = v14;
        if ( v14 > 0 )
          v15 = (unsigned __int16)v14 | 0x80070000;
      }
      else
      {
        v15 = -2147467259;
      }
      v16 = GetLastError();
      v17 = CurrentIP();
      v18 = ConstructPartialMsgW(0x2000000, "RecLoadKey: Failed to unload hive [%s]. Error: 0x%08X", lpFile, v15);
      WdsSetupLogMessageW(
        v18,
        0,
        L"D",
        0,
        560,
        L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
        L"RecLoadKey",
        v17,
        v16,
        0,
        0);
      return 0;
    }
  }
  KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, a3, (LPCWSTR)lpFile);
  v21 = KeyW;
  if ( KeyW )
  {
    SetLastError(KeyW);
    v22 = GetLastError();
    v23 = CurrentIP();
    v24 = ConstructPartialMsgW(
            0x2000000,
            "RegLoadKeyW failed to mount %s at %s. Error %d",
            lpFile,
            (const char *)a3,
            v21);
    WdsSetupLogMessageW(
      v24,
      0,
      L"D",
      0,
      569,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecLoadKey",
      v23,
      v22,
      0,
      0);
    return 0;
  }
  Key = RegCreateKeyExW(HKEY_LOCAL_MACHINE, a3, 0, 0, 4u, 0x3001Fu, 0, phkResult, 0);
  if ( Key )
  {
    RecUnloadKey(v25, a3);
    SetLastError(Key);
    v27 = GetLastError();
    v28 = CurrentIP();
    v29 = ConstructPartialMsgW(0x2000000, "RegOpenKeyExW failed to open %s", (const char *)a3);
    WdsSetupLogMessageW(
      v29,
      0,
      L"D",
      0,
      579,
      L"base\\diagnosis\\srt\\srinfra\\recutil\\reg.cpp",
      L"RecLoadKey",
      v28,
      v27,
      0,
      0);
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x18003fc08  push    rbx
0x18003fc0a  push    rbp
0x18003fc0b  push    rsi
0x18003fc0c  push    rdi
0x18003fc0d  push    r12
0x18003fc0f  push    r14
0x18003fc11  sub     rsp, 68h
0x18003fc15  mov     rsi, r8
0x18003fc18  mov     r14, rcx
0x18003fc1b  mov     r12, 0FFFFFFFF80000002h
0x18003fc22  mov     rdx, rsi
0x18003fc25  mov     rcx, r12
0x18003fc28  xor     r8d, r8d
0x18003fc2b  call    RegExists
0x18003fc30  lea     rbp, aRecloadkey; "RecLoadKey"
0x18003fc37  test    eax, eax
0x18003fc39  jz      loc_18003FD63
0x18003fc3f  call    cs:__imp_GetLastError
0x18003fc45  mov     edi, eax
0x18003fc47  call    cs:__imp_CurrentIP
0x18003fc4d  mov     r8, r14
0x18003fc50  lea     rdx, aRecloadkeyFoun; "RecLoadKey: Found previously loaded hiv"...
0x18003fc57  mov     ecx, 3000000h; unsigned int
0x18003fc5c  mov     rbx, rax
0x18003fc5f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fc64  mov     [rsp+98h+var_48], 0
0x18003fc6c  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003fc73  mov     [rsp+98h+var_50], 0
0x18003fc7c  lea     r8, aD; "D"
0x18003fc83  mov     dword ptr [rsp+98h+lpdwDisposition], edi
0x18003fc87  xor     r9d, r9d
0x18003fc8a  mov     [rsp+98h+phkResult], rbx
0x18003fc8f  xor     edx, edx
0x18003fc91  mov     [rsp+98h+lpSecurityAttributes], rbp
0x18003fc96  mov     qword ptr [rsp+98h+samDesired], rcx
0x18003fc9b  mov     rcx, rax
0x18003fc9e  mov     [rsp+98h+dwOptions], 22Ch
0x18003fca6  call    cs:__imp_WdsSetupLogMessageW
0x18003fcac  mov     rdx, rsi; unsigned __int16 *
0x18003fcaf  call    ?RecUnloadKey@@YAHPEAUHKEY__@@PEBG@Z; RecUnloadKey(HKEY__ *,ushort const *)
0x18003fcb4  test    eax, eax
0x18003fcb6  jnz     loc_18003FD63
0x18003fcbc  call    cs:__imp_GetLastError
0x18003fcc2  mov     ebx, 80070000h
0x18003fcc7  test    eax, eax
0x18003fcc9  jle     short loc_18003FCD2
0x18003fccb  movzx   eax, ax
0x18003fcce  or      eax, ebx
0x18003fcd0  test    eax, eax
0x18003fcd2  jns     short loc_18003FCE7
0x18003fcd4  call    cs:__imp_GetLastError
0x18003fcda  mov     esi, eax
0x18003fcdc  test    eax, eax
0x18003fcde  jle     short loc_18003FCEC
0x18003fce0  movzx   esi, ax
0x18003fce3  or      esi, ebx
0x18003fce5  jmp     short loc_18003FCEC
0x18003fce7  mov     esi, 80004005h
0x18003fcec  call    cs:__imp_GetLastError
0x18003fcf2  mov     edi, eax
0x18003fcf4  call    cs:__imp_CurrentIP
0x18003fcfa  mov     r9d, esi
0x18003fcfd  lea     rdx, aRecloadkeyFail; "RecLoadKey: Failed to unload hive [%s]."...
0x18003fd04  mov     r8, r14
0x18003fd07  mov     ecx, 2000000h; unsigned int
0x18003fd0c  mov     rbx, rax
0x18003fd0f  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fd14  mov     [rsp+98h+var_48], 0
0x18003fd1c  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003fd23  mov     [rsp+98h+var_50], 0
0x18003fd2c  mov     dword ptr [rsp+98h+lpdwDisposition], edi
0x18003fd30  mov     [rsp+98h+phkResult], rbx
0x18003fd35  mov     [rsp+98h+lpSecurityAttributes], rbp
0x18003fd3a  mov     qword ptr [rsp+98h+samDesired], rcx
0x18003fd3f  mov     [rsp+98h+dwOptions], 230h
0x18003fd47  xor     r9d, r9d
0x18003fd4a  lea     r8, aD; "D"
0x18003fd51  xor     edx, edx
0x18003fd53  mov     rcx, rax
0x18003fd56  call    cs:__imp_WdsSetupLogMessageW
0x18003fd5c  xor     eax, eax
0x18003fd5e  jmp     loc_18003FEAB
0x18003fd63  mov     r8, r14; lpFile
0x18003fd66  mov     rdx, rsi; lpSubKey
0x18003fd69  mov     rcx, r12; hKey
0x18003fd6c  call    cs:__imp_RegLoadKeyW
0x18003fd72  mov     ebp, eax
0x18003fd74  test    eax, eax
0x18003fd76  jz      short loc_18003FDEB
0x18003fd78  mov     ecx, eax; dwErrCode
0x18003fd7a  call    cs:__imp_SetLastError
0x18003fd80  call    cs:__imp_GetLastError
0x18003fd86  mov     edi, eax
0x18003fd88  call    cs:__imp_CurrentIP
0x18003fd8e  mov     r9, rsi
0x18003fd91  mov     [rsp+98h+dwOptions], ebp
0x18003fd95  mov     r8, r14
0x18003fd98  lea     rdx, aRegloadkeywFai; "RegLoadKeyW failed to mount %s at %s. E"...
0x18003fd9f  mov     ecx, 2000000h; unsigned int
0x18003fda4  mov     rbx, rax
0x18003fda7  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fdac  mov     [rsp+98h+var_48], 0
0x18003fdb4  lea     rcx, aRecloadkey; "RecLoadKey"
0x18003fdbb  mov     [rsp+98h+var_50], 0
0x18003fdc4  mov     dword ptr [rsp+98h+lpdwDisposition], edi
0x18003fdc8  mov     [rsp+98h+phkResult], rbx
0x18003fdcd  mov     [rsp+98h+lpSecurityAttributes], rcx
0x18003fdd2  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003fdd9  mov     qword ptr [rsp+98h+samDesired], rcx
0x18003fdde  mov     [rsp+98h+dwOptions], 239h
0x18003fde6  jmp     loc_18003FD47
0x18003fdeb  mov     rax, [rsp+98h+arg_28]
0x18003fdf3  xor     r9d, r9d; lpClass
0x18003fdf6  mov     [rsp+98h+lpdwDisposition], 0; lpdwDisposition
0x18003fdff  xor     r8d, r8d; Reserved
0x18003fe02  mov     [rsp+98h+phkResult], rax; phkResult
0x18003fe07  mov     rdx, rsi; lpSubKey
0x18003fe0a  mov     [rsp+98h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003fe13  mov     rcx, r12; hKey
0x18003fe16  mov     [rsp+98h+samDesired], 3001Fh; samDesired
0x18003fe1e  mov     [rsp+98h+dwOptions], 4; dwOptions
0x18003fe26  call    cs:__imp_RegCreateKeyExW
0x18003fe2c  mov     ebx, eax
0x18003fe2e  test    eax, eax
0x18003fe30  jz      short loc_18003FEA6
0x18003fe32  mov     rdx, rsi; unsigned __int16 *
0x18003fe35  call    ?RecUnloadKey@@YAHPEAUHKEY__@@PEBG@Z; RecUnloadKey(HKEY__ *,ushort const *)
0x18003fe3a  mov     ecx, ebx; dwErrCode
0x18003fe3c  call    cs:__imp_SetLastError
0x18003fe42  call    cs:__imp_GetLastError
0x18003fe48  mov     edi, eax
0x18003fe4a  call    cs:__imp_CurrentIP
0x18003fe50  mov     r8, rsi
0x18003fe53  lea     rdx, aRegopenkeyexwF; "RegOpenKeyExW failed to open %s"
0x18003fe5a  mov     ecx, 2000000h; unsigned int
0x18003fe5f  mov     rbx, rax
0x18003fe62  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18003fe67  mov     [rsp+98h+var_48], 0
0x18003fe6f  lea     rcx, aRecloadkey; "RecLoadKey"
0x18003fe76  mov     [rsp+98h+var_50], 0
0x18003fe7f  mov     dword ptr [rsp+98h+lpdwDisposition], edi
0x18003fe83  mov     [rsp+98h+phkResult], rbx
0x18003fe88  mov     [rsp+98h+lpSecurityAttributes], rcx
0x18003fe8d  lea     rcx, aBaseDiagnosisS_2; "base\\diagnosis\\srt\\srinfra\\recutil"...
0x18003fe94  mov     qword ptr [rsp+98h+samDesired], rcx
0x18003fe99  mov     [rsp+98h+dwOptions], 243h
0x18003fea1  jmp     loc_18003FD47
0x18003fea6  mov     eax, 1
0x18003feab  add     rsp, 68h
0x18003feaf  pop     r14
0x18003feb1  pop     r12
0x18003feb3  pop     rdi
0x18003feb4  pop     rsi
0x18003feb5  pop     rbp
0x18003feb6  pop     rbx
0x18003feb7  retn
```
