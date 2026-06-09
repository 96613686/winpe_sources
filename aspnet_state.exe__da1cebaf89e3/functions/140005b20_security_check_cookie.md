# __security_check_cookie

- ea: `0x140005b20`
- end: `0x140005b3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001d04`
- `0x140001de4`
- `0x140001f74`
- `0x14000248c`
- `0x140002950`
- `0x140002a78`
- `0x140002f14`
- `0x140003f98`
- `0x14000505c`
- `0x1400055fc`
- `0x140005ab4`

## callees

- `0x140005b20`
- `0x140006190`

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
0x140005b20  cmp     rcx, cs:__security_cookie
0x140005b27  jnz     short ReportFailure
0x140005b29  rol     rcx, 10h
0x140005b2d  test    cx, 0FFFFh
0x140005b32  jnz     short RestoreRcx
0x140005b34  retn
0x140005b35  ror     rcx, 10h
0x140005b39  jmp     __report_gsfailure
```
