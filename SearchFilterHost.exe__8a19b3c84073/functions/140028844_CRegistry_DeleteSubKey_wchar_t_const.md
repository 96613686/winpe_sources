# CRegistry::DeleteSubKey(wchar_t const *)

- ea: `0x140028844`
- end: `0x140028889`
- name: `?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z`
- size: `69`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140028890`

## callees

- `0x140028844`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028879`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028859`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140028879`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140028869`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x140028869`

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
0x140028844  sub     rsp, 28h
0x140028848  mov     rcx, [rcx+0B0h]; hKey
0x14002884f  test    rcx, rcx
0x140028852  jnz     short loc_140028863
0x140028854  mov     ecx, 6; dwErrCode
0x140028859  call    cs:__imp_SetLastError
0x14002885f  xor     eax, eax
0x140028861  jmp     short loc_140028884
0x140028863  xor     r9d, r9d; Reserved
0x140028866  xor     r8d, r8d; samDesired
0x140028869  call    cs:__imp_RegDeleteKeyExW
0x14002886f  test    eax, eax
0x140028871  jz      short loc_140028877
0x140028873  mov     ecx, eax
0x140028875  jmp     short loc_140028859
0x140028877  xor     ecx, ecx; dwErrCode
0x140028879  call    cs:__imp_SetLastError
0x14002887f  mov     eax, 1
0x140028884  add     rsp, 28h
0x140028888  retn
```
