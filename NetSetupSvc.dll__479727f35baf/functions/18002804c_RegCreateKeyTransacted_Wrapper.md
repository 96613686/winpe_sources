# RegCreateKeyTransacted_Wrapper

- ea: `0x18002804c`
- end: `0x1800280fb`
- name: `RegCreateKeyTransacted_Wrapper`
- size: `175`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, int, PHKEY, int, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180026a10`

## callees

- `0x18002804c`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800280a2`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800280ea`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800280a2`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x1800280ea`

## pseudocode

```c
LSTATUS __fastcall RegCreateKeyTransacted_Wrapper(
        HKEY hKey,
        LPCWSTR lpSubKey,
        __int64 a3,
        REGSAM samDesired,
        int a5,
        PHKEY phkResult,
        int a7,
        HANDLE hTransaction)
{
  LSTATUS result; // eax

  result = RegCreateKeyTransactedW(hKey, lpSubKey, 0, 0, 0, samDesired, 0, phkResult, 0, hTransaction, 0);
  if ( result == 5 )
    return RegCreateKeyTransactedW(hKey, lpSubKey, 0, 0, 4u, samDesired, 0, phkResult, 0, hTransaction, 0);
  return result;
}

```

## disassembly

```asm
0x18002804c  mov     rax, rsp
0x18002804f  push    rbx
0x180028050  push    rbp
0x180028051  push    rsi
0x180028052  push    rdi
0x180028053  push    r14
0x180028055  sub     rsp, 60h
0x180028059  mov     rbp, [rsp+88h+arg_38]
0x180028061  mov     ebx, r9d
0x180028064  mov     r14, [rsp+88h+arg_28]
0x18002806c  xor     r9d, r9d; lpClass
0x18002806f  mov     qword ptr [rax-38h], 0
0x180028077  xor     r8d, r8d; Reserved
0x18002807a  mov     [rax-40h], rbp
0x18002807e  mov     rdi, rdx
0x180028081  mov     qword ptr [rax-48h], 0
0x180028089  mov     rsi, rcx
0x18002808c  mov     [rax-50h], r14
0x180028090  mov     qword ptr [rax-58h], 0
0x180028098  mov     [rax-60h], ebx
0x18002809b  mov     dword ptr [rax-68h], 0
0x1800280a2  call    cs:__imp_RegCreateKeyTransactedW
0x1800280a8  cmp     eax, 5
0x1800280ab  jnz     short loc_1800280F0
0x1800280ad  mov     [rsp+88h+pExtendedParemeter], 0; pExtendedParemeter
0x1800280b6  xor     r9d, r9d; lpClass
0x1800280b9  mov     [rsp+88h+hTransaction], rbp; hTransaction
0x1800280be  xor     r8d, r8d; Reserved
0x1800280c1  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x1800280ca  mov     rdx, rdi; lpSubKey
0x1800280cd  mov     [rsp+88h+phkResult], r14; phkResult
0x1800280d2  mov     rcx, rsi; hKey
0x1800280d5  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x1800280de  mov     [rsp+88h+samDesired], ebx; samDesired
0x1800280e2  mov     [rsp+88h+dwOptions], 4; dwOptions
0x1800280ea  call    cs:__imp_RegCreateKeyTransactedW
0x1800280f0  add     rsp, 60h
0x1800280f4  pop     r14
0x1800280f6  pop     rdi
0x1800280f7  pop     rsi
0x1800280f8  pop     rbp
0x1800280f9  pop     rbx
0x1800280fa  retn
```
