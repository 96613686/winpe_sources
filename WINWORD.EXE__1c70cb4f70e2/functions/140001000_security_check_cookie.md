# __security_check_cookie

- ea: `0x140001000`
- end: `0x14000101e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400011a0`
- `0x140003068`
- `0x140003b74`
- `0x140003e24`
- `0x140003f18`
- `0x140004244`
- `0x1400049bc`
- `0x140004b00`
- `0x140004fe0`
- `0x1400053b0`
- `0x140005490`
- `0x1400055d4`

## callees

- `0x140001000`
- `0x140001d30`

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
0x140001000  cmp     rcx, cs:__security_cookie
0x140001007  jnz     short ReportFailure
0x140001009  rol     rcx, 10h
0x14000100d  test    cx, 0FFFFh
0x140001012  jnz     short RestoreRcx
0x140001014  retn
0x140001015  ror     rcx, 10h
0x140001019  jmp     __report_gsfailure
```
