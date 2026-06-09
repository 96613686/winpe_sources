# _anonymous_namespace_::CreateOrOpenKey

- ea: `0x18004daa4`
- end: `0x18004db00`
- name: `_anonymous_namespace_::CreateOrOpenKey`
- size: `92`
- prototype: `HKEY __fastcall(HKEY, const WCHAR *, char, REGSAM, HKEY phkResult)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800118a4`
- `0x18004ce94`
- `0x18004cf5c`

## callees

- `0x18004daa4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004daed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004daed`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dae5`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18004dae5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004dad5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x18004dad5`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x18004daa4  mov     r11, rsp
0x18004daa7  sub     rsp, 58h
0x18004daab  xor     r10d, r10d
0x18004daae  lea     rax, [r11+28h]
0x18004dab2  mov     [r11+28h], r10
0x18004dab6  test    r8b, r8b
0x18004dab9  jz      short loc_18004DADD
0x18004dabb  mov     [r11-18h], r10
0x18004dabf  xor     r8d, r8d; Reserved
0x18004dac2  mov     [r11-20h], rax
0x18004dac6  mov     [r11-28h], r10
0x18004daca  mov     [r11-30h], r9d
0x18004dace  xor     r9d, r9d; lpClass
0x18004dad1  mov     [r11-38h], r10d
0x18004dad5  call    cs:__imp_RegCreateKeyExW
0x18004dadb  jmp     short loc_18004DAEB
0x18004dadd  xor     r8d, r8d; ulOptions
0x18004dae0  mov     [rsp+58h+phkResult], rax; phkResult
0x18004dae5  call    cs:__imp_RegOpenKeyExW
0x18004daeb  mov     ecx, eax; dwErrCode
0x18004daed  call    cs:__imp_SetLastError
0x18004daf3  mov     rax, [rsp+58h+arg_20]
0x18004dafb  add     rsp, 58h
0x18004daff  retn
```
