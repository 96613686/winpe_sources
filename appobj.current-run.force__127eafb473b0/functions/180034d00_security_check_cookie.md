# __security_check_cookie

- ea: `0x180034d00`
- end: `0x180034d1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `145`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005e40`
- `0x1800063c8`
- `0x1800067c8`
- `0x180006a08`
- `0x180006be0`
- `0x18000774c`
- `0x180008160`
- `0x1800082d0`
- `0x1800085a0`
- `0x180008990`
- `0x180008f00`
- `0x180009890`
- `0x180009aac`
- `0x18000a91c`
- `0x18000ab4c`
- `0x18000ad70`
- `0x18000aed4`
- `0x18000b0c0`
- `0x18000b400`
- `0x18000b7c0`
- `0x18000bff0`
- `0x18000c5e0`
- `0x18000c800`
- `0x18000cb80`
- `0x18000cd60`
- `0x18000d360`
- `0x18000d6e0`
- `0x18000dce8`
- `0x18000e27c`
- `0x18000eb40`
- `0x18000f234`
- `0x18000fc84`
- `0x180010200`
- `0x18001042c`
- `0x180010850`
- `0x180010cc0`
- `0x1800113c8`
- `0x180011690`
- `0x180011fe0`
- `0x180012450`
- `0x180012b28`
- `0x180013030`
- `0x180013288`
- `0x180013504`
- `0x180013d88`
- `0x180014010`
- `0x180014690`
- `0x180014a40`
- `0x180015138`
- `0x180015844`

## callees

- `0x1800015b0`
- `0x180034d00`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180034d00  cmp     rcx, cs:__security_cookie
0x180034d07  jnz     short ReportFailure
0x180034d09  rol     rcx, 10h
0x180034d0d  test    cx, 0FFFFh
0x180034d12  jnz     short RestoreRcx
0x180034d14  retn
0x180034d15  ror     rcx, 10h
0x180034d19  jmp     __report_gsfailure
```
