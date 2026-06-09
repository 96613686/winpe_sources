# WinApiLite::IsValidSid(void *)

- ea: `0x1800172d0`
- end: `0x1800172da`
- name: `?IsValidSid@WinApiLite@@UEAAHPEAX@Z`
- size: `10`
- prototype: `BOOL __fastcall(WinApiLite *this, void *)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x1800172d3`

## pseudocode

```c
BOOL __fastcall WinApiLite::IsValidSid(WinApiLite *this, void *a2)
{
  return IsValidSid(a2);
}

```

## disassembly

```asm
0x1800172d0  mov     rcx, rdx
0x1800172d3  jmp     cs:__imp_IsValidSid
```
