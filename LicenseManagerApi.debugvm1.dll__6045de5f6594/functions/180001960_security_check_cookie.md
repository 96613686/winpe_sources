# __security_check_cookie

- ea: `0x180001960`
- end: `0x18000197e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000110c`
- `0x1800011d4`
- `0x1800028f4`
- `0x180002f64`
- `0x180003214`
- `0x1800037a8`
- `0x180003b10`
- `0x180004074`
- `0x1800043e4`
- `0x180005d2c`
- `0x1800061c0`
- `0x180006378`
- `0x18000640c`
- `0x1800064bc`
- `0x1800065e8`
- `0x180007018`
- `0x1800070d4`
- `0x1800073e8`
- `0x18000762c`
- `0x18000be7c`
- `0x18000e71c`
- `0x18000eaec`
- `0x18000efe0`
- `0x18000f060`
- `0x18000fdd0`
- `0x180010420`
- `0x180010710`
- `0x1800109a0`
- `0x180010cc0`
- `0x180011248`
- `0x1800114a0`
- `0x180011720`
- `0x180011a98`

## callees

- `0x180001960`
- `0x180001f20`

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
0x180001960  cmp     rcx, cs:__security_cookie
0x180001967  jnz     short ReportFailure
0x180001969  rol     rcx, 10h
0x18000196d  test    cx, 0FFFFh
0x180001972  jnz     short RestoreRcx
0x180001974  retn
0x180001975  ror     rcx, 10h; StackCookie
0x180001979  jmp     __report_gsfailure
```
