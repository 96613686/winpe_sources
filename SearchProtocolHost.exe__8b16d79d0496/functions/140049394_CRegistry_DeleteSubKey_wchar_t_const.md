# CRegistry::DeleteSubKey(wchar_t const *)

- ea: `0x140049394`
- end: `0x1400493d9`
- name: `?DeleteSubKey@CRegistry@@QEAAHPEB_W@Z`
- size: `69`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400493e0`

## callees

- `0x140049394`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400493b9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteKeyExW` at `0x1400493b9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400493a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400493c9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400493a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400493c9`

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
0x140049394  sub     rsp, 28h
0x140049398  mov     rcx, [rcx+0B0h]; hKey
0x14004939f  test    rcx, rcx
0x1400493a2  jnz     short loc_1400493B3
0x1400493a4  mov     ecx, 6; dwErrCode
0x1400493a9  call    cs:__imp_SetLastError
0x1400493af  xor     eax, eax
0x1400493b1  jmp     short loc_1400493D4
0x1400493b3  xor     r9d, r9d; Reserved
0x1400493b6  xor     r8d, r8d; samDesired
0x1400493b9  call    cs:__imp_RegDeleteKeyExW
0x1400493bf  test    eax, eax
0x1400493c1  jz      short loc_1400493C7
0x1400493c3  mov     ecx, eax
0x1400493c5  jmp     short loc_1400493A9
0x1400493c7  xor     ecx, ecx; dwErrCode
0x1400493c9  call    cs:__imp_SetLastError
0x1400493cf  mov     eax, 1
0x1400493d4  add     rsp, 28h
0x1400493d8  retn
```
