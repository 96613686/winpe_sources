# _anonymous_namespace_::OpenOrCreateRegKey

- ea: `0x14006f28c`
- end: `0x14006f2ea`
- name: `_anonymous_namespace_::OpenOrCreateRegKey`
- size: `94`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, REGSAM samDesired, PHKEY phkResult)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14006f7ac`
- `0x14006f850`

## callees

- `0x14006f28c`

## import_xrefs

- `KERNEL32!RegOpenKeyExW` at `0x14006f2ac`
- `KERNEL32!RegOpenKeyExW` at `0x14006f2ac`
- `KERNEL32!RegCreateKeyExW` at `0x14006f2db`
- `KERNEL32!RegCreateKeyExW` at `0x14006f2db`

## pseudocode

```c
LSTATUS __fastcall anonymous_namespace_::OpenOrCreateRegKey(
        HKEY hKey,
        LPCWSTR lpSubKey,
        REGSAM samDesired,
        PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(hKey, lpSubKey, 0, samDesired, phkResult);
  if ( result )
    return RegCreateKeyExW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, phkResult, 0);
  return result;
}

```

## disassembly

```asm
0x14006f28c  push    rbx
0x14006f28e  push    rbp
0x14006f28f  push    rsi
0x14006f290  push    rdi
0x14006f291  sub     rsp, 58h
0x14006f295  mov     rbx, r9
0x14006f298  mov     edi, r8d
0x14006f29b  mov     r9d, r8d; samDesired
0x14006f29e  mov     [rsp+78h+phkResult], rbx; phkResult
0x14006f2a3  xor     r8d, r8d; ulOptions
0x14006f2a6  mov     rsi, rdx
0x14006f2a9  mov     rbp, rcx
0x14006f2ac  call    cs:__imp_RegOpenKeyExW
0x14006f2b2  xor     ecx, ecx
0x14006f2b4  test    eax, eax
0x14006f2b6  jz      short loc_14006F2E1
0x14006f2b8  mov     [rsp+78h+lpdwDisposition], rcx; lpdwDisposition
0x14006f2bd  xor     r9d, r9d; lpClass
0x14006f2c0  mov     [rsp+78h+var_40], rbx; phkResult
0x14006f2c5  xor     r8d, r8d; Reserved
0x14006f2c8  mov     [rsp+78h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x14006f2cd  mov     rdx, rsi; lpSubKey
0x14006f2d0  mov     [rsp+78h+samDesired], edi; samDesired
0x14006f2d4  mov     dword ptr [rsp+78h+phkResult], ecx; dwOptions
0x14006f2d8  mov     rcx, rbp; hKey
0x14006f2db  call    cs:__imp_RegCreateKeyExW
0x14006f2e1  add     rsp, 58h
0x14006f2e5  pop     rdi
0x14006f2e6  pop     rsi
0x14006f2e7  pop     rbp
0x14006f2e8  pop     rbx
0x14006f2e9  retn
```
