# CRegistry::DeleteValue(wchar_t const *)

- ea: `0x140028a70`
- end: `0x140028aaf`
- name: `?DeleteValue@CRegistry@@UEAAHPEB_W@Z`
- size: `63`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140028a70`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028a9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028a85`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028a9f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140028a8f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140028a8f`

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
0x140028a70  sub     rsp, 28h
0x140028a74  mov     rcx, [rcx+0B0h]; hKey
0x140028a7b  test    rcx, rcx
0x140028a7e  jnz     short loc_140028A8F
0x140028a80  mov     ecx, 6; dwErrCode
0x140028a85  call    cs:__imp_SetLastError
0x140028a8b  xor     eax, eax
0x140028a8d  jmp     short loc_140028AAA
0x140028a8f  call    cs:__imp_RegDeleteValueW
0x140028a95  test    eax, eax
0x140028a97  jz      short loc_140028A9D
0x140028a99  mov     ecx, eax
0x140028a9b  jmp     short loc_140028A85
0x140028a9d  xor     ecx, ecx; dwErrCode
0x140028a9f  call    cs:__imp_SetLastError
0x140028aa5  mov     eax, 1
0x140028aaa  add     rsp, 28h
0x140028aae  retn
```
