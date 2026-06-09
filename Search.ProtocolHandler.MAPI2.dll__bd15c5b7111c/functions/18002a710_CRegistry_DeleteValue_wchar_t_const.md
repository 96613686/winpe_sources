# CRegistry::DeleteValue(wchar_t const *)

- ea: `0x18002a710`
- end: `0x18002a74f`
- name: `?DeleteValue@CRegistry@@UEAAHPEB_W@Z`
- size: `63`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18002a710`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a73f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a725`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002a73f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a72f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x18002a72f`

## pseudocode

```c
__int64 __fastcall CRegistry::DeleteValue(CRegistry *this, const wchar_t *a2)
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
  v5 = RegDeleteValueW(v2, a2);
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
0x18002a710  sub     rsp, 28h
0x18002a714  mov     rcx, [rcx+0B0h]; hKey
0x18002a71b  test    rcx, rcx
0x18002a71e  jnz     short loc_18002A72F
0x18002a720  mov     ecx, 6; dwErrCode
0x18002a725  call    cs:__imp_SetLastError
0x18002a72b  xor     eax, eax
0x18002a72d  jmp     short loc_18002A74A
0x18002a72f  call    cs:__imp_RegDeleteValueW
0x18002a735  test    eax, eax
0x18002a737  jz      short loc_18002A73D
0x18002a739  mov     ecx, eax
0x18002a73b  jmp     short loc_18002A725
0x18002a73d  xor     ecx, ecx; dwErrCode
0x18002a73f  call    cs:__imp_SetLastError
0x18002a745  mov     eax, 1
0x18002a74a  add     rsp, 28h
0x18002a74e  retn
```
