# SpSignSkipValidation

- ea: `0x140013d70`
- end: `0x140013e0b`
- name: `SpSignSkipValidation`
- size: `155`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x140015f08`
- `0x14002ccdc`
- `0x14002d158`
- `0x14002e0d4`
- `0x14002e91c`
- `0x14002ed80`

## callees

- `0x140013d70`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013da9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140013da9`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013dfc`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140013dfc`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013dde`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140013dde`

## pseudocode

```c
_BOOL8 SpSignSkipValidation()
{
  BOOL v0; // ebx
  DWORD cbData; // [rsp+50h] [rbp+18h] BYREF
  DWORD Type; // [rsp+58h] [rbp+20h] BYREF
  int Data; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  v0 = 0;
  hKey = 0;
  Type = 0;
  Data = 0;
  cbData = 0;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows\\CurrentVersion\\Setup", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"MinimizeFootprint", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
      v0 = cbData == 4;
    RegCloseKey(hKey);
  }
  return v0;
}

```

## disassembly

```asm
0x140013d70  push    rbp
0x140013d72  push    rbx
0x140013d73  mov     rbp, rsp
0x140013d76  sub     rsp, 38h
0x140013d7a  xor     ebx, ebx
0x140013d7c  lea     rax, [rbp+hKey]
0x140013d80  mov     r9d, 20019h; samDesired
0x140013d86  mov     [rbp+hKey], rbx
0x140013d8a  xor     r8d, r8d; ulOptions
0x140013d8d  mov     [rbp+Type], ebx
0x140013d90  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x140013d97  mov     [rbp+Data], ebx
0x140013d9a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140013da1  mov     [rbp+cbData], ebx
0x140013da4  mov     [rsp+38h+phkResult], rax; phkResult
0x140013da9  call    cs:__imp_RegOpenKeyExW
0x140013daf  test    eax, eax
0x140013db1  jnz     short loc_140013E02
0x140013db3  mov     rcx, [rbp+hKey]; hKey
0x140013db7  lea     rax, [rbp+cbData]
0x140013dbb  mov     [rsp+38h+lpcbData], rax; lpcbData
0x140013dc0  lea     r9, [rbp+Type]; lpType
0x140013dc4  lea     rax, [rbp+Data]
0x140013dc8  mov     [rbp+cbData], 4
0x140013dcf  xor     r8d, r8d; lpReserved
0x140013dd2  mov     [rsp+38h+phkResult], rax; lpData
0x140013dd7  lea     rdx, ValueName; "MinimizeFootprint"
0x140013dde  call    cs:__imp_RegQueryValueExW
0x140013de4  test    eax, eax
0x140013de6  jnz     short loc_140013DF8
0x140013de8  cmp     [rbp+Type], 4
0x140013dec  jnz     short loc_140013DF8
0x140013dee  cmp     [rbp+cbData], 4
0x140013df2  lea     eax, [rbx+1]
0x140013df5  cmovz   ebx, eax
0x140013df8  mov     rcx, [rbp+hKey]; hKey
0x140013dfc  call    cs:__imp_RegCloseKey
0x140013e02  mov     eax, ebx
0x140013e04  add     rsp, 38h
0x140013e08  pop     rbx
0x140013e09  pop     rbp
0x140013e0a  retn
```
