# __security_check_cookie

- ea: `0x140051ba0`
- end: `0x140051bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `351`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001000`
- `0x1400010a0`
- `0x140001158`
- `0x140001230`
- `0x1400014ec`
- `0x140001800`
- `0x140001960`
- `0x140001a14`
- `0x140001b3c`
- `0x140001c3c`
- `0x140001d38`
- `0x140001e6c`
- `0x140001f8c`
- `0x140002088`
- `0x1400021a8`
- `0x1400023b0`
- `0x14000246c`
- `0x14000254c`
- `0x14000264c`
- `0x140002724`
- `0x140002844`
- `0x1400028f8`
- `0x140002994`
- `0x140002ab8`
- `0x140002bb4`
- `0x140002d44`
- `0x140002e28`
- `0x140002efc`
- `0x140002ff8`
- `0x140003338`
- `0x14000346c`
- `0x140003590`
- `0x140003648`
- `0x140003748`
- `0x140003a68`
- `0x140003b88`
- `0x140003ccc`
- `0x140003dec`
- `0x140003ee8`
- `0x140004124`
- `0x140004248`
- `0x140004368`
- `0x140004464`
- `0x140004584`
- `0x1400046a4`
- `0x1400047d8`
- `0x140004920`
- `0x140004a78`
- `0x140004b98`
- `0x140004cb4`

## callees

- `0x140051ba0`
- `0x140052340`

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
0x140051ba0  cmp     rcx, cs:__security_cookie
0x140051ba7  jnz     short ReportFailure
0x140051ba9  rol     rcx, 10h
0x140051bad  test    cx, 0FFFFh
0x140051bb2  jnz     short RestoreRcx
0x140051bb4  retn
0x140051bb5  ror     rcx, 10h; StackCookie
0x140051bb9  jmp     __report_gsfailure
```
