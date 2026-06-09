# RegOpenKeyEx_Wrapper

- ea: `0x1800052b0`
- end: `0x180005302`
- name: `RegOpenKeyEx_Wrapper`
- size: `82`
- prototype: `LSTATUS __fastcall(HKEY hKey, LPCWSTR lpSubKey, __int64, REGSAM, PHKEY phkResult)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180010c9c`

## callees

- `0x1800052b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052fa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800052fa`

## pseudocode

```c
LSTATUS __fastcall RegOpenKeyEx_Wrapper(HKEY hKey, LPCWSTR lpSubKey, __int64 a3, REGSAM a4, PHKEY phkResult)
{
  LSTATUS result; // eax

  result = RegOpenKeyExW(hKey, lpSubKey, 0, a4, phkResult);
  if ( result == 5 )
    return RegOpenKeyExW(hKey, lpSubKey, 4u, a4, phkResult);
  return result;
}

```

## disassembly

```asm
0x1800052b0  push    rbx
0x1800052b2  push    rbp
0x1800052b3  push    rsi
0x1800052b4  push    rdi
0x1800052b5  sub     rsp, 38h
0x1800052b9  mov     rbp, [rsp+58h+arg_20]
0x1800052c1  xor     r8d, r8d; ulOptions
0x1800052c4  mov     [rsp+58h+phkResult], rbp; phkResult
0x1800052c9  mov     ebx, r9d
0x1800052cc  mov     rdi, rdx
0x1800052cf  mov     rsi, rcx
0x1800052d2  call    cs:__imp_RegOpenKeyExW
0x1800052d8  cmp     eax, 5
0x1800052db  jz      short loc_1800052E6
0x1800052dd  add     rsp, 38h
0x1800052e1  pop     rdi
0x1800052e2  pop     rsi
0x1800052e3  pop     rbp
0x1800052e4  pop     rbx
0x1800052e5  retn
0x1800052e6  mov     r9d, ebx; samDesired
0x1800052e9  mov     [rsp+58h+phkResult], rbp; phkResult
0x1800052ee  mov     r8d, 4; ulOptions
0x1800052f4  mov     rdx, rdi; lpSubKey
0x1800052f7  mov     rcx, rsi; hKey
0x1800052fa  call    cs:__imp_RegOpenKeyExW
0x180005300  jmp     short loc_1800052DD
```
