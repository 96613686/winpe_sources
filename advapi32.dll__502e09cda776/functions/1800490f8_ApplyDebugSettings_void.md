# ApplyDebugSettings(void)

- ea: `0x1800490f8`
- end: `0x180049382`
- name: `?ApplyDebugSettings@@YAXXZ`
- size: `650`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180049e60`

## callees

- `0x1800490f8`
- `0x1800493b4`
- `0x1800720b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800491d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049221`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004925d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800491d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180049221`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18004925d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004918a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004918a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004926e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18004926e`
- `KERNEL32!GetLastError` at `0x1800492f2`
- `KERNEL32!GetLastError` at `0x1800492f2`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180049321`
- `KERNEL32!ExpandEnvironmentStringsW` at `0x180049321`
- `KERNEL32!GetFileAttributesExW` at `0x1800492e2`
- `KERNEL32!GetFileAttributesExW` at `0x1800492e2`
- `KERNEL32!DeleteFileW` at `0x18004933b`
- `KERNEL32!DeleteFileW` at `0x18004933b`
- `KERNEL32!MoveFileW` at `0x180049353`
- `KERNEL32!MoveFileW` at `0x180049353`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800490f8  push    rbp
0x1800490fa  lea     rbp, [rsp-3A0h]
0x180049102  sub     rsp, 4A0h
0x180049109  mov     rax, cs:__security_cookie
0x180049110  xor     rax, rsp
0x180049113  mov     [rbp+3A0h+var_10], rax
0x18004911a  cmp     cs:?gDebugEnabled@@3KA, 1; ulong gDebugEnabled
0x180049121  mov     [rsp+4A0h+hKey], 0
0x18004912a  mov     [rsp+4A0h+cbData], 0
0x180049132  mov     [rsp+4A0h+Type], 0
0x18004913a  mov     dword ptr [rsp+4A0h+Data], 0
0x180049142  jnz     loc_180049369
0x180049148  cmp     cs:?gDebugInitialized@@3KA, 0; ulong gDebugInitialized
0x18004914f  jnz     loc_180049369
0x180049155  lea     rax, [rsp+4A0h+hKey]
0x18004915a  mov     cs:?gDebugLevel@@3KA, 0; ulong gDebugLevel
0x180049164  mov     r9d, 20019h; samDesired
0x18004916a  mov     [rsp+4A0h+phkResult], rax; phkResult
0x18004916f  xor     r8d, r8d; ulOptions
0x180049172  mov     cs:?gDebugBreak@@3KA, 0; ulong gDebugBreak
0x18004917c  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows NT\\Curren"...
0x180049183  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18004918a  call    cs:__imp_RegOpenKeyExW
0x180049191  nop     dword ptr [rax+rax+00h]
0x180049196  mov     dword ptr [rsp+4A0h+Data], 0
0x18004919e  test    eax, eax
0x1800491a0  jnz     loc_180049292
0x1800491a6  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800491ab  lea     rax, [rsp+4A0h+cbData]
0x1800491b0  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x1800491b5  lea     r9, [rsp+4A0h+Type]; lpType
0x1800491ba  lea     rax, [rsp+4A0h+Data]
0x1800491bf  mov     [rsp+4A0h+cbData], 4
0x1800491c7  xor     r8d, r8d; lpReserved
0x1800491ca  mov     [rsp+4A0h+phkResult], rax; lpData
0x1800491cf  lea     rdx, aRundiagnosticl; "RunDiagnosticLoggingApplicationManageme"...
0x1800491d6  call    cs:__imp_RegQueryValueExW
0x1800491dd  nop     dword ptr [rax+rax+00h]
0x1800491e2  test    eax, eax
0x1800491e4  jnz     short loc_1800491F1
0x1800491e6  cmp     [rsp+4A0h+Type], 4
0x1800491eb  jz      short loc_1800491F1
0x1800491ed  mov     dword ptr [rsp+4A0h+Data], eax
0x1800491f1  mov     rcx, [rsp+4A0h+hKey]; hKey
0x1800491f6  lea     rax, [rsp+4A0h+cbData]
0x1800491fb  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x180049200  lea     rdx, aAppmgmtdebugle; "AppMgmtDebugLevel"
0x180049207  lea     rax, ?gDebugLevel@@3KA; ulong gDebugLevel
0x18004920e  mov     [rsp+4A0h+cbData], 4
0x180049216  xor     r9d, r9d; lpType
0x180049219  mov     [rsp+4A0h+phkResult], rax; lpData
0x18004921e  xor     r8d, r8d; lpReserved
0x180049221  call    cs:__imp_RegQueryValueExW
0x180049228  nop     dword ptr [rax+rax+00h]
0x18004922d  mov     rcx, [rsp+4A0h+hKey]; hKey
0x180049232  lea     rax, [rsp+4A0h+cbData]
0x180049237  mov     [rsp+4A0h+lpcbData], rax; lpcbData
0x18004923c  lea     rdx, aAppmgmtdebugbr; "AppMgmtDebugBreak"
0x180049243  lea     rax, ?gDebugBreak@@3KA; ulong gDebugBreak
0x18004924a  mov     [rsp+4A0h+cbData], 4
0x180049252  xor     r9d, r9d; lpType
0x180049255  mov     [rsp+4A0h+phkResult], rax; lpData
0x18004925a  xor     r8d, r8d; lpReserved
0x18004925d  call    cs:__imp_RegQueryValueExW
0x180049264  nop     dword ptr [rax+rax+00h]
0x180049269  mov     rcx, [rsp+4A0h+hKey]; hKey
0x18004926e  call    cs:__imp_RegCloseKey
0x180049275  nop     dword ptr [rax+rax+00h]
0x18004927a  cmp     dword ptr [rsp+4A0h+Data], 0
0x18004927f  jz      short loc_180049292
0x180049281  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180049287  or      eax, 6
0x18004928a  mov     cs:?gDebugLevel@@3KA, eax; ulong gDebugLevel
0x180049290  jmp     short loc_180049298
0x180049292  mov     eax, cs:?gDebugLevel@@3KA; ulong gDebugLevel
0x180049298  test    al, 8
0x18004929a  jz      loc_18004935F
0x1800492a0  xorps   xmm0, xmm0
0x1800492a3  lea     rcx, [rbp+3A0h+FileName]; lpDst
0x1800492aa  xor     eax, eax
0x1800492ac  movups  [rsp+4A0h+FileInformation], xmm0
0x1800492b1  mov     [rsp+4A0h+var_438], eax
0x1800492b5  movups  [rsp+4A0h+var_448], xmm0
0x1800492ba  call    ?GetDebugLogFileName@@YAHPEAGJ@Z; GetDebugLogFileName(ushort *,long)
0x1800492bf  test    eax, eax
0x1800492c1  jz      loc_180049369
0x1800492c7  cmp     cs:?gDebugRequestedMode@@3KA, 1; ulong gDebugRequestedMode
0x1800492ce  jnz     loc_180049369
0x1800492d4  lea     r8, [rsp+4A0h+FileInformation]; lpFileInformation
0x1800492d9  xor     edx, edx; fInfoLevelId
0x1800492db  lea     rcx, [rbp+3A0h+FileName]; lpFileName
0x1800492e2  call    cs:__imp_GetFileAttributesExW
0x1800492e9  nop     dword ptr [rax+rax+00h]
0x1800492ee  test    eax, eax
0x1800492f0  jnz     short loc_180049305
0x1800492f2  call    cs:__imp_GetLastError
0x1800492f9  nop     dword ptr [rax+rax+00h]
0x1800492fe  cmp     eax, 2
0x180049301  jz      short loc_18004935F
0x180049303  jmp     short loc_180049369
0x180049305  cmp     [rsp+4A0h+var_438], 19000h
0x18004930d  jb      short loc_18004935F
0x18004930f  mov     r8d, 104h; nSize
0x180049315  lea     rdx, [rsp+4A0h+Dst]; lpDst
0x18004931a  lea     rcx, aSystemrootDebu; "%SystemRoot%\\Debug\\UserMode\\appmgmt."...
0x180049321  call    cs:__imp_ExpandEnvironmentStringsW
0x180049328  nop     dword ptr [rax+rax+00h]
0x18004932d  dec     eax
0x18004932f  cmp     eax, 103h
0x180049334  ja      short loc_18004935F
0x180049336  lea     rcx, [rsp+4A0h+Dst]; lpFileName
0x18004933b  call    cs:__imp_DeleteFileW
0x180049342  nop     dword ptr [rax+rax+00h]
0x180049347  lea     rdx, [rsp+4A0h+Dst]; lpNewFileName
0x18004934c  lea     rcx, [rbp+3A0h+FileName]; lpExistingFileName
0x180049353  call    cs:__imp_MoveFileW
0x18004935a  nop     dword ptr [rax+rax+00h]
0x18004935f  mov     cs:?gDebugInitialized@@3KA, 1; ulong gDebugInitialized
0x180049369  mov     rcx, [rbp+3A0h+var_10]
0x180049370  xor     rcx, rsp; StackCookie
0x180049373  call    __security_check_cookie
0x180049378  add     rsp, 4A0h
0x18004937f  pop     rbp
0x180049380  retn
```
