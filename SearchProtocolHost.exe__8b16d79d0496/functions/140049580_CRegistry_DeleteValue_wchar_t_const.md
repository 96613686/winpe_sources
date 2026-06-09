# CRegistry::DeleteValue(wchar_t const *)

- ea: `0x140049580`
- end: `0x1400495bf`
- name: `?DeleteValue@CRegistry@@UEAAHPEB_W@Z`
- size: `63`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x140049580`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004959f`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x14004959f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400495af`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049595`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400495af`

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
0x140049580  sub     rsp, 28h
0x140049584  mov     rcx, [rcx+0B0h]; hKey
0x14004958b  test    rcx, rcx
0x14004958e  jnz     short loc_14004959F
0x140049590  mov     ecx, 6; dwErrCode
0x140049595  call    cs:__imp_SetLastError
0x14004959b  xor     eax, eax
0x14004959d  jmp     short loc_1400495BA
0x14004959f  call    cs:__imp_RegDeleteValueW
0x1400495a5  test    eax, eax
0x1400495a7  jz      short loc_1400495AD
0x1400495a9  mov     ecx, eax
0x1400495ab  jmp     short loc_140049595
0x1400495ad  xor     ecx, ecx; dwErrCode
0x1400495af  call    cs:__imp_SetLastError
0x1400495b5  mov     eax, 1
0x1400495ba  add     rsp, 28h
0x1400495be  retn
```
