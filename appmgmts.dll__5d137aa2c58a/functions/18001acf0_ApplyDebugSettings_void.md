# ApplyDebugSettings(void)

- ea: `0x18001acf0`
- end: `0x18001af39`
- name: `?ApplyDebugSettings@@YAXXZ`
- size: `585`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001b1a0`

## callees

- `0x1800016d0`
- `0x18001acf0`
- `0x18001af40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aec2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001aec2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ad82`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001ad82`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001adc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae43`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001adc8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae0d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001ae43`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ae4e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001ae4e`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001aeff`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001aeff`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001aeb8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesExW` at `0x18001aeb8`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001aeeb`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18001aeeb`
- `KERNEL32!MoveFileW` at `0x18001af11`
- `KERNEL32!MoveFileW` at `0x18001af11`

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
0x18001acf0  push    rbp
0x18001acf2  lea     rbp, [rsp-3A0h]
0x18001acfa  sub     rsp, 4A0h
0x18001ad01  mov     rax, cs:__security_cookie
0x18001ad08  xor     rax, rsp
0x18001ad0b  mov     [rbp+3A0h+var_10], rax
0x18001ad12  cmp     cs:?gDebugEnabled@@3KA, 1; ulong gDebugEnabled
0x18001ad19  mov     [rsp+4A0h+hKey], 0
0x18001ad22  mov     [rsp+4A0h+cbData], 0
0x18001ad2a  mov     [rsp+4A0h+Type], 0
0x18001ad32  mov     dword ptr [rsp+4A0h+Data], 0
0x18001ad3a  jnz     loc_18001AF21
0x18001ad40  cmp     cs:?gDebugInitialized@@3KA, 0; ulong gDebugInitialized
0x18001ad47  jnz     loc_18001AF21
0x18001ad4d  lea     rax, [rsp+4A0h+hKey]
0x18001ad52  mov     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x18001ad5c  mov     r9d, 20019h; samDesired
0x18001ad62  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18001ad67  xor     r8d, r8d; ulOptions
0x18001ad6a  mov     cs:?gDebugBreak@@3KA, 0; ulong gDebugBreak
0x18001ad74  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x18001ad7b  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001ad82  call    cs:__imp_RegOpenKeyExW
0x18001ad88  mov     dword ptr [rsp+4A0h+Data], 0
0x18001ad90  test    eax, eax
0x18001ad92  jnz     loc_18001AE6C
0x18001ad98  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001ad9d  lea     rax, [rsp+4A0h+cbData]
0x18001ada2  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18001ada7  lea     r9, [rsp+4A0h+Type]; lpType
0x18001adac  lea     rax, [rsp+4A0h+Data]
0x18001adb1  mov     [rsp+4A0h+cbData], 4
0x18001adb9  xor     r8d, r8d; lpReserved
0x18001adbc  mov     [rsp+4A0h+phkResult], rax; lpData
0x18001adc1  lea     rdx, aRundiagnosticl; "RunDiagnosticLoggingApplicationManageme"...
0x18001adc8  call    cs:__imp_RegQueryValueExW
0x18001adce  test    eax, eax
0x18001add0  jnz     short loc_18001ADDD
0x18001add2  cmp     [rsp+4A0h+Type], 4
0x18001add7  jz      short loc_18001ADDD
0x18001add9  mov     dword ptr [rsp+4A0h+Data], eax
0x18001addd  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001ade2  lea     rax, [rsp+4A0h+cbData]
0x18001ade7  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18001adec  lea     rdx, aAppmgmtdebugle; "AppMgmtDebugLevel"
0x18001adf3  lea     rax, ?gDebugLevel@@3KA; ulong gDebugLevel
0x18001adfa  mov     [rsp+4A0h+cbData], 4
0x18001ae02  xor     r9d, r9d; lpType
0x18001ae05  mov     [rsp+4A0h+phkResult], rax; lpData
0x18001ae0a  xor     r8d, r8d; lpReserved
0x18001ae0d  call    cs:__imp_RegQueryValueExW
0x18001ae13  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001ae18  lea     rax, [rsp+4A0h+cbData]
0x18001ae1d  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18001ae22  lea     rdx, aAppmgmtdebugbr; "AppMgmtDebugBreak"
0x18001ae29  lea     rax, ?gDebugBreak@@3KA; ulong gDebugBreak
0x18001ae30  mov     [rsp+4A0h+cbData], 4
0x18001ae38  xor     r9d, r9d; lpType
0x18001ae3b  mov     [rsp+4A0h+phkResult], rax; lpData
0x18001ae40  xor     r8d, r8d; lpReserved
0x18001ae43  call    cs:__imp_RegQueryValueExW
0x18001ae49  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18001ae4e  call    cs:__imp_RegCloseKey
0x18001ae54  cmp     dword ptr [rsp+4A0h+Data], 0
0x18001ae59  jz      short loc_18001AE6C
0x18001ae5b  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001ae61  or      eax, 6
0x18001ae64  mov     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x18001ae6a  jmp     short loc_18001AE72
0x18001ae6c  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x18001ae72  test    al, 8
0x18001ae74  jz      loc_18001AF17
0x18001ae7a  xorps   xmm0, xmm0
0x18001ae7d  lea     rcx, [rbp+3A0h+FileName]; lpDst
0x18001ae84  xor     eax, eax
0x18001ae86  movups  [rsp+4A0h+FileInformation], xmm0
0x18001ae8b  mov     [rsp+4A0h+var_438], eax
0x18001ae8f  movups  [rsp+4A0h+var_448], xmm0
0x18001ae94  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x18001ae99  test    eax, eax
0x18001ae9b  jz      loc_18001AF21
0x18001aea1  cmp     cs:?gDebugRequestedMode@@3KA, 1; ulong gDebugRequestedMode
0x18001aea8  jnz     short loc_18001AF21
0x18001aeaa  lea     r8, [rsp+4A0h+FileInformation]; lpFileInformation
0x18001aeaf  xor     edx, edx; fInfoLevelId
0x18001aeb1  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x18001aeb8  call    cs:__imp_GetFileAttributesExW
0x18001aebe  test    eax, eax
0x18001aec0  jnz     short loc_18001AECF
0x18001aec2  call    cs:__imp_GetLastError
0x18001aec8  cmp     eax, 2
0x18001aecb  jz      short loc_18001AF17
0x18001aecd  jmp     short loc_18001AF21
0x18001aecf  cmp     [rsp+4A0h+var_438], 19000h
0x18001aed7  jb      short loc_18001AF17
0x18001aed9  mov     r8d, 104h; nSize
0x18001aedf  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x18001aee4  lea     rcx, aSystemrootDebu; "%SystemRoot%\\Debug\\UserMode\\appmgmt."...
0x18001aeeb  call    cs:__imp_ExpandEnvironmentStringsW
0x18001aef1  dec     eax
0x18001aef3  cmp     eax, 103h
0x18001aef8  ja      short loc_18001AF17
0x18001aefa  lea     rcx, [rsp+4A0h+Dst]; lpFileName
0x18001aeff  call    cs:__imp_DeleteFileW
0x18001af05  lea     rdx, [rsp+4A0h+Dst]; lpNewFileName
0x18001af0a  lea     rcx, [rbp+3A0h+FileName]; lpExistingFileName
0x18001af11  call    cs:__imp_MoveFileW
0x18001af17  mov     cs:?gDebugInitialized@@3KA, 1; ulong gDebugInitialized
0x18001af21  mov     rcx, [rbp+3A0h+var_10]
0x18001af28  xor     rcx, rsp; StackCookie
0x18001af2b  call    __security_check_cookie
0x18001af30  add     rsp, 4A0h
0x18001af37  pop     rbp
0x18001af38  retn
```
