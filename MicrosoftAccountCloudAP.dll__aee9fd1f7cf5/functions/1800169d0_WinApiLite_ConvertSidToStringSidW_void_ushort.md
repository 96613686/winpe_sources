# WinApiLite::ConvertSidToStringSidW(void *,ushort * *)

- ea: `0x1800169d0`
- end: `0x1800169dd`
- name: `?ConvertSidToStringSidW@WinApiLite@@UEAAHPEAXPEAPEAG@Z`
- size: `13`
- prototype: `BOOL __fastcall(WinApiLite *this, void *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800169d6`

## pseudocode

```c
BOOL __fastcall WinApiLite::ConvertSidToStringSidW(WinApiLite *this, void *a2, unsigned __int16 **a3)
{
  return ConvertSidToStringSidW(a2, a3);
}

```

## disassembly

```asm
0x1800169d0  mov     rcx, rdx
0x1800169d3  mov     rdx, r8
0x1800169d6  jmp     cs:__imp_ConvertSidToStringSidW
```
