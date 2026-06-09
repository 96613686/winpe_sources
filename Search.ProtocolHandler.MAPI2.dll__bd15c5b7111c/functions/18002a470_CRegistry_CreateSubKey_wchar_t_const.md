# CRegistry::CreateSubKey(wchar_t const *)

- ea: `0x18002a470`
- end: `0x18002a50c`
- name: `?CreateSubKey@CRegistry@@UEAAHPEB_W@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002a470`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a496`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4fc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a496`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a4fc`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a4d3`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18002a4d3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4e6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002a4e6`

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
0x18002a470  sub     rsp, 58h
0x18002a474  mov     rcx, [rcx+0B0h]; hKey
0x18002a47b  mov     [rsp+58h+hKey], 0
0x18002a484  mov     [rsp+58h+dwDisposition], 0
0x18002a48c  test    rcx, rcx
0x18002a48f  jnz     short loc_18002A4A0
0x18002a491  mov     ecx, 6; dwErrCode
0x18002a496  call    cs:__imp_SetLastError
0x18002a49c  xor     eax, eax
0x18002a49e  jmp     short loc_18002A507
0x18002a4a0  lea     rax, [rsp+58h+dwDisposition]
0x18002a4a5  xor     r9d, r9d; lpClass
0x18002a4a8  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x18002a4ad  xor     r8d, r8d; Reserved
0x18002a4b0  lea     rax, [rsp+58h+hKey]
0x18002a4b5  mov     [rsp+58h+phkResult], rax; phkResult
0x18002a4ba  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002a4c3  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x18002a4cb  mov     [rsp+58h+dwOptions], 0; dwOptions
0x18002a4d3  call    cs:__imp_RegCreateKeyExW
0x18002a4d9  test    eax, eax
0x18002a4db  jz      short loc_18002A4E1
0x18002a4dd  mov     ecx, eax
0x18002a4df  jmp     short loc_18002A496
0x18002a4e1  mov     rcx, [rsp+58h+hKey]; hKey
0x18002a4e6  call    cs:__imp_RegCloseKey
0x18002a4ec  cmp     [rsp+58h+dwDisposition], 2
0x18002a4f1  jnz     short loc_18002A4FA
0x18002a4f3  mov     ecx, 0B7h
0x18002a4f8  jmp     short loc_18002A496
0x18002a4fa  xor     ecx, ecx; dwErrCode
0x18002a4fc  call    cs:__imp_SetLastError
0x18002a502  mov     eax, 1
0x18002a507  add     rsp, 58h
0x18002a50b  retn
```
