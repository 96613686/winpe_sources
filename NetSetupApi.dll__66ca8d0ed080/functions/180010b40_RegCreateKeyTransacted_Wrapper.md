# RegCreateKeyTransacted_Wrapper

- ea: `0x180010b40`
- end: `0x180010bf3`
- name: `RegCreateKeyTransacted_Wrapper`
- size: `179`
- prototype: `LSTATUS __fastcall(HKEY hKey, __int64, __int64, REGSAM samDesired, int, PHKEY phkResult, int, HANDLE hTransaction)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1800102e8`

## callees

- `0x180010b40`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010b98`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010be4`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010b98`
- `api-ms-win-core-registry-l2-1-0!RegCreateKeyTransactedW` at `0x180010be4`

## pseudocode

```c
LSTATUS __fastcall RegCreateKeyTransacted_Wrapper(
        HKEY hKey,
        __int64 a2,
        __int64 a3,
        REGSAM samDesired,
        int a5,
        PHKEY phkResult,
        int a7,
        HANDLE hTransaction)
{
  LSTATUS result; // eax

  result = RegCreateKeyTransactedW(hKey, &word_18001F4EC, 0, 0, 0, samDesired, 0, phkResult, 0, hTransaction, 0);
  if ( result == 5 )
    return RegCreateKeyTransactedW(hKey, &word_18001F4EC, 0, 0, 4u, samDesired, 0, phkResult, 0, hTransaction, 0);
  return result;
}

```

## disassembly

```asm
0x180010b40  mov     rax, rsp
0x180010b43  push    rbx
0x180010b44  push    rbp
0x180010b45  push    rsi
0x180010b46  push    rdi
0x180010b47  sub     rsp, 68h
0x180010b4b  mov     rsi, [rsp+88h+arg_38]
0x180010b53  lea     rdx, word_18001F4EC; lpSubKey
0x180010b5a  mov     rbp, [rsp+88h+arg_28]
0x180010b62  mov     ebx, r9d
0x180010b65  mov     qword ptr [rax-38h], 0
0x180010b6d  xor     r9d, r9d; lpClass
0x180010b70  mov     [rax-40h], rsi
0x180010b74  xor     r8d, r8d; Reserved
0x180010b77  mov     qword ptr [rax-48h], 0
0x180010b7f  mov     rdi, rcx
0x180010b82  mov     [rax-50h], rbp
0x180010b86  mov     qword ptr [rax-58h], 0
0x180010b8e  mov     [rax-60h], ebx
0x180010b91  mov     dword ptr [rax-68h], 0
0x180010b98  call    cs:__imp_RegCreateKeyTransactedW
0x180010b9e  cmp     eax, 5
0x180010ba1  jnz     short loc_180010BEA
0x180010ba3  mov     [rsp+88h+pExtendedParemeter], 0; pExtendedParemeter
0x180010bac  lea     rdx, word_18001F4EC; lpSubKey
0x180010bb3  mov     [rsp+88h+hTransaction], rsi; hTransaction
0x180010bb8  xor     r9d, r9d; lpClass
0x180010bbb  mov     [rsp+88h+lpdwDisposition], 0; lpdwDisposition
0x180010bc4  xor     r8d, r8d; Reserved
0x180010bc7  mov     [rsp+88h+phkResult], rbp; phkResult
0x180010bcc  mov     rcx, rdi; hKey
0x180010bcf  mov     [rsp+88h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180010bd8  mov     [rsp+88h+samDesired], ebx; samDesired
0x180010bdc  mov     [rsp+88h+dwOptions], 4; dwOptions
0x180010be4  call    cs:__imp_RegCreateKeyTransactedW
0x180010bea  add     rsp, 68h
0x180010bee  pop     rdi
0x180010bef  pop     rsi
0x180010bf0  pop     rbp
0x180010bf1  pop     rbx
0x180010bf2  retn
```
