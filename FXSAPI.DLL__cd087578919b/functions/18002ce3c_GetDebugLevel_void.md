# GetDebugLevel(void)

- ea: `0x18002ce3c`
- end: `0x18002cef8`
- name: `?GetDebugLevel@@YAKXZ`
- size: `188`
- prototype: `unsigned int(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002d0e4`

## callees

- `0x18002ce3c`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18002cec1`
- `ADVAPI32!RegQueryValueExW` at `0x18002cec1`
- `ADVAPI32!RegCloseKey` at `0x18002cee2`
- `ADVAPI32!RegCloseKey` at `0x18002cee2`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ce82`
- `ADVAPI32!RegOpenKeyExW` at `0x18002ce82`

## pseudocode

```c
__int64 GetDebugLevel(void)
{
  unsigned int Data; // [rsp+40h] [rbp+10h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+18h] BYREF
  DWORD Type; // [rsp+50h] [rbp+20h] BYREF
  HKEY hKey; // [rsp+58h] [rbp+28h] BYREF

  Data = 0;
  cbData = 0;
  Type = 0;
  hKey = 0;
  if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Fax\\Client", 0, 0x20019u, &hKey) )
    return 0;
  cbData = 4;
  if ( RegQueryValueExW(hKey, L"DebugLevel", 0, &Type, (LPBYTE)&Data, &cbData) || Type != 4 )
    Data = 0;
  RegCloseKey(hKey);
  return Data;
}

```

## disassembly

```asm
0x18002ce3c  push    rbp
0x18002ce3e  mov     rbp, rsp
0x18002ce41  sub     rsp, 30h
0x18002ce45  lea     rax, [rbp+hKey]
0x18002ce49  mov     [rbp+Data], 0
0x18002ce50  mov     r9d, 20019h; samDesired
0x18002ce56  mov     [rsp+30h+phkResult], rax; phkResult
0x18002ce5b  xor     r8d, r8d; ulOptions
0x18002ce5e  mov     [rbp+cbData], 0
0x18002ce65  lea     rdx, SubKey; "Software\\Microsoft\\Fax\\Client"
0x18002ce6c  mov     [rbp+Type], 0
0x18002ce73  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18002ce7a  mov     [rbp+hKey], 0
0x18002ce82  call    cs:__imp_RegOpenKeyExW
0x18002ce89  nop     dword ptr [rax+rax+00h]
0x18002ce8e  test    eax, eax
0x18002ce90  jz      short loc_18002CE96
0x18002ce92  xor     eax, eax
0x18002ce94  jmp     short loc_18002CEF1
0x18002ce96  mov     rcx, [rbp+hKey]; hKey
0x18002ce9a  lea     rax, [rbp+cbData]
0x18002ce9e  mov     [rsp+30h+lpcbData], rax; lpcbData
0x18002cea3  lea     r9, [rbp+Type]; lpType
0x18002cea7  lea     rax, [rbp+Data]
0x18002ceab  mov     [rbp+cbData], 4
0x18002ceb2  xor     r8d, r8d; lpReserved
0x18002ceb5  mov     [rsp+30h+phkResult], rax; lpData
0x18002ceba  lea     rdx, aDebuglevel; "DebugLevel"
0x18002cec1  call    cs:__imp_RegQueryValueExW
0x18002cec8  nop     dword ptr [rax+rax+00h]
0x18002cecd  test    eax, eax
0x18002cecf  jnz     short loc_18002CED7
0x18002ced1  cmp     [rbp+Type], 4
0x18002ced5  jz      short loc_18002CEDE
0x18002ced7  mov     [rbp+Data], 0
0x18002cede  mov     rcx, [rbp+hKey]; hKey
0x18002cee2  call    cs:__imp_RegCloseKey
0x18002cee9  nop     dword ptr [rax+rax+00h]
0x18002ceee  mov     eax, [rbp+Data]
0x18002cef1  add     rsp, 30h
0x18002cef5  pop     rbp
0x18002cef6  retn
```
