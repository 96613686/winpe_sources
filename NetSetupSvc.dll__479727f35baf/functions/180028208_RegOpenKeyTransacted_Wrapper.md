# RegOpenKeyTransacted_Wrapper

- ea: `0x180028208`
- end: `0x18002827e`
- name: `RegOpenKeyTransacted_Wrapper`
- size: `118`
- prototype: `__int64 __usercall@<rax>(HKEY hKey@<rcx>, LPCWSTR lpSubKey@<rdx>, PHKEY, HANDLE)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180027ef4`
- `0x1800285cc`

## callees

- `0x180028208`

## import_xrefs

- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180028242`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002826d`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x180028242`
- `api-ms-win-core-registry-l2-1-0!RegOpenKeyTransactedW` at `0x18002826d`

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
0x180028208  push    rbx
0x18002820a  push    rbp
0x18002820b  push    rsi
0x18002820c  push    rdi
0x18002820d  push    r14
0x18002820f  sub     rsp, 40h
0x180028213  mov     rbp, [rsp+68h+arg_28]
0x18002821b  xor     r8d, r8d; ulOptions
0x18002821e  mov     r14, [rsp+68h+arg_20]
0x180028226  mov     ebx, r9d
0x180028229  mov     [rsp+68h+pExtendedParemeter], 0; pExtendedParemeter
0x180028232  mov     rdi, rdx
0x180028235  mov     [rsp+68h+hTransaction], rbp; hTransaction
0x18002823a  mov     rsi, rcx
0x18002823d  mov     [rsp+68h+phkResult], r14; phkResult
0x180028242  call    cs:__imp_RegOpenKeyTransactedW
0x180028248  cmp     eax, 5
0x18002824b  jnz     short loc_180028273
0x18002824d  mov     [rsp+68h+pExtendedParemeter], 0; pExtendedParemeter
0x180028256  lea     r8d, [rax-1]; ulOptions
0x18002825a  mov     [rsp+68h+hTransaction], rbp; hTransaction
0x18002825f  mov     r9d, ebx; samDesired
0x180028262  mov     rdx, rdi; lpSubKey
0x180028265  mov     [rsp+68h+phkResult], r14; phkResult
0x18002826a  mov     rcx, rsi; hKey
0x18002826d  call    cs:__imp_RegOpenKeyTransactedW
0x180028273  add     rsp, 40h
0x180028277  pop     r14
0x180028279  pop     rdi
0x18002827a  pop     rsi
0x18002827b  pop     rbp
0x18002827c  pop     rbx
0x18002827d  retn
```
