# __security_check_cookie

- ea: `0x18000c990`
- end: `0x18000c9ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001560`
- `0x1800028a0`
- `0x1800029cc`
- `0x180002fec`
- `0x180003288`
- `0x180003758`
- `0x180003afc`
- `0x180003f84`
- `0x1800043a0`
- `0x180005218`
- `0x18000570c`
- `0x1800057e8`
- `0x180005c40`
- `0x180006784`
- `0x180006ee0`
- `0x180007a10`
- `0x180008100`
- `0x180008190`
- `0x1800085b0`
- `0x180008ecc`
- `0x1800093e8`
- `0x180009538`
- `0x1800096c8`
- `0x180009884`
- `0x18000a3c4`
- `0x18000abe0`
- `0x18000ac94`
- `0x18000ae3c`
- `0x18000afb0`
- `0x18000b2b0`
- `0x18000b514`
- `0x18000b5dc`
- `0x18000bea8`

## callees

- `0x1800022b0`
- `0x18000c990`

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
0x18000c990  cmp     rcx, cs:__security_cookie
0x18000c997  jnz     short ReportFailure
0x18000c999  rol     rcx, 10h
0x18000c99d  test    cx, 0FFFFh
0x18000c9a2  jnz     short RestoreRcx
0x18000c9a4  retn
0x18000c9a5  ror     rcx, 10h
0x18000c9a9  jmp     __report_gsfailure
```
