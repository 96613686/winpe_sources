# __security_check_cookie

- ea: `0x180001cb0`
- end: `0x180001cce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010c8`
- `0x18000137c`
- `0x1800035cc`
- `0x180003868`
- `0x180003e40`
- `0x180003ff8`
- `0x18000439c`
- `0x1800048e4`
- `0x180004c60`
- `0x180006304`
- `0x180006460`
- `0x1800066d4`
- `0x180006a78`
- `0x180006f80`
- `0x180007018`
- `0x180007150`
- `0x180007518`
- `0x180008390`
- `0x180008a2c`

## callees

- `0x180001cb0`
- `0x180002290`

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
0x180001cb0  cmp     rcx, cs:__security_cookie
0x180001cb7  jnz     short ReportFailure
0x180001cb9  rol     rcx, 10h
0x180001cbd  test    cx, 0FFFFh
0x180001cc2  jnz     short RestoreRcx
0x180001cc4  retn
0x180001cc5  ror     rcx, 10h; StackCookie
0x180001cc9  jmp     __report_gsfailure
```
