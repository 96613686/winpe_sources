# _anonymous_namespace_::CreateOrOpenKey

- ea: `0x180026050`
- end: `0x1800260ac`
- name: `_anonymous_namespace_::CreateOrOpenKey`
- size: `92`
- prototype: `__int64 __fastcall(_DWORD, _DWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180024edc`
- `0x180024fa4`

## callees

- `0x180026050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026099`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180026099`
- `ADVAPI32!RegCreateKeyExW` at `0x180026081`
- `ADVAPI32!RegCreateKeyExW` at `0x180026081`
- `ADVAPI32!RegOpenKeyExW` at `0x180026091`
- `ADVAPI32!RegOpenKeyExW` at `0x180026091`

## pseudocode

```c
HKEY __fastcall anonymous_namespace_::CreateOrOpenKey(HKEY a1, const WCHAR *a2, char a3, REGSAM a4, HKEY phkResult)
{
  LSTATUS v5; // eax

  phkResult = 0;
  if ( a3 )
    v5 = RegCreateKeyExW(a1, a2, 0, 0, 0, a4, 0, &phkResult, 0);
  else
    v5 = RegOpenKeyExW(a1, a2, 0, a4, &phkResult);
  SetLastError(v5);
  return phkResult;
}

```

## disassembly

```asm
0x180026050  mov     r11, rsp
0x180026053  sub     rsp, 58h
0x180026057  xor     r10d, r10d
0x18002605a  lea     rax, [r11+28h]
0x18002605e  mov     [r11+28h], r10
0x180026062  test    r8b, r8b
0x180026065  jz      short loc_180026089
0x180026067  mov     [r11-18h], r10
0x18002606b  xor     r8d, r8d; Reserved
0x18002606e  mov     [r11-20h], rax
0x180026072  mov     [r11-28h], r10
0x180026076  mov     [r11-30h], r9d
0x18002607a  xor     r9d, r9d; lpClass
0x18002607d  mov     [r11-38h], r10d
0x180026081  call    cs:__imp_RegCreateKeyExW
0x180026087  jmp     short loc_180026097
0x180026089  xor     r8d, r8d; ulOptions
0x18002608c  mov     [rsp+58h+phkResult], rax; phkResult
0x180026091  call    cs:__imp_RegOpenKeyExW
0x180026097  mov     ecx, eax; dwErrCode
0x180026099  call    cs:__imp_SetLastError
0x18002609f  mov     rax, [rsp+58h+arg_20]
0x1800260a7  add     rsp, 58h
0x1800260ab  retn
```
