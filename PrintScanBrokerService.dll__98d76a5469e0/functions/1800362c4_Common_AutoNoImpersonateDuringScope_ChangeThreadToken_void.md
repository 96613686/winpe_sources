# Common::AutoNoImpersonateDuringScope::ChangeThreadToken(void *)

- ea: `0x1800362c4`
- end: `0x1800362ef`
- name: `?ChangeThreadToken@AutoNoImpersonateDuringScope@Common@@AEAAJPEAX@Z`
- size: `43`
- prototype: `__int64 __fastcall(Common::AutoNoImpersonateDuringScope *__hidden this, void *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800361d0`
- `0x180036a34`

## callees

- `0x1800362c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800362d4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800362ca`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800362ca`

## pseudocode

```c
signed int __fastcall Common::AutoNoImpersonateDuringScope::ChangeThreadToken(
        Common::AutoNoImpersonateDuringScope *this,
        void *a2)
{
  signed int result; // eax

  if ( SetThreadToken(0, a2) )
    return 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x1800362c4  sub     rsp, 28h
0x1800362c8  xor     ecx, ecx; Thread
0x1800362ca  call    cs:__imp_SetThreadToken
0x1800362d0  test    eax, eax
0x1800362d2  jnz     short loc_1800362E8
0x1800362d4  call    cs:__imp_GetLastError
0x1800362da  test    eax, eax
0x1800362dc  jle     short loc_1800362EA
0x1800362de  movzx   eax, ax
0x1800362e1  or      eax, 80070000h
0x1800362e6  jmp     short loc_1800362EA
0x1800362e8  xor     eax, eax
0x1800362ea  add     rsp, 28h
0x1800362ee  retn
```
