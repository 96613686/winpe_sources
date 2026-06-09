# RemoveWinReOperationSyncKey

- ea: `0x180030fcc`
- end: `0x180031099`
- name: `RemoveWinReOperationSyncKey`
- size: `205`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800193e8`
- `0x18001fd7c`
- `0x180024ff0`
- `0x18002a570`

## callees

- `0x1800059fc`
- `0x180030fcc`
- `0x18005cf30`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x18003100b`
- `ADVAPI32!RegOpenKeyExW` at `0x18003100b`
- `ADVAPI32!RegCloseKey` at `0x18003107e`
- `ADVAPI32!RegCloseKey` at `0x18003107e`
- `ADVAPI32!RegDeleteKeyW` at `0x180031054`
- `ADVAPI32!RegDeleteKeyW` at `0x180031054`

## string_xrefs

- `0x18003102e`: `failed to open key`
- `0x180031017`: `base\diagnosis\srt\reagent2\reagent\util.cpp`
- `0x18003103a`: `RemoveWinReOperationSyncKey %s (0x%x) in file %S line %d`
- `0x180031063`: `RegDeleteKey(InstallKey) failed: 0x%x`
- `0x18003104d`: `InstallInProgress`

## pseudocode

```c
__int64 RemoveWinReOperationSyncKey()
{
  unsigned int v0; // ebx
  unsigned int v1; // eax
  int v3; // [rsp+28h] [rbp-20h]
  HKEY hKey; // [rsp+30h] [rbp-18h] BYREF

  hKey = 0;
  v0 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Reliability\\WinRE",
         0,
         0x10000u,
         &hKey);
  if ( v0 )
  {
    v3 = 177;
    UnattendLogW(
      2,
      L"RemoveWinReOperationSyncKey %s (0x%x) in file %S line %d",
      L"failed to open key",
      v0,
      "base\\diagnosis\\srt\\reagent2\\reagent\\util.cpp",
      v3);
  }
  else
  {
    v1 = RegDeleteKeyW(hKey, L"InstallInProgress");
    v0 = v1;
    if ( v1 )
      UnattendLogW(1, L"RegDeleteKey(InstallKey) failed: 0x%x", v1);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180030fcc  push    rbx
0x180030fce  sub     rsp, 40h
0x180030fd2  mov     rax, cs:__security_cookie
0x180030fd9  xor     rax, rsp
0x180030fdc  mov     [rsp+48h+var_10], rax
0x180030fe1  lea     rax, [rsp+48h+hKey]
0x180030fe6  mov     [rsp+48h+hKey], 0
0x180030fef  mov     r9d, 10000h; samDesired
0x180030ff5  mov     [rsp+48h+phkResult], rax; phkResult
0x180030ffa  xor     r8d, r8d; ulOptions
0x180030ffd  lea     rdx, aSoftwareMicros_9; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180031004  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18003100b  call    cs:__imp_RegOpenKeyExW
0x180031011  mov     ebx, eax
0x180031013  test    eax, eax
0x180031015  jz      short loc_180031048
0x180031017  lea     rax, aBaseDiagnosisS_0; "base\\diagnosis\\srt\\reagent2\\reagent"...
0x18003101e  mov     [rsp+48h+var_20], 0B1h
0x180031026  mov     r9d, ebx
0x180031029  mov     [rsp+48h+phkResult], rax
0x18003102e  lea     r8, aFailedToOpenKe; "failed to open key"
0x180031035  mov     ecx, 2
0x18003103a  lea     rdx, aRemovewinreope; "RemoveWinReOperationSyncKey %s (0x%x) i"...
0x180031041  call    UnattendLogW
0x180031046  jmp     short loc_180031074
0x180031048  mov     rcx, [rsp+48h+hKey]; hKey
0x18003104d  lea     rdx, aInstallinprogr; "InstallInProgress"
0x180031054  call    cs:__imp_RegDeleteKeyW
0x18003105a  mov     ebx, eax
0x18003105c  test    eax, eax
0x18003105e  jz      short loc_180031074
0x180031060  mov     r8d, eax
0x180031063  lea     rdx, aRegdeletekeyIn; "RegDeleteKey(InstallKey) failed: 0x%x"
0x18003106a  mov     ecx, 1
0x18003106f  call    UnattendLogW
0x180031074  mov     rcx, [rsp+48h+hKey]; hKey
0x180031079  test    rcx, rcx
0x18003107c  jz      short loc_180031084
0x18003107e  call    cs:__imp_RegCloseKey
0x180031084  mov     eax, ebx
0x180031086  mov     rcx, [rsp+48h+var_10]
0x18003108b  xor     rcx, rsp; StackCookie
0x18003108e  call    __security_check_cookie
0x180031093  add     rsp, 40h
0x180031097  pop     rbx
0x180031098  retn
```
