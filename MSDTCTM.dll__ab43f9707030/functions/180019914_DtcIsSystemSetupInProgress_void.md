# DtcIsSystemSetupInProgress(void)

- ea: `0x180019914`
- end: `0x1800199c9`
- name: `?DtcIsSystemSetupInProgress@@YAHXZ`
- size: `181`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x180005220`

## callees

- `0x180019914`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019992`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180019992`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001995d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001995d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800199ba`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800199ba`

## pseudocode

```c
_BOOL8 DtcIsSystemSetupInProgress(void)
{
  BOOL v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  cbData = 0;
  Type = 0;
  Data = 0;
  hKey = 0;
  v0 = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\Setup", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"SystemSetupInProgress", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 && cbData == 4 )
      v0 = Data != 0;
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v0;
}

```

## disassembly

```asm
0x180019914  push    rbp
0x180019916  push    rbx
0x180019917  mov     rbp, rsp
0x18001991a  sub     rsp, 38h
0x18001991e  lea     rax, [rbp+hKey]
0x180019922  mov     [rbp+cbData], 0
0x180019929  mov     r9d, 20019h; samDesired
0x18001992f  mov     [rsp+38h+phkResult], rax; phkResult
0x180019934  xor     r8d, r8d; ulOptions
0x180019937  mov     [rbp+Type], 0
0x18001993e  lea     rdx, aSystemSetup; "System\\Setup"
0x180019945  mov     [rbp+Data], 0
0x18001994c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180019953  mov     [rbp+hKey], 0
0x18001995b  xor     ebx, ebx
0x18001995d  call    cs:__imp_RegOpenKeyExW
0x180019963  test    eax, eax
0x180019965  jnz     short loc_1800199B1
0x180019967  mov     rcx, [rbp+hKey]; hKey
0x18001996b  lea     rax, [rbp+cbData]
0x18001996f  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180019974  lea     r9, [rbp+Type]; lpType
0x180019978  lea     rax, [rbp+Data]
0x18001997c  mov     [rbp+cbData], 4
0x180019983  xor     r8d, r8d; lpReserved
0x180019986  mov     [rsp+38h+phkResult], rax; lpData
0x18001998b  lea     rdx, aSystemsetupinp; "SystemSetupInProgress"
0x180019992  call    cs:__imp_RegQueryValueExW
0x180019998  test    eax, eax
0x18001999a  jnz     short loc_1800199B1
0x18001999c  cmp     [rbp+Type], 4
0x1800199a0  jnz     short loc_1800199B1
0x1800199a2  cmp     [rbp+cbData], 4
0x1800199a6  jnz     short loc_1800199B1
0x1800199a8  cmp     [rbp+Data], ebx
0x1800199ab  lea     eax, [rbx+1]
0x1800199ae  cmovnz  ebx, eax
0x1800199b1  mov     rcx, [rbp+hKey]; hKey
0x1800199b5  test    rcx, rcx
0x1800199b8  jz      short loc_1800199C0
0x1800199ba  call    cs:__imp_RegCloseKey
0x1800199c0  mov     eax, ebx
0x1800199c2  add     rsp, 38h
0x1800199c6  pop     rbx
0x1800199c7  pop     rbp
0x1800199c8  retn
```
