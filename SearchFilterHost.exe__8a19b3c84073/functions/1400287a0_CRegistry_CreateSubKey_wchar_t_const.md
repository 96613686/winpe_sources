# CRegistry::CreateSubKey(wchar_t const *)

- ea: `0x1400287a0`
- end: `0x14002883c`
- name: `?CreateSubKey@CRegistry@@UEAAHPEB_W@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400287a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400287c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002882c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400287c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14002882c`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140028803`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140028803`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028816`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140028816`

## pseudocode

```c
__int64 __fastcall CRegistry::CreateSubKey(CRegistry *this, const wchar_t *a2)
{
  HKEY v2; // rcx
  DWORD v3; // ecx
  LSTATUS v5; // eax
  DWORD dwDisposition; // [rsp+60h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+70h] [rbp+18h] BYREF

  v2 = (HKEY)*((_QWORD *)this + 22);
  hKey = 0;
  dwDisposition = 0;
  if ( !v2 )
  {
    v3 = 6;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = RegCreateKeyExW(v2, a2, 0, 0, 0, 0xF003Fu, 0, &hKey, &dwDisposition);
  if ( v5 )
  {
    v3 = v5;
    goto LABEL_3;
  }
  RegCloseKey(hKey);
  if ( dwDisposition == 2 )
  {
    v3 = 183;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x1400287a0  sub     rsp, 58h
0x1400287a4  mov     rcx, [rcx+0B0h]; hKey
0x1400287ab  mov     [rsp+58h+hKey], 0
0x1400287b4  mov     [rsp+58h+dwDisposition], 0
0x1400287bc  test    rcx, rcx
0x1400287bf  jnz     short loc_1400287D0
0x1400287c1  mov     ecx, 6; dwErrCode
0x1400287c6  call    cs:__imp_SetLastError
0x1400287cc  xor     eax, eax
0x1400287ce  jmp     short loc_140028837
0x1400287d0  lea     rax, [rsp+58h+dwDisposition]
0x1400287d5  xor     r9d, r9d; lpClass
0x1400287d8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x1400287dd  xor     r8d, r8d; Reserved
0x1400287e0  lea     rax, [rsp+58h+hKey]
0x1400287e5  mov     [rsp+58h+phkResult], rax; phkResult
0x1400287ea  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1400287f3  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x1400287fb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140028803  call    cs:__imp_RegCreateKeyExW
0x140028809  test    eax, eax
0x14002880b  jz      short loc_140028811
0x14002880d  mov     ecx, eax
0x14002880f  jmp     short loc_1400287C6
0x140028811  mov     rcx, [rsp+58h+hKey]; hKey
0x140028816  call    cs:__imp_RegCloseKey
0x14002881c  cmp     [rsp+58h+dwDisposition], 2
0x140028821  jnz     short loc_14002882A
0x140028823  mov     ecx, 0B7h
0x140028828  jmp     short loc_1400287C6
0x14002882a  xor     ecx, ecx; dwErrCode
0x14002882c  call    cs:__imp_SetLastError
0x140028832  mov     eax, 1
0x140028837  add     rsp, 58h
0x14002883b  retn
```
