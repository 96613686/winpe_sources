# __security_check_cookie

- ea: `0x180003950`
- end: `0x18000396e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000120c`
- `0x180001ba0`
- `0x180002048`
- `0x1800022a0`
- `0x18000291c`
- `0x180002fac`
- `0x180003878`

## callees

- `0x180003950`
- `0x180003ff0`

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
0x180003950  cmp     rcx, cs:__security_cookie
0x180003957  jnz     short ReportFailure
0x180003959  rol     rcx, 10h
0x18000395d  test    cx, 0FFFFh
0x180003962  jnz     short RestoreRcx
0x180003964  retn
0x180003965  ror     rcx, 10h
0x180003969  jmp     __report_gsfailure
```
