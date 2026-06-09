# __security_check_cookie

- ea: `0x1800096b0`
- end: `0x1800096ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d64`
- `0x18000292c`
- `0x180002bdc`
- `0x180003354`
- `0x180003700`
- `0x180003ad8`
- `0x1800043bc`
- `0x180005134`
- `0x1800055b8`
- `0x180005830`
- `0x180006154`
- `0x1800070e4`
- `0x1800078e4`
- `0x180007d80`
- `0x180008460`
- `0x1800089fc`
- `0x180008b80`
- `0x1800095fc`

## callees

- `0x1800019c0`
- `0x1800096b0`

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
0x1800096b0  cmp     rcx, cs:__security_cookie
0x1800096b7  jnz     short ReportFailure
0x1800096b9  rol     rcx, 10h
0x1800096bd  test    cx, 0FFFFh
0x1800096c2  jnz     short RestoreRcx
0x1800096c4  retn
0x1800096c5  ror     rcx, 10h
0x1800096c9  jmp     __report_gsfailure
```
