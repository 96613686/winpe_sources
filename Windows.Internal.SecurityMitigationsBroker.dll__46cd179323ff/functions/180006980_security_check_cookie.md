# __security_check_cookie

- ea: `0x180006980`
- end: `0x18000699e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180002288`
- `0x1800026f4`
- `0x180002d70`
- `0x180003060`
- `0x180003278`
- `0x180003484`
- `0x180003850`
- `0x18000448c`
- `0x1800045f0`
- `0x180004d64`
- `0x180005020`
- `0x180006360`
- `0x1800068e0`

## callees

- `0x180001ba0`
- `0x180006980`

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
0x180006980  cmp     rcx, cs:__security_cookie
0x180006987  jnz     short ReportFailure
0x180006989  rol     rcx, 10h
0x18000698d  test    cx, 0FFFFh
0x180006992  jnz     short RestoreRcx
0x180006994  retn
0x180006995  ror     rcx, 10h
0x180006999  jmp     __report_gsfailure
```
