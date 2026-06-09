# FastRegCreateKey(HKEY__ *,ushort const *,HKEY__ * *,ulong)

- ea: `0x1800384ec`
- end: `0x180038549`
- name: `?FastRegCreateKey@@YAJPEAUHKEY__@@PEBGPEAPEAU1@K@Z`
- size: `93`
- prototype: `__int64 __fastcall(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult, REGSAM samDesired)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180038220`
- `0x180038470`
- `0x180040dd4`
- `0x1800591f0`

## callees

- `0x1800384ec`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038541`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180038541`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038509`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180038509`

## pseudocode

```c
LSTATUS __fastcall FastRegCreateKey(HKEY hKey, LPCWSTR lpSubKey, PHKEY phkResult, REGSAM samDesired)
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
0x1800384ec  push    rbx
0x1800384ee  push    rbp
0x1800384ef  push    rsi
0x1800384f0  push    rdi
0x1800384f1  sub     rsp, 58h
0x1800384f5  mov     rdi, r8
0x1800384f8  mov     [rsp+78h+phkResult], r8; phkResult
0x1800384fd  xor     r8d, r8d; ulOptions
0x180038500  mov     ebx, r9d
0x180038503  mov     rsi, rdx
0x180038506  mov     rbp, rcx
0x180038509  call    cs:__imp_RegOpenKeyExW
0x18003850f  xor     ecx, ecx
0x180038511  test    eax, eax
0x180038513  jnz     short loc_18003851E
0x180038515  add     rsp, 58h
0x180038519  pop     rdi
0x18003851a  pop     rsi
0x18003851b  pop     rbp
0x18003851c  pop     rbx
0x18003851d  retn
0x18003851e  mov     [rsp+78h+lpdwDisposition], rcx; lpdwDisposition
0x180038523  xor     r9d, r9d; lpClass
0x180038526  mov     [rsp+78h+var_40], rdi; phkResult
0x18003852b  xor     r8d, r8d; Reserved
0x18003852e  mov     [rsp+78h+lpSecurityAttributes], rcx; lpSecurityAttributes
0x180038533  mov     rdx, rsi; lpSubKey
0x180038536  mov     [rsp+78h+samDesired], ebx; samDesired
0x18003853a  mov     dword ptr [rsp+78h+phkResult], ecx; dwOptions
0x18003853e  mov     rcx, rbp; hKey
0x180038541  call    cs:__imp_RegCreateKeyExW
0x180038547  jmp     short loc_180038515
```
