# ApplyDebugSettings(void)

- ea: `0x180043b4c`
- end: `0x180043d95`
- name: `?ApplyDebugSettings@@YAXXZ`
- size: `585`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180044814`

## callees

- `0x180043b4c`
- `0x180043dc8`
- `0x180065090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c9f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c24`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c69`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180043c9f`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043bde`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043bde`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043caa`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180043caa`
- `KERNEL32!GetLastError` at `0x180043d1e`
- `KERNEL32!GetLastError` at `0x180043d1e`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180043d47`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180043d47`
- `KERNEL32!GetFileAttributesExW` at `0x180043d14`
- `KERNEL32!GetFileAttributesExW` at `0x180043d14`
- `KERNEL32!DeleteFileW` at `0x180043d5b`
- `KERNEL32!DeleteFileW` at `0x180043d5b`
- `KERNEL32!MoveFileW` at `0x180043d6d`
- `KERNEL32!MoveFileW` at `0x180043d6d`

## pseudocode

```c
void ApplyDebugSettings(void)
{
  int v0; // edx
  BYTE v1; // al
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  DWORD Type; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _OWORD FileInformation[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v7; // [rsp+68h] [rbp-98h]
  WCHAR Dst[264]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR FileName[264]; // [rsp+280h] [rbp+180h] BYREF

  hKey = 0;
  cbData = 0;
  Type = 0;
  *(_DWORD *)Data = 0;
  if ( gDebugEnabled == 1 && !gDebugInitialized )
  {
    *(_DWORD *)&gDebugLevel = 0;
    *(_DWORD *)&gDebugBreak = 0;
    *(_DWORD *)Data = 0;
    if ( RegOpenKeyExW(
           HKEY_LOCAL_MACHINE,
           L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Diagnostics",
           0,
           0x20019u,
           &hKey) )
    {
      goto LABEL_9;
    }
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"RunDiagnosticLoggingApplicationManagement", 0, &Type, Data, &cbData) && Type != 4 )
      *(_DWORD *)Data = 0;
    cbData = 4;
    RegQueryValueExW(hKey, L"AppMgmtDebugLevel", 0, 0, &gDebugLevel, &cbData);
    cbData = 4;
    RegQueryValueExW(hKey, L"AppMgmtDebugBreak", 0, 0, &gDebugBreak, &cbData);
    RegCloseKey(hKey);
    if ( !*(_DWORD *)Data )
    {
LABEL_9:
      v1 = gDebugLevel;
    }
    else
    {
      v1 = gDebugLevel | 6;
      *(_DWORD *)&gDebugLevel |= 6u;
    }
    if ( (v1 & 8) == 0 )
      goto LABEL_19;
    memset(FileInformation, 0, sizeof(FileInformation));
    v7 = 0;
    if ( (unsigned int)GetDebugLogFileName(FileName, v0) && gDebugRequestedMode == 1 )
    {
      if ( GetFileAttributesExW(FileName, GetFileExInfoStandard, FileInformation) )
      {
        if ( v7 >= 0x19000
          && ExpandEnvironmentStringsW(L"%SystemRoot%\\Debug\\UserMode\\appmgmt.bak", Dst, 0x104u) - 1 <= 0x103 )
        {
          DeleteFileW(Dst);
          MoveFileW(FileName, Dst);
        }
      }
      else if ( GetLastError() != 2 )
      {
        return;
      }
LABEL_19:
      gDebugInitialized = 1;
    }
  }
}

