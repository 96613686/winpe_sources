# EfspDeleteCurrentKey

- ea: `0x18003c950`
- end: `0x18003c9d0`
- name: `EfspDeleteCurrentKey`
- size: `128`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18003d348`

## callees

- `0x18003c950`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c9c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18003c9c5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c991`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c9a3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c9b5`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c991`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c9a3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18003c9b5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c97b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003c97b`

## pseudocode

```c
LSTATUS __fastcall EfspDeleteCurrentKey(__int64 a1)
{
  const WCHAR *v1; // rdx
  LSTATUS result; // eax
  HKEY hKey; // [rsp+40h] [rbp+8h] BYREF

  v1 = *(const WCHAR **)(a1 + 32);
  hKey = 0;
  result = RegOpenKeyExW(HKEY_USERS, v1, 0, 0x2001Fu, &hKey);
  if ( !result )
  {
    RegDeleteValueW(hKey, L"CertificateHash");
    RegDeleteValueW(hKey, L"Capabilities");
    result = RegDeleteValueW(hKey, L"Flag");
  }
  if ( hKey )
    return RegCloseKey(hKey);
  return result;
}

```

## disassembly

```asm
0x18003c950  sub     rsp, 38h
0x18003c954  mov     rdx, [rcx+20h]; lpSubKey
0x18003c958  lea     rax, [rsp+38h+hKey]
0x18003c95d  mov     rcx, 0FFFFFFFF80000003h; hKey
0x18003c964  mov     [rsp+38h+phkResult], rax; phkResult
0x18003c969  mov     r9d, 2001Fh; samDesired
0x18003c96f  mov     [rsp+38h+hKey], 0
0x18003c978  xor     r8d, r8d; ulOptions
0x18003c97b  call    cs:__imp_RegOpenKeyExW
0x18003c981  test    eax, eax
0x18003c983  jnz     short loc_18003C9BB
0x18003c985  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c98a  lea     rdx, aCertificatehas; "CertificateHash"
0x18003c991  call    cs:__imp_RegDeleteValueW
0x18003c997  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c99c  lea     rdx, aCapabilities; "Capabilities"
0x18003c9a3  call    cs:__imp_RegDeleteValueW
0x18003c9a9  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c9ae  lea     rdx, aFlag; "Flag"
0x18003c9b5  call    cs:__imp_RegDeleteValueW
0x18003c9bb  mov     rcx, [rsp+38h+hKey]; hKey
0x18003c9c0  test    rcx, rcx
0x18003c9c3  jz      short loc_18003C9CB
0x18003c9c5  call    cs:__imp_RegCloseKey
0x18003c9cb  add     rsp, 38h
0x18003c9cf  retn
```
