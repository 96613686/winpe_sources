# CRegistry::DeleteSubKey(wchar_t const *)

- ea: `0x18002a514`
- end: `0x18002a559`
- name: `?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z`
- size: `69`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002a560`

## callees

- `0x18002a514`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a529`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a549`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a529`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a549`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a539`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x18002a539`

## pseudocode

```c
__int64 __fastcall CRegistry::DeleteSubKey(CRegistry *this, const wchar_t *a2)
{
  HKEY v2; // rcx
  DWORD v3; // ecx
  LSTATUS v5; // eax

  v2 = (HKEY)*((_QWORD *)this + 22);
  if ( !v2 )
  {
    v3 = 6;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  v5 = RegDeleteKeyExW(v2, a2, 0, 0);
  if ( v5 )
  {
    v3 = v5;
    goto LABEL_3;
  }
  SetLastError(0);
  return 1;
}

```

## disassembly

```asm
0x18002a514  sub     rsp, 28h
0x18002a518  mov     rcx, [rcx+0B0h]; hKey
0x18002a51f  test    rcx, rcx
0x18002a522  jnz     short loc_18002A533
0x18002a524  mov     ecx, 6; dwErrCode
0x18002a529  call    cs:__imp_SetLastError
0x18002a52f  xor     eax, eax
0x18002a531  jmp     short loc_18002A554
0x18002a533  xor     r9d, r9d; Reserved
0x18002a536  xor     r8d, r8d; samDesired
0x18002a539  call    cs:__imp_RegDeleteKeyExW
0x18002a53f  test    eax, eax
0x18002a541  jz      short loc_18002A547
0x18002a543  mov     ecx, eax
0x18002a545  jmp     short loc_18002A529
0x18002a547  xor     ecx, ecx; dwErrCode
0x18002a549  call    cs:__imp_SetLastError
0x18002a54f  mov     eax, 1
0x18002a554  add     rsp, 28h
0x18002a558  retn
```
