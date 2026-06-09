# McpManagement::RevertToSelfFromUserImpersonation(void *)

- ea: `0x180024330`
- end: `0x18002435d`
- name: `?RevertToSelfFromUserImpersonation@McpManagement@@YAJPEAX@Z`
- size: `45`
- prototype: `signed int __fastcall(McpManagement *this, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation`

## callees

- `0x180024330`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024342`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024342`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180024338`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180024338`

## pseudocode

```c
signed int __fastcall McpManagement::RevertToSelfFromUserImpersonation(McpManagement *this, void *a2)
{
  signed int result; // eax

  if ( SetThreadToken(0, 0) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180024330  sub     rsp, 28h
0x180024334  xor     edx, edx; Token
0x180024336  xor     ecx, ecx; Thread
0x180024338  call    cs:__imp_SetThreadToken
0x18002433e  test    eax, eax
0x180024340  jnz     short loc_180024356
0x180024342  call    cs:__imp_GetLastError
0x180024348  test    eax, eax
0x18002434a  jle     short loc_180024358
0x18002434c  movzx   eax, ax
0x18002434f  or      eax, 80070000h
0x180024354  jmp     short loc_180024358
0x180024356  xor     eax, eax
0x180024358  add     rsp, 28h
0x18002435c  retn
```
