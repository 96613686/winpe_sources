# __security_check_cookie

- ea: `0x140047e50`
- end: `0x140047e6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `137`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x140001158`
- `0x140001300`
- `0x1400013ec`
- `0x1400014b0`
- `0x1400031d8`
- `0x140003744`
- `0x140004004`
- `0x140004af0`
- `0x140008838`
- `0x140008918`
- `0x1400099cc`
- `0x14000a660`
- `0x14000b670`
- `0x14000bb48`
- `0x14000c37c`
- `0x14000d49c`
- `0x14000fca8`
- `0x14000ff80`
- `0x1400101d0`
- `0x140010600`
- `0x140011330`
- `0x1400124a0`
- `0x140012a2c`
- `0x140013590`
- `0x1400138d0`
- `0x140014540`
- `0x140014730`
- `0x140014b10`
- `0x140015a40`
- `0x140017aa0`
- `0x140017c80`
- `0x1400193bc`
- `0x14001b47c`
- `0x14001d774`
- `0x14001e250`
- `0x14001f25c`
- `0x14001ffa4`
- `0x140020c18`
- `0x140020ed8`
- `0x140022f4c`
- `0x1400235d8`
- `0x14002561c`
- `0x140025854`
- `0x140025d78`
- `0x140025e40`
- `0x140026048`
- `0x140026698`
- `0x140026e44`
- `0x1400275f0`

## callees

- `0x1400018e0`
- `0x140047e50`

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
0x140047e50  cmp     rcx, cs:__security_cookie
0x140047e57  jnz     short ReportFailure
0x140047e59  rol     rcx, 10h
0x140047e5d  test    cx, 0FFFFh
0x140047e62  jnz     short RestoreRcx
0x140047e64  retn
0x140047e65  ror     rcx, 10h; StackCookie
0x140047e69  jmp     __report_gsfailure
```
