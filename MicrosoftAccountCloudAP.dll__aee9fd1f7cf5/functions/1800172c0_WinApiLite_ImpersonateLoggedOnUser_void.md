# WinApiLite::ImpersonateLoggedOnUser(void *)

- ea: `0x1800172c0`
- end: `0x1800172ca`
- name: `?ImpersonateLoggedOnUser@WinApiLite@@UEAAHPEAX@Z`
- size: `10`
- prototype: `BOOL __fastcall(WinApiLite *this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800172c3`

## pseudocode

```c
BOOL __fastcall WinApiLite::ImpersonateLoggedOnUser(WinApiLite *this, void *a2)
{
  return ImpersonateLoggedOnUser(a2);
}

```

## disassembly

```asm
0x1800172c0  mov     rcx, rdx
0x1800172c3  jmp     cs:__imp_ImpersonateLoggedOnUser
```
