# WinApiLite::GetProcessIdOfThread(void *)

- ea: `0x180017170`
- end: `0x18001717a`
- name: `?GetProcessIdOfThread@WinApiLite@@UEAAKPEAX@Z`
- size: `10`
- prototype: `DWORD __fastcall(WinApiLite *this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessIdOfThread` at `0x180017173`

## pseudocode

```c
DWORD __fastcall WinApiLite::GetProcessIdOfThread(WinApiLite *this, void *a2)
{
  return GetProcessIdOfThread(a2);
}

```

## disassembly

```asm
0x180017170  mov     rcx, rdx
0x180017173  jmp     cs:__imp_GetProcessIdOfThread
```
