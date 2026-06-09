# __security_check_cookie

- ea: `0x180008c50`
- end: `0x180008c6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027c0`
- `0x18000301c`
- `0x18000314c`
- `0x1800032f0`
- `0x1800043ec`
- `0x180004528`
- `0x1800048fc`
- `0x180004b0c`
- `0x180004d98`
- `0x180005110`
- `0x180005b48`
- `0x1800068b0`
- `0x180006ad0`
- `0x180006ed8`
- `0x1800076e0`
- `0x18000885c`
- `0x180008a10`
- `0x180008b40`

## callees

- `0x180001880`
- `0x180008c50`

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
0x180008c50  cmp     rcx, cs:__security_cookie
0x180008c57  jnz     short ReportFailure
0x180008c59  rol     rcx, 10h
0x180008c5d  test    cx, 0FFFFh
0x180008c62  jnz     short RestoreRcx
0x180008c64  retn
0x180008c65  ror     rcx, 10h
0x180008c69  jmp     __report_gsfailure
```
