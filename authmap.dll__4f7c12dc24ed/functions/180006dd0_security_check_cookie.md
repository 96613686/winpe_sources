# __security_check_cookie

- ea: `0x180006dd0`
- end: `0x180006dee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001da0`
- `0x180003824`
- `0x1800039e4`
- `0x180003d94`
- `0x180003f3c`
- `0x1800041f0`
- `0x180004fc4`
- `0x180005258`
- `0x180005730`
- `0x180005aec`
- `0x18000691c`
- `0x180006d10`

## callees

- `0x180001790`
- `0x180006dd0`

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
0x180006dd0  cmp     rcx, cs:__security_cookie
0x180006dd7  jnz     short ReportFailure
0x180006dd9  rol     rcx, 10h
0x180006ddd  test    cx, 0FFFFh
0x180006de2  jnz     short RestoreRcx
0x180006de4  retn
0x180006de5  ror     rcx, 10h
0x180006de9  jmp     __report_gsfailure
```
