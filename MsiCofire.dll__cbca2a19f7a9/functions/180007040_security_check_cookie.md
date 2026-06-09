# __security_check_cookie

- ea: `0x180007040`
- end: `0x18000705e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002590`
- `0x1800028dc`
- `0x180002a88`
- `0x180002f08`
- `0x1800035f4`
- `0x180003ac8`
- `0x180003ff8`
- `0x18000425c`
- `0x18000465c`
- `0x18000480c`
- `0x180004a70`
- `0x180004bf4`
- `0x180005d44`
- `0x180005ee4`
- `0x180006370`
- `0x180006f40`

## callees

- `0x180001950`
- `0x180007040`

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
0x180007040  cmp     rcx, cs:__security_cookie
0x180007047  jnz     short ReportFailure
0x180007049  rol     rcx, 10h
0x18000704d  test    cx, 0FFFFh
0x180007052  jnz     short RestoreRcx
0x180007054  retn
0x180007055  ror     rcx, 10h
0x180007059  jmp     __report_gsfailure
```
