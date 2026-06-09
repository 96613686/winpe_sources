# __security_check_cookie

- ea: `0x1800051c0`
- end: `0x1800051de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cdc`
- `0x180001e9c`
- `0x18000228c`
- `0x180002474`
- `0x180002fd0`
- `0x1800031bc`
- `0x1800032fc`
- `0x1800038dc`
- `0x180003f00`
- `0x1800040a8`
- `0x1800043d8`
- `0x180004434`
- `0x1800044f4`
- `0x1800045cc`
- `0x18000466c`
- `0x180004788`
- `0x1800049d0`
- `0x180004af4`
- `0x180004ca4`
- `0x180004ef4`
- `0x180005100`

## callees

- `0x180001780`
- `0x1800051c0`

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
0x1800051c0  cmp     rcx, cs:__security_cookie
0x1800051c7  jnz     short ReportFailure
0x1800051c9  rol     rcx, 10h
0x1800051cd  test    cx, 0FFFFh
0x1800051d2  jnz     short RestoreRcx
0x1800051d4  retn
0x1800051d5  ror     rcx, 10h
0x1800051d9  jmp     __report_gsfailure
```
