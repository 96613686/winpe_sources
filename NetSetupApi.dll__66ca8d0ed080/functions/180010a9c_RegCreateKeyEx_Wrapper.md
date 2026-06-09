# RegCreateKeyEx_Wrapper

- ea: `0x180010a9c`
- end: `0x180010b39`
- name: `RegCreateKeyEx_Wrapper`
- size: `157`
- prototype: `LSTATUS __fastcall(HKEY hKey, __int64, __int64, REGSAM samDesired, int, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800102e8`

## callees

- `0x180010a9c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ae5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010b23`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010ae5`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180010b23`

## pseudocode

```c
LSTATUS __fastcall RegCreateKeyEx_Wrapper(
        HKEY hKey,
        __int64 a2,
        __int64 a3,
        REGSAM samDesired,
        int a5,
        PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegCreateKeyExW(hKey, &word_18001F4EC, 0, 0, 0, samDesired, 0, phkResult, 0);
  if ( result == 5 )
    return RegCreateKeyExW(hKey, &word_18001F4EC, 0, 0, 4u, samDesired, 0, phkResult, 0);
  return result;
}

```

## disassembly

```asm
0x180010a9c  mov     rax, rsp
0x180010a9f  mov     [rax+8], rbx
0x180010aa3  mov     [rax+10h], rsi
0x180010aa7  push    rdi
0x180010aa8  sub     rsp, 50h
0x180010aac  mov     rsi, [rsp+58h+arg_28]
0x180010ab4  lea     rdx, word_18001F4EC; lpSubKey
0x180010abb  mov     qword ptr [rax-18h], 0
0x180010ac3  mov     ebx, r9d
0x180010ac6  mov     [rax-20h], rsi
0x180010aca  xor     r9d, r9d; lpClass
0x180010acd  mov     qword ptr [rax-28h], 0
0x180010ad5  xor     r8d, r8d; Reserved
0x180010ad8  mov     [rax-30h], ebx
0x180010adb  mov     rdi, rcx
0x180010ade  mov     dword ptr [rax-38h], 0
0x180010ae5  call    cs:__imp_RegCreateKeyExW
0x180010aeb  cmp     eax, 5
0x180010aee  jnz     short loc_180010B29
0x180010af0  mov     [rsp+58h+lpdwDisposition], 0; lpdwDisposition
0x180010af9  lea     rdx, word_18001F4EC; lpSubKey
0x180010b00  mov     [rsp+58h+phkResult], rsi; phkResult
0x180010b05  xor     r9d, r9d; lpClass
0x180010b08  mov     [rsp+58h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010b11  xor     r8d, r8d; Reserved
0x180010b14  mov     [rsp+58h+samDesired], ebx; samDesired
0x180010b18  mov     rcx, rdi; hKey
0x180010b1b  mov     [rsp+58h+dwOptions], 4; dwOptions
0x180010b23  call    cs:__imp_RegCreateKeyExW
0x180010b29  mov     rbx, [rsp+58h+arg_0]
0x180010b2e  mov     rsi, [rsp+58h+arg_8]
0x180010b33  add     rsp, 50h
0x180010b37  pop     rdi
0x180010b38  retn
```
