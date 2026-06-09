# Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(void)

- ea: `0x18000b7d4`
- end: `0x18000b87b`
- name: `?GetStoreVersion@AssignedAccessConfigStoreHelper@AssignedAccess@Internal@Windows@@AEAAKXZ`
- size: `167`
- prototype: `__int64 __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18000ab90`

## callees

- `0x18000b7d4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b802`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18000b802`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b859`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b86c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b859`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000b86c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b83d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18000b83d`

## pseudocode

```c
__int64 __fastcall Windows::Internal::AssignedAccess::AssignedAccessConfigStoreHelper::GetStoreVersion(LPCWSTR *this)
{
  LSTATUS v1; // eax
  HKEY v2; // rcx
  unsigned int v3; // ebx
  DWORD Type; // [rsp+50h] [rbp+18h] BYREF
  unsigned int Data; // [rsp+58h] [rbp+20h] BYREF
  DWORD cbData; // [rsp+60h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+68h] [rbp+30h] BYREF

  hKey = 0;
  v1 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, *this, 0, 0x20019u, &hKey);
  v2 = hKey;
  if ( !v1 )
  {
    Type = 0;
    Data = 0;
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"Version", 0, &Type, (LPBYTE)&Data, &cbData) && Type == 4 )
    {
      v3 = Data;
      if ( hKey )
        RegCloseKey(hKey);
      return v3;
    }
    v2 = hKey;
  }
  if ( v2 )
    RegCloseKey(v2);
  return 0;
}

```

## disassembly

```asm
0x18000b7d4  push    rbp
0x18000b7d6  push    rbx
0x18000b7d7  mov     rbp, rsp
0x18000b7da  sub     rsp, 38h
0x18000b7de  mov     [rbp+hKey], 0
0x18000b7e6  lea     rax, [rbp+hKey]
0x18000b7ea  mov     [rsp+38h+phkResult], rax; phkResult
0x18000b7ef  mov     r9d, 20019h; samDesired
0x18000b7f5  xor     r8d, r8d; ulOptions
0x18000b7f8  mov     rdx, [rcx]; lpSubKey
0x18000b7fb  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18000b802  call    cs:__imp_RegOpenKeyExW
0x18000b808  mov     rcx, [rbp+hKey]; hKey
0x18000b80c  test    eax, eax
0x18000b80e  jnz     short loc_18000B867
0x18000b810  mov     [rbp+Type], eax
0x18000b813  mov     [rbp+Data], eax
0x18000b816  mov     [rbp+cbData], 4
0x18000b81d  lea     rax, [rbp+cbData]
0x18000b821  mov     [rsp+38h+lpcbData], rax; lpcbData
0x18000b826  lea     rax, [rbp+Data]
0x18000b82a  mov     [rsp+38h+phkResult], rax; lpData
0x18000b82f  lea     r9, [rbp+Type]; lpType
0x18000b833  xor     r8d, r8d; lpReserved
0x18000b836  lea     rdx, ValueName; "Version"
0x18000b83d  call    cs:__imp_RegQueryValueExW
0x18000b843  test    eax, eax
0x18000b845  jnz     short loc_18000B863
0x18000b847  cmp     [rbp+Type], 4
0x18000b84b  jnz     short loc_18000B863
0x18000b84d  mov     ebx, [rbp+Data]
0x18000b850  mov     rcx, [rbp+hKey]; hKey
0x18000b854  test    rcx, rcx
0x18000b857  jz      short loc_18000B85F
0x18000b859  call    cs:__imp_RegCloseKey
0x18000b85f  mov     eax, ebx
0x18000b861  jmp     short loc_18000B874
0x18000b863  mov     rcx, [rbp+hKey]; hKey
0x18000b867  test    rcx, rcx
0x18000b86a  jz      short loc_18000B872
0x18000b86c  call    cs:__imp_RegCloseKey
0x18000b872  xor     eax, eax
0x18000b874  add     rsp, 38h
0x18000b878  pop     rbx
0x18000b879  pop     rbp
0x18000b87a  retn
```
