# __security_check_cookie

- ea: `0x180006600`
- end: `0x18000661e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e00`
- `0x180003200`
- `0x1800048d0`
- `0x180004b1c`
- `0x180005a64`
- `0x180005e2c`
- `0x18000619c`
- `0x180006554`

## callees

- `0x180001860`
- `0x180006600`

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
0x180006600  cmp     rcx, cs:__security_cookie
0x180006607  jnz     short ReportFailure
0x180006609  rol     rcx, 10h
0x18000660d  test    cx, 0FFFFh
0x180006612  jnz     short RestoreRcx
0x180006614  retn
0x180006615  ror     rcx, 10h
0x180006619  jmp     __report_gsfailure
```
