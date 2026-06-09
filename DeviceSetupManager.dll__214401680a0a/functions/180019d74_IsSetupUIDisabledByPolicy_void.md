# _IsSetupUIDisabledByPolicy(void)

- ea: `0x180019d74`
- end: `0x180019e35`
- name: `?_IsSetupUIDisabledByPolicy@@YA_NXZ`
- size: `193`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18003598c`

## callees

- `0x180019d74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019da8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180019da8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019df7`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019df7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e26`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180019e26`

## string_xrefs

- `0x180019d98`: `Software\Policies\Microsoft\Windows\DeviceInstall\Settings`

## pseudocode

```c
bool _IsSetupUIDisabledByPolicy(void)
{
  bool v0; // bl
  LSTATUS v1; // eax
  bool v2; // sf
  LSTATUS v3; // eax
  bool v4; // sf
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v0 = 0;
  v1 = RegOpenKeyExW(
         HKEY_LOCAL_MACHINE,
         L"Software\\Policies\\Microsoft\\Windows\\DeviceInstall\\Settings",
         0,
         0x20019u,
         &hKey);
  v2 = v1 < 0;
  if ( v1 > 0 )
    v2 = 1;
  if ( !v2 )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    v3 = RegQueryValueExW(hKey, L"DisableBalloonTips", 0, &Type, (LPBYTE)&Data, &cbData);
    v4 = v3 < 0;
    if ( v3 > 0 )
      v4 = 1;
    if ( !v4 && Type == 4 )
      v0 = Data != 0;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x180019d74  push    rbp
0x180019d76  push    rbx
0x180019d77  mov     rbp, rsp
0x180019d7a  sub     rsp, 38h
0x180019d7e  lea     rax, [rbp+hKey]
0x180019d82  mov     [rbp+hKey], 0
0x180019d8a  mov     r9d, 20019h; samDesired
0x180019d90  mov     [rsp+38h+phkResult], rax; phkResult
0x180019d95  xor     r8d, r8d; ulOptions
0x180019d98  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x180019d9f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019da6  xor     bl, bl
0x180019da8  call    cs:__imp_RegOpenKeyExW
0x180019dae  test    eax, eax
0x180019db0  jle     short loc_180019DBC
0x180019db2  movzx   eax, ax
0x180019db5  or      eax, 80070000h
0x180019dba  test    eax, eax
0x180019dbc  js      short loc_180019E2C
0x180019dbe  mov     rcx, [rbp+hKey]; hKey
0x180019dc2  lea     rax, [rbp+cbData]
0x180019dc6  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180019dcb  lea     r9, [rbp+Type]; lpType
0x180019dcf  lea     rax, [rbp+Data]
0x180019dd3  mov     [rbp+Type], 0
0x180019dda  xor     r8d, r8d; lpReserved
0x180019ddd  mov     [rsp+38h+phkResult], rax; lpData
0x180019de2  lea     rdx, aDisableballoon; "DisableBalloonTips"
0x180019de9  mov     [rbp+Data], 0
0x180019df0  mov     [rbp+cbData], 4
0x180019df7  call    cs:__imp_RegQueryValueExW
0x180019dfd  test    eax, eax
0x180019dff  jle     short loc_180019E0B
0x180019e01  movzx   eax, ax
0x180019e04  or      eax, 80070000h
0x180019e09  test    eax, eax
0x180019e0b  js      short loc_180019E22
0x180019e0d  cmp     [rbp+Type], 4
0x180019e11  jnz     short loc_180019E22
0x180019e13  cmp     [rbp+Data], 0
0x180019e17  mov     eax, 1
0x180019e1c  movzx   ebx, bl
0x180019e1f  cmovnz  ebx, eax
0x180019e22  mov     rcx, [rbp+hKey]; hKey
0x180019e26  call    cs:__imp_RegCloseKey
0x180019e2c  mov     al, bl
0x180019e2e  add     rsp, 38h
0x180019e32  pop     rbx
0x180019e33  pop     rbp
0x180019e34  retn
```