```

## disassembly

```asm
0x180043b4c  push    rbp
0x180043b4e  lea     rbp, [rsp-3A0h]
0x180043b56  sub     rsp, 4A0h
0x180043b5d  mov     rax, cs:__security_cookie
0x180043b64  xor     rax, rsp
0x180043b67  mov     [rbp+3A0h+var_10], rax
0x180043b6e  cmp     cs:?gDebugEnabled@@3KA, 1; ulong gDebugEnabled
0x180043b75  mov     [rsp+4A0h+hKey], 0
0x180043b7e  mov     [rsp+4A0h+cbData], 0
0x180043b86  mov     [rsp+4A0h+Type], 0
0x180043b8e  mov     dword ptr [rsp+4A0h+Data], 0
0x180043b96  jnz     loc_180043D7D
0x180043b9c  cmp     cs:?gDebugInitialized@@3KA, 0; ulong gDebugInitialized
0x180043ba3  jnz     loc_180043D7D
0x180043ba9  lea     rax, [rsp+4A0h+hKey]
0x180043bae  mov     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180043bb8  mov     r9d, 20019h; samDesired
0x180043bbe  mov     [rsp+4A0h+phkResult], rax; phkResult
0x180043bc3  xor     r8d, r8d; ulOptions
0x180043bc6  mov     cs:?gDebugBreak@@3KA, 0; ulong gDebugBreak
0x180043bd0  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180043bd7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180043bde  call    cs:__imp_RegOpenKeyExW
0x180043be4  mov     dword ptr [rsp+4A0h+Data], 0
0x180043bec  test    eax, eax
0x180043bee  jnz     loc_180043CC8
0x180043bf4  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180043bf9  lea     rax, [rsp+4A0h+cbData]
0x180043bfe  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180043c03  lea     r9, [rsp+4A0h+Type]; lpType
0x180043c08  lea     rax, [rsp+4A0h+Data]
0x180043c0d  mov     [rsp+4A0h+cbData], 4
0x180043c15  xor     r8d, r8d; lpReserved
0x180043c18  mov     [rsp+4A0h+phkResult], rax; lpData
0x180043c1d  lea     rdx, aRundiagnosticl; "RunDiagnosticLoggingApplicationManageme"...
0x180043c24  call    cs:__imp_RegQueryValueExW
0x180043c2a  test    eax, eax
0x180043c2c  jnz     short loc_180043C39
0x180043c2e  cmp     [rsp+4A0h+Type], 4
0x180043c33  jz      short loc_180043C39
0x180043c35  mov     dword ptr [rsp+4A0h+Data], eax
0x180043c39  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180043c3e  lea     rax, [rsp+4A0h+cbData]
0x180043c43  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180043c48  lea     rdx, aAppmgmtdebugle; "AppMgmtDebugLevel"
0x180043c4f  lea     rax, ?gDebugLevel@@3KA; ulong gDebugLevel
0x180043c56  mov     [rsp+4A0h+cbData], 4
0x180043c5e  xor     r9d, r9d; lpType
0x180043c61  mov     [rsp+4A0h+phkResult], rax; lpData
0x180043c66  xor     r8d, r8d; lpReserved
0x180043c69  call    cs:__imp_RegQueryValueExW
0x180043c6f  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180043c74  lea     rax, [rsp+4A0h+cbData]
0x180043c79  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180043c7e  lea     rdx, aAppmgmtdebugbr; "AppMgmtDebugBreak"
0x180043c85  lea     rax, ?gDebugBreak@@3KA; ulong gDebugBreak
0x180043c8c  mov     [rsp+4A0h+cbData], 4
0x180043c94  xor     r9d, r9d; lpType
0x180043c97  mov     [rsp+4A0h+phkResult], rax; lpData
0x180043c9c  xor     r8d, r8d; lpReserved
0x180043c9f  call    cs:__imp_RegQueryValueExW
0x180043ca5  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180043caa  call    cs:__imp_RegCloseKey
0x180043cb0  cmp     dword ptr [rsp+4A0h+Data], 0
0x180043cb5  jz      short loc_180043CC8
0x180043cb7  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180043cbd  or      eax, 6
0x180043cc0  mov     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180043cc6  jmp     short loc_180043CCE
0x180043cc8  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180043cce  test    al, 8
0x180043cd0  jz      loc_180043D73
0x180043cd6  xorps   xmm0, xmm0
0x180043cd9  lea     rcx, [rbp+3A0h+FileName]; lpDst
0x180043ce0  xor     eax, eax
0x180043ce2  movups  [rsp+4A0h+FileInformation], xmm0
0x180043ce7  mov     [rsp+4A0h+var_438], eax
0x180043ceb  movups  [rsp+4A0h+var_448], xmm0
0x180043cf0  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x180043cf5  test    eax, eax
0x180043cf7  jz      loc_180043D7D
0x180043cfd  cmp     cs:?gDebugRequestedMode@@3KA, 1; ulong gDebugRequestedMode
0x180043d04  jnz     short loc_180043D7D
0x180043d06  lea     r8, [rsp+4A0h+FileInformation]; lpFileInformation
0x180043d0b  xor     edx, edx; fInfoLevelId
0x180043d0d  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x180043d14  call    cs:__imp_GetFileAttributesExW
0x180043d1a  test    eax, eax
0x180043d1c  jnz     short loc_180043D2B
0x180043d1e  call    cs:__imp_GetLastError
0x180043d24  cmp     eax, 2
0x180043d27  jz      short loc_180043D73
0x180043d29  jmp     short loc_180043D7D
0x180043d2b  cmp     [rsp+4A0h+var_438], 19000h
0x180043d33  jb      short loc_180043D73
0x180043d35  mov     r8d, 104h; nSize
0x180043d3b  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x180043d40  lea     rcx, aSystemrootDebu; "%SystemRoot%\\Debug\\UserMode\\appmgmt."...
0x180043d47  call    cs:__imp_ExpandEnvironmentStringsW
0x180043d4d  dec     eax
0x180043d4f  cmp     eax, 103h
0x180043d54  ja      short loc_180043D73
0x180043d56  lea     rcx, [rsp+4A0h+Dst]; lpFileName
0x180043d5b  call    cs:__imp_DeleteFileW
0x180043d61  lea     rdx, [rsp+4A0h+Dst]; lpNewFileName
0x180043d66  lea     rcx, [rbp+3A0h+FileName]; lpExistingFileName
0x180043d6d  call    cs:__imp_MoveFileW
0x180043d73  mov     cs:?gDebugInitialized@@3KA, 1; ulong gDebugInitialized
0x180043d7d  mov     rcx, [rbp+3A0h+var_10]
0x180043d84  xor     rcx, rsp; StackCookie
0x180043d87  call    __security_check_cookie
0x180043d8c  add     rsp, 4A0h
0x180043d93  pop     rbp
0x180043d94  retn
```
