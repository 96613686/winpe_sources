# McpManagement::ImpersonateUser(void *)

- ea: `0x1800242f0`
- end: `0x18002431e`
- name: `?ImpersonateUser@McpManagement@@YAJPEAX@Z`
- size: `46`
- prototype: `signed int __fastcall(HANDLE Token, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x1800242f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024303`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024303`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800242f9`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800242f9`

## pseudocode

```c
signed int __fastcall McpManagement::ImpersonateUser(HANDLE Token, void *a2)
{
  signed int result; // eax

  if ( SetThreadToken(0, Token) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800242f0  sub     rsp, 28h
0x1800242f4  mov     rdx, rcx; Token
0x1800242f7  xor     ecx, ecx; Thread
0x1800242f9  call    cs:__imp_SetThreadToken
0x1800242ff  test    eax, eax
0x180024301  jnz     short loc_180024317
0x180024303  call    cs:__imp_GetLastError
0x180024309  test    eax, eax
0x18002430b  jle     short loc_180024319
0x18002430d  movzx   eax, ax
0x180024310  or      eax, 80070000h
0x180024315  jmp     short loc_180024319
0x180024317  xor     eax, eax
0x180024319  add     rsp, 28h
0x18002431d  retn
```
