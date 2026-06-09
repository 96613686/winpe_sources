# WinApiLite::GetComputerNameW(ushort *,ulong *)

- ea: `0x180016f40`
- end: `0x180016f4d`
- name: `?GetComputerNameW@WinApiLite@@UEAAHPEAGPEAK@Z`
- size: `13`
- prototype: `BOOL __fastcall(WinApiLite *this, unsigned __int16 *, unsigned int *)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetComputerNameW` at `0x180016f46`

## pseudocode

```c
BOOL __fastcall WinApiLite::GetComputerNameW(WinApiLite *this, unsigned __int16 *a2, unsigned int *a3)
{
  return GetComputerNameW(a2, a3);
}

```

## disassembly

```asm
0x180016f40  mov     rcx, rdx
0x180016f43  mov     rdx, r8
0x180016f46  jmp     cs:__imp_GetComputerNameW
```
