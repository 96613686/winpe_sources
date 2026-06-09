# CacheRegionalCodeInUCPDRegistry(void)

- ea: `0x14000e850`
- end: `0x14000e99a`
- name: `?CacheRegionalCodeInUCPDRegistry@@YAXXZ`
- size: `330`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000e590`

## callees

- `0x14000a390`
- `0x14000e850`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x14000e8a1`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e90c`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e8a1`
- `ADVAPI32!RegOpenKeyExW` at `0x14000e90c`
- `ADVAPI32!RegCloseKey` at `0x14000e8de`
- `ADVAPI32!RegCloseKey` at `0x14000e97d`
- `ADVAPI32!RegCloseKey` at `0x14000e8de`
- `ADVAPI32!RegCloseKey` at `0x14000e97d`
- `ADVAPI32!RegQueryValueExW` at `0x14000e8d2`
- `ADVAPI32!RegQueryValueExW` at `0x14000e93c`
- `ADVAPI32!RegQueryValueExW` at `0x14000e8d2`
- `ADVAPI32!RegQueryValueExW` at `0x14000e93c`
- `ADVAPI32!RegSetValueExW` at `0x14000e973`
- `ADVAPI32!RegSetValueExW` at `0x14000e973`

## string_xrefs

- `0x14000e8fe`: `SYSTEM\CurrentControlSet\Services\UCPD`
- `0x14000e91a`: `RCodeCache`
- `0x14000e95e`: `RCodeCache`

## pseudocode

```c
void CacheRegionalCodeInUCPDRegistry(void)
{
  LSTATUS v0; // ebx
  HKEY hKey; // [rsp+30h] [rbp-20h] BYREF
  BYTE Data[4]; // [rsp+38h] [rbp-18h] BYREF
  DWORD cbData; // [rsp+3Ch] [rbp-14h] BYREF
  BYTE v4[8]; // [rsp+40h] [rbp-10h] BYREF

  hKey = 0;
  *(_DWORD *)Data = 0;
  cbData = 4;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Control Panel\\DeviceRegion",
          0,
          0x20019u,
          &hKey) )
  {
    v0 = RegQueryValueExW(hKey, L"DeviceRegion", 0, 0, Data, &cbData);
    RegCloseKey(hKey);
    if ( !v0 && !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"SYSTEM\\CurrentControlSet\\Services\\UCPD", 0, 0x2001Fu, &hKey) )
    {
      *(_DWORD *)v4 = 0;
      if ( RegQueryValueExW(hKey, L"RCodeCache", 0, 0, v4, &cbData) || *(_DWORD *)v4 != *(_DWORD *)Data )
        RegSetValueExW(hKey, L"RCodeCache", 0, 4u, Data, 4u);
      RegCloseKey(hKey);
    }
  }
}

```

## disassembly

```asm
0x14000e850  mov     [rsp-8+arg_0], rbx
0x14000e855  push    rbp
0x14000e856  mov     rbp, rsp
0x14000e859  sub     rsp, 50h
0x14000e85d  mov     rax, cs:__security_cookie
0x14000e864  xor     rax, rsp
0x14000e867  mov     [rbp+var_8], rax
0x14000e86b  lea     rax, [rbp+hKey]
0x14000e86f  mov     [rbp+hKey], 0
0x14000e877  mov     r9d, 20019h; samDesired
0x14000e87d  mov     [rsp+50h+phkResult], rax; phkResult
0x14000e882  xor     r8d, r8d; ulOptions
0x14000e885  mov     dword ptr [rbp+Data], 0
0x14000e88c  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14000e893  mov     [rbp+cbData], 4
0x14000e89a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e8a1  call    cs:__imp_RegOpenKeyExW
0x14000e8a7  test    eax, eax
0x14000e8a9  jnz     loc_14000E983
0x14000e8af  mov     rcx, [rbp+hKey]; hKey
0x14000e8b3  lea     rax, [rbp+cbData]
0x14000e8b7  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000e8bc  lea     rdx, ValueName; "DeviceRegion"
0x14000e8c3  lea     rax, [rbp+Data]
0x14000e8c7  xor     r9d, r9d; lpType
0x14000e8ca  xor     r8d, r8d; lpReserved
0x14000e8cd  mov     [rsp+50h+phkResult], rax; lpData
0x14000e8d2  call    cs:__imp_RegQueryValueExW
0x14000e8d8  mov     rcx, [rbp+hKey]; hKey
0x14000e8dc  mov     ebx, eax
0x14000e8de  call    cs:__imp_RegCloseKey
0x14000e8e4  test    ebx, ebx
0x14000e8e6  jnz     loc_14000E983
0x14000e8ec  lea     rax, [rbp+hKey]
0x14000e8f0  mov     r9d, 2001Fh; samDesired
0x14000e8f6  xor     r8d, r8d; ulOptions
0x14000e8f9  mov     [rsp+50h+phkResult], rax; phkResult
0x14000e8fe  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\UC"...
0x14000e905  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000e90c  call    cs:__imp_RegOpenKeyExW
0x14000e912  test    eax, eax
0x14000e914  jnz     short loc_14000E983
0x14000e916  mov     rcx, [rbp+hKey]; hKey
0x14000e91a  lea     rdx, aRcodecache; "RCodeCache"
0x14000e921  mov     dword ptr [rbp+var_10], eax
0x14000e924  xor     r9d, r9d; lpType
0x14000e927  lea     rax, [rbp+cbData]
0x14000e92b  xor     r8d, r8d; lpReserved
0x14000e92e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000e933  lea     rax, [rbp+var_10]
0x14000e937  mov     [rsp+50h+phkResult], rax; lpData
0x14000e93c  call    cs:__imp_RegQueryValueExW
0x14000e942  test    eax, eax
0x14000e944  jnz     short loc_14000E94E
0x14000e946  mov     eax, dword ptr [rbp+Data]
0x14000e949  cmp     dword ptr [rbp+var_10], eax
0x14000e94c  jz      short loc_14000E979
0x14000e94e  mov     rcx, [rbp+hKey]; hKey
0x14000e952  lea     rax, [rbp+Data]
0x14000e956  mov     dword ptr [rsp+50h+lpcbData], 4; cbData
0x14000e95e  lea     rdx, aRcodecache; "RCodeCache"
0x14000e965  mov     r9d, 4; dwType
0x14000e96b  mov     [rsp+50h+phkResult], rax; lpData
0x14000e970  xor     r8d, r8d; Reserved
0x14000e973  call    cs:__imp_RegSetValueExW
0x14000e979  mov     rcx, [rbp+hKey]; hKey
0x14000e97d  call    cs:__imp_RegCloseKey
0x14000e983  mov     rcx, [rbp+var_8]
0x14000e987  xor     rcx, rsp; StackCookie
0x14000e98a  call    __security_check_cookie
0x14000e98f  mov     rbx, [rsp+50h+arg_0]
0x14000e994  add     rsp, 50h
0x14000e998  pop     rbp
0x14000e999  retn
```
