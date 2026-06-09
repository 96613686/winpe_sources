# GetGroupPolicySetting

- ea: `0x180004a70`
- end: `0x180004bee`
- name: `GetGroupPolicySetting`
- size: `382`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180003ac8`

## callees

- `0x180002590`
- `0x180004a70`
- `0x180007013`
- `0x180007040`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004b31`
- `KERNEL32!GetLastError` at `0x180004b31`
- `KERNEL32!GetVersionExW` at `0x180004b27`
- `KERNEL32!GetVersionExW` at `0x180004b27`
- `ADVAPI32!RegQueryValueExW` at `0x180004b91`
- `ADVAPI32!RegQueryValueExW` at `0x180004b91`
- `ADVAPI32!RegOpenKeyExW` at `0x180004afe`
- `ADVAPI32!RegOpenKeyExW` at `0x180004afe`
- `ADVAPI32!RegCloseKey` at `0x180004bc5`
- `ADVAPI32!RegCloseKey` at `0x180004bc5`

## string_xrefs

- `0x180004aca`: `MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n`

## pseudocode

```c
__int64 __fastcall GetGroupPolicySetting(_DWORD *a1)
{
  signed int v2; // ebx
  int v3; // r9d
  signed int LastError; // eax
  LSTATUS v5; // eax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[4]; // [rsp+34h] [rbp-CCh] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+40h] [rbp-C0h] BYREF
  char v11; // [rsp+15Ah] [rbp+5Ah]

  hKey = 0;
  *(_DWORD *)Data = 2;
  cbData = 0;
  if ( !a1 )
  {
    v2 = -2147024809;
    v3 = 59;
LABEL_3:
    DebugPrint(0, "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n", "GetGroupPolicySetting", v3, v2);
    goto LABEL_15;
  }
  if ( RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\WDI\\{54077489-683b-4762-86c8-02cf87a33423}",
         0,
         0x20019u,
         &hKey) )
  {
    memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
    VersionInformation.dwOSVersionInfoSize = 284;
    if ( !GetVersionExW(&VersionInformation) )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      v3 = 79;
      goto LABEL_3;
    }
    v2 = 0;
    *a1 = (v11 != 1) + 2;
  }
  else
  {
    cbData = 4;
    v5 = RegQueryValueExW(hKey, L"EnabledScenarioExecutionLevel", 0, 0, Data, &cbData);
    v2 = v5;
    if ( v5 > 0 )
      v2 = (unsigned __int16)v5 | 0x80070000;
    if ( v2 < 0 )
    {
      v3 = 102;
      goto LABEL_3;
    }
    *a1 = *(_DWORD *)Data;
  }
LABEL_15:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180004a70  mov     [rsp-8+arg_8], rbx
0x180004a75  mov     [rsp-8+arg_10], rdi
0x180004a7a  push    rbp
0x180004a7b  lea     rbp, [rsp-70h]
0x180004a80  sub     rsp, 170h
0x180004a87  mov     rax, cs:__security_cookie
0x180004a8e  xor     rax, rsp
0x180004a91  mov     [rbp+70h+var_10], rax
0x180004a95  mov     [rsp+170h+hKey], 0
0x180004a9e  mov     rdi, rcx
0x180004aa1  mov     dword ptr [rsp+170h+Data], 2
0x180004aa9  mov     [rsp+170h+cbData], 0
0x180004ab1  test    rcx, rcx
0x180004ab4  jnz     short loc_180004ADD
0x180004ab6  mov     ebx, 80070057h
0x180004abb  lea     r9d, [rcx+3Bh]
0x180004abf  lea     r8, aGetgrouppolicy; "GetGroupPolicySetting"
0x180004ac6  mov     dword ptr [rsp+170h+phkResult], ebx
0x180004aca  lea     rdx, aMsiCofireError; "MSI-COFIRE ERROR: %s:%d - hr = 0x%08X\n"
0x180004ad1  xor     ecx, ecx; Level
0x180004ad3  call    ?DebugPrint@@YAXKPEBDZZ; DebugPrint(ulong,char const *,...)
0x180004ad8  jmp     loc_180004BBB
0x180004add  lea     rax, [rsp+170h+hKey]
0x180004ae2  mov     r9d, 20019h; samDesired
0x180004ae8  xor     r8d, r8d; ulOptions
0x180004aeb  mov     [rsp+170h+phkResult], rax; phkResult
0x180004af0  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180004af7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180004afe  call    cs:__imp_RegOpenKeyExW
0x180004b04  test    eax, eax
0x180004b06  jz      short loc_180004B63
0x180004b08  xor     edx, edx; Val
0x180004b0a  lea     rcx, [rsp+170h+VersionInformation.dwMajorVersion]; void *
0x180004b0f  mov     r8d, 118h; Size
0x180004b15  call    memset_0
0x180004b1a  lea     rcx, [rsp+170h+VersionInformation]; lpVersionInformation
0x180004b1f  mov     [rsp+170h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x180004b27  call    cs:__imp_GetVersionExW
0x180004b2d  test    eax, eax
0x180004b2f  jnz     short loc_180004B51
0x180004b31  call    cs:__imp_GetLastError
0x180004b37  mov     ebx, eax
0x180004b39  test    eax, eax
0x180004b3b  jle     short loc_180004B46
0x180004b3d  movzx   ebx, ax
0x180004b40  or      ebx, 80070000h
0x180004b46  mov     r9d, 4Fh ; 'O'
0x180004b4c  jmp     loc_180004ABF
0x180004b51  xor     eax, eax
0x180004b53  xor     ebx, ebx
0x180004b55  cmp     [rbp+70h+var_16], 1
0x180004b59  setnz   al
0x180004b5c  add     eax, 2
0x180004b5f  mov     [rdi], eax
0x180004b61  jmp     short loc_180004BBB
0x180004b63  mov     rcx, [rsp+170h+hKey]; hKey
0x180004b68  lea     rax, [rsp+170h+cbData]
0x180004b6d  mov     [rsp+170h+lpcbData], rax; lpcbData
0x180004b72  lea     rdx, aEnabledscenari; "EnabledScenarioExecutionLevel"
0x180004b79  lea     rax, [rsp+170h+Data]
0x180004b7e  mov     [rsp+170h+cbData], 4
0x180004b86  xor     r9d, r9d; lpType
0x180004b89  mov     [rsp+170h+phkResult], rax; lpData
0x180004b8e  xor     r8d, r8d; lpReserved
0x180004b91  call    cs:__imp_RegQueryValueExW
0x180004b97  mov     ebx, eax
0x180004b99  test    eax, eax
0x180004b9b  jle     short loc_180004BA6
0x180004b9d  movzx   ebx, ax
0x180004ba0  or      ebx, 80070000h
0x180004ba6  test    ebx, ebx
0x180004ba8  jns     short loc_180004BB5
0x180004baa  mov     r9d, 66h ; 'f'
0x180004bb0  jmp     loc_180004ABF
0x180004bb5  mov     ecx, dword ptr [rsp+170h+Data]
0x180004bb9  mov     [rdi], ecx
0x180004bbb  mov     rcx, [rsp+170h+hKey]; hKey
0x180004bc0  test    rcx, rcx
0x180004bc3  jz      short loc_180004BCB
0x180004bc5  call    cs:__imp_RegCloseKey
0x180004bcb  mov     eax, ebx
0x180004bcd  mov     rcx, [rbp+70h+var_10]
0x180004bd1  xor     rcx, rsp; StackCookie
0x180004bd4  call    __security_check_cookie
0x180004bd9  lea     r11, [rsp+170h+var_s0]
0x180004be1  mov     rbx, [r11+18h]
0x180004be5  mov     rdi, [r11+20h]
0x180004be9  mov     rsp, r11
0x180004bec  pop     rbp
0x180004bed  retn
```
