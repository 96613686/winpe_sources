# RegOpenKeyTransacted_Wrapper

- ea: `0x18003ef08`
- end: `0x18003ef82`
- name: `RegOpenKeyTransacted_Wrapper`
- size: `122`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, PHKEY, HANDLE)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006eb0`

## callees

- `0x18003ef08`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003ef42`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003ef7a`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003ef42`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18003ef7a`

## pseudocode

```c
LSTATUS __fastcall RegOpenKeyTransacted_Wrapper(
        HKEY hKey,
        LPCWSTR lpSubKey,
        __int64 a3,
        REGSAM a4,
        PHKEY phkResult,
        HANDLE hTransaction)
{
  LSTATUS result; // eax

  result = RegOpenKeyTransactedW(hKey, lpSubKey, 0, a4, phkResult, hTransaction, 0);
  if ( result == 5 )
    return RegOpenKeyTransactedW(hKey, lpSubKey, 4u, a4, phkResult, hTransaction, 0);
  return result;
}

```

## disassembly

```asm
0x18003ef08  push    rbx
0x18003ef0a  push    rbp
0x18003ef0b  push    rsi
0x18003ef0c  push    rdi
0x18003ef0d  push    r14
0x18003ef0f  sub     rsp, 40h
0x18003ef13  mov     rbp, [rsp+68h+arg_28]
0x18003ef1b  xor     r8d, r8d; ulOptions
0x18003ef1e  mov     r14, [rsp+68h+arg_20]
0x18003ef26  mov     ebx, r9d
0x18003ef29  mov     [rsp+68h+pExtendedParemeter], 0; pExtendedParemeter
0x18003ef32  mov     rdi, rdx
0x18003ef35  mov     [rsp+68h+hTransaction], rbp; hTransaction
0x18003ef3a  mov     rsi, rcx
0x18003ef3d  mov     [rsp+68h+phkResult], r14; phkResult
0x18003ef42  call    cs:__imp_RegOpenKeyTransactedW
0x18003ef48  cmp     eax, 5
0x18003ef4b  jz      short loc_18003EF58
0x18003ef4d  add     rsp, 40h
0x18003ef51  pop     r14
0x18003ef53  pop     rdi
0x18003ef54  pop     rsi
0x18003ef55  pop     rbp
0x18003ef56  pop     rbx
0x18003ef57  retn
0x18003ef58  mov     [rsp+68h+pExtendedParemeter], 0; pExtendedParemeter
0x18003ef61  mov     r9d, ebx; samDesired
0x18003ef64  mov     [rsp+68h+hTransaction], rbp; hTransaction
0x18003ef69  mov     r8d, 4; ulOptions
0x18003ef6f  mov     rdx, rdi; lpSubKey
0x18003ef72  mov     [rsp+68h+phkResult], r14; phkResult
0x18003ef77  mov     rcx, rsi; hKey
0x18003ef7a  call    cs:__imp_RegOpenKeyTransactedW
0x18003ef80  jmp     short loc_18003EF4D
```
