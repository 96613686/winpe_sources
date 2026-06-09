# EURL::GetEnableExtensionlessUrlsRegKey(void)

- ea: `0x180001fa4`
- end: `0x180002034`
- name: `?GetEnableExtensionlessUrlsRegKey@EURL@@CAHXZ`
- size: `144`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002048`

## callees

- `0x180001fa4`

## import_xrefs

- `ADVAPI32!RegQueryValueExW` at `0x18000200e`
- `ADVAPI32!RegQueryValueExW` at `0x18000200e`
- `ADVAPI32!RegOpenKeyExW` at `0x180001fde`
- `ADVAPI32!RegOpenKeyExW` at `0x180001fde`
- `ADVAPI32!RegCloseKey` at `0x18000201e`
- `ADVAPI32!RegCloseKey` at `0x18000201e`

## string_xrefs

- `0x180001ff7`: `EnableExtensionlessUrls`

## pseudocode

```c
__int64 EURL::GetEnableExtensionlessUrlsRegKey(void)
{
  unsigned int v0; // ebx
  int Data; // [rsp+40h] [rbp+8h] BYREF
  DWORD cbData; // [rsp+48h] [rbp+10h] BYREF
  HKEY hKey; // [rsp+50h] [rbp+18h] BYREF

  v0 = 0;
  Data = 1;
  hKey = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\ASP.NET\\4.0.30319.0", 0, 1u, &hKey) )
    RegQueryValueExW(hKey, L"EnableExtensionlessUrls", 0, 0, (LPBYTE)&Data, &cbData);
  if ( hKey )
    RegCloseKey(hKey);
  LOBYTE(v0) = Data == 1;
  return v0;
}

```

## disassembly

```asm
0x180001fa4  mov     rax, rsp
0x180001fa7  push    rbx
0x180001fa8  sub     rsp, 30h
0x180001fac  xor     ebx, ebx
0x180001fae  mov     dword ptr [rax+8], 1
0x180001fb5  mov     [rax+18h], rbx
0x180001fb9  xor     r8d, r8d; ulOptions
0x180001fbc  mov     dword ptr [rax+10h], 4
0x180001fc3  lea     rax, [rax+18h]
0x180001fc7  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\ASP.NET\\4.0.30319"...
0x180001fce  mov     [rsp+38h+phkResult], rax; phkResult
0x180001fd3  lea     r9d, [rbx+1]; samDesired
0x180001fd7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001fde  call    cs:__imp_RegOpenKeyExW
0x180001fe4  test    eax, eax
0x180001fe6  jnz     short loc_180002014
0x180001fe8  mov     rcx, [rsp+38h+hKey]; hKey
0x180001fed  lea     rax, [rsp+38h+cbData]
0x180001ff2  mov     [rsp+38h+lpcbData], rax; lpcbData
0x180001ff7  lea     rdx, aEnableextensio; "EnableExtensionlessUrls"
0x180001ffe  lea     rax, [rsp+38h+Data]
0x180002003  xor     r9d, r9d; lpType
0x180002006  xor     r8d, r8d; lpReserved
0x180002009  mov     [rsp+38h+phkResult], rax; lpData
0x18000200e  call    cs:__imp_RegQueryValueExW
0x180002014  mov     rcx, [rsp+38h+hKey]; hKey
0x180002019  test    rcx, rcx
0x18000201c  jz      short loc_180002024
0x18000201e  call    cs:__imp_RegCloseKey
0x180002024  cmp     [rsp+38h+Data], 1
0x180002029  setz    bl
0x18000202c  mov     eax, ebx
0x18000202e  add     rsp, 30h
0x180002032  pop     rbx
0x180002033  retn
```
