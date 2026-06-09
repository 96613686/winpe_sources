# CRegistry::CreateSubKey(wchar_t const *)

- ea: `0x1400492f0`
- end: `0x14004938c`
- name: `?CreateSubKey@CRegistry@@UEAAHPEB_W@Z`
- size: `156`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x1400492f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049366`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140049366`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049353`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140049353`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049316`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004937c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140049316`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14004937c`

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
0x1400492f0  sub     rsp, 58h
0x1400492f4  mov     rcx, [rcx+0B0h]; hKey
0x1400492fb  mov     [rsp+58h+hKey], 0
0x140049304  mov     [rsp+58h+dwDisposition], 0
0x14004930c  test    rcx, rcx
0x14004930f  jnz     short loc_140049320
0x140049311  mov     ecx, 6; dwErrCode
0x140049316  call    cs:__imp_SetLastError
0x14004931c  xor     eax, eax
0x14004931e  jmp     short loc_140049387
0x140049320  lea     rax, [rsp+58h+dwDisposition]
0x140049325  xor     r9d, r9d; lpClass
0x140049328  mov     [rsp+58h+lpdwDisposition], rax; lpdwDisposition
0x14004932d  xor     r8d, r8d; Reserved
0x140049330  lea     rax, [rsp+58h+hKey]
0x140049335  mov     [rsp+58h+phkResult], rax; phkResult
0x14004933a  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140049343  mov     [rsp+58h+samDesired], 0F003Fh; samDesired
0x14004934b  mov     [rsp+58h+dwOptions], 0; dwOptions
0x140049353  call    cs:__imp_RegCreateKeyExW
0x140049359  test    eax, eax
0x14004935b  jz      short loc_140049361
0x14004935d  mov     ecx, eax
0x14004935f  jmp     short loc_140049316
0x140049361  mov     rcx, [rsp+58h+hKey]; hKey
0x140049366  call    cs:__imp_RegCloseKey
0x14004936c  cmp     [rsp+58h+dwDisposition], 2
0x140049371  jnz     short loc_14004937A
0x140049373  mov     ecx, 0B7h
0x140049378  jmp     short loc_140049316
0x14004937a  xor     ecx, ecx; dwErrCode
0x14004937c  call    cs:__imp_SetLastError
0x140049382  mov     eax, 1
0x140049387  add     rsp, 58h
0x14004938b  retn
```
