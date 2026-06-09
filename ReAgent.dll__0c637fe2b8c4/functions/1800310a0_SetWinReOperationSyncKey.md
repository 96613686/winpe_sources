# SetWinReOperationSyncKey

- ea: `0x1800310a0`
- end: `0x180031232`
- name: `SetWinReOperationSyncKey`
- size: `402`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800193e8`
- `0x18001fd7c`
- `0x18002a570`

## callees

- `0x1800059fc`
- `0x1800310a0`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegCreateKeyExW` at `0x180031110`
- `ADVAPI32!RegCreateKeyExW` at `0x18003118c`
- `ADVAPI32!RegCreateKeyExW` at `0x180031110`
- `ADVAPI32!RegCreateKeyExW` at `0x18003118c`
- `ADVAPI32!RegCloseKey` at `0x1800311f9`
- `ADVAPI32!RegCloseKey` at `0x180031210`
- `ADVAPI32!RegCloseKey` at `0x1800311f9`
- `ADVAPI32!RegCloseKey` at `0x180031210`

## string_xrefs

- `0x18003111c`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x180031133`: ` failed to open key`
- `0x1800311af`: `SetWinReOperationSyncKey failed to create key %s: %x`
- `0x1800311db`: `SetWinReOperationSyncKey another installation in progress`
- `0x18003115d`: `InstallInProgress`
- `0x1800311a3`: `InstallInProgress`

## pseudocode

```c
__int64 SetWinReOperationSyncKey()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  __int64 samDesired; // [rsp+28h] [rbp-48h]
  HKEY phkResult; // [rsp+50h] [rbp-20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp-18h] BYREF
  DWORD dwDisposition; // [rsp+60h] [rbp-10h] BYREF

  hKey = 0;
  phkResult = 0;
  dwDisposition = 0;
  v0 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
         0,
         0,
         0,
         0x30006u,
         0,
         &hKey,
         0);
  if ( v0 )
  {
    LODWORD(samDesired) = 113;
    UnattendLogW(
      2,
      L"SetWinReOperationSyncKey %s (0x%x) in file %S line %d",
      L" failed to open key",
      v0,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      samDesired);
  }
  else
  {
    v1 = RegCreateKeyExW(hKey, L"InstallInProgress", 0, 0, 1u, 1u, 0, &phkResult, &dwDisposition);
    v0 = v1;
    if ( v1 )
    {
      phkResult = 0;
      UnattendLogW(1, L"SetWinReOperationSyncKey failed to create key %s: %x", L"InstallInProgress", v1);
    }
    else if ( dwDisposition == 2 )
    {
      v0 = 1152;
      if ( !ReAgentError )
        ReAgentError = 26;
      UnattendLogW(1, L"SetWinReOperationSyncKey another installation in progress");
    }
    else
    {
      v0 = 0;
    }
  }
  if ( phkResult )
  {
    RegCloseKey(phkResult);
    phkResult = 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x1800310a0  mov     r11, rsp
0x1800310a3  mov     [r11+8], rbx
0x1800310a7  push    rbp
0x1800310a8  mov     rbp, rsp
0x1800310ab  sub     rsp, 70h
0x1800310af  mov     rax, cs:__security_cookie
0x1800310b6  xor     rax, rsp
0x1800310b9  mov     [rbp+var_8], rax
0x1800310bd  mov     qword ptr [r11-38h], 0
0x1800310c5  lea     rax, [rbp+hKey]
0x1800310c9  mov     [r11-40h], rax
0x1800310cd  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x1800310d4  mov     qword ptr [r11-48h], 0
0x1800310dc  xor     r9d, r9d; lpClass
0x1800310df  mov     dword ptr [rsp+70h+samDesired], 30006h; samDesired
0x1800310e7  xor     r8d, r8d; Reserved
0x1800310ea  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800310f1  mov     [rsp+70h+dwOptions], 0; dwOptions
0x1800310f9  mov     [rbp+hKey], 0
0x180031101  mov     [rbp+var_20], 0
0x180031109  mov     [rbp+dwDisposition], 0
0x180031110  call    cs:__imp_RegCreateKeyExW
0x180031116  mov     ebx, eax
0x180031118  test    eax, eax
0x18003111a  jz      short loc_180031150
0x18003111c  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x180031123  mov     dword ptr [rsp+70h+samDesired], 71h ; 'q'
0x18003112b  mov     r9d, ebx
0x18003112e  mov     qword ptr [rsp+70h+dwOptions], rax
0x180031133  lea     r8, aFailedToOpenKe_0; " failed to open key"
0x18003113a  mov     ecx, 2
0x18003113f  lea     rdx, aSetwinreoperat_1; "SetWinReOperationSyncKey %s (0x%x) in f"...
0x180031146  call    UnattendLogW
0x18003114b  jmp     loc_1800311F0
0x180031150  mov     rcx, [rbp+hKey]; hKey
0x180031154  lea     rax, [rbp+dwDisposition]
0x180031158  mov     [rsp+70h+lpdwDisposition], rax; lpdwDisposition
0x18003115d  lea     rdx, aInstallinprogr; "InstallInProgress"
0x180031164  lea     rax, [rbp+var_20]
0x180031168  xor     r9d, r9d; lpClass
0x18003116b  mov     [rsp+70h+phkResult], rax; phkResult
0x180031170  xor     r8d, r8d; Reserved
0x180031173  mov     [rsp+70h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18003117c  mov     dword ptr [rsp+70h+samDesired], 1; samDesired
0x180031184  mov     [rsp+70h+dwOptions], 1; dwOptions
0x18003118c  call    cs:__imp_RegCreateKeyExW
0x180031192  mov     ebx, eax
0x180031194  test    eax, eax
0x180031196  jz      short loc_1800311BD
0x180031198  mov     r9d, eax
0x18003119b  mov     [rbp+var_20], 0
0x1800311a3  lea     r8, aInstallinprogr; "InstallInProgress"
0x1800311aa  mov     ecx, 1
0x1800311af  lea     rdx, aSetwinreoperat_0; "SetWinReOperationSyncKey failed to crea"...
0x1800311b6  call    UnattendLogW
0x1800311bb  jmp     short loc_1800311F0
0x1800311bd  cmp     [rbp+dwDisposition], 2
0x1800311c1  jnz     short loc_1800311EE
0x1800311c3  cmp     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 0; _ReAgentErrorCodes ReAgentError
0x1800311ca  mov     ebx, 480h
0x1800311cf  jnz     short loc_1800311DB
0x1800311d1  mov     cs:?ReAgentError@@3W4_ReAgentErrorCodes@@A, 1Ah; _ReAgentErrorCodes ReAgentError
0x1800311db  lea     rdx, aSetwinreoperat; "SetWinReOperationSyncKey another instal"...
0x1800311e2  mov     ecx, 1
0x1800311e7  call    UnattendLogW
0x1800311ec  jmp     short loc_1800311F0
0x1800311ee  xor     ebx, ebx
0x1800311f0  mov     rcx, [rbp+var_20]; hKey
0x1800311f4  test    rcx, rcx
0x1800311f7  jz      short loc_180031207
0x1800311f9  call    cs:__imp_RegCloseKey
0x1800311ff  mov     [rbp+var_20], 0
0x180031207  mov     rcx, [rbp+hKey]; hKey
0x18003120b  test    rcx, rcx
0x18003120e  jz      short loc_180031216
0x180031210  call    cs:__imp_RegCloseKey
0x180031216  mov     eax, ebx
0x180031218  mov     rcx, [rbp+var_8]
0x18003121c  xor     rcx, rsp; StackCookie
0x18003121f  call    __security_check_cookie
0x180031224  mov     rbx, [rsp+70h+arg_0]
0x18003122c  add     rsp, 70h
0x180031230  pop     rbp
0x180031231  retn
```
