# __security_check_cookie

- ea: `0x180001590`
- end: `0x1800015ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800024dc`
- `0x180002778`
- `0x180002d18`
- `0x1800030bc`
- `0x180003604`
- `0x180003980`
- `0x18000513c`
- `0x1800055f0`
- `0x180005bb0`
- `0x18000608c`

## callees

- `0x180001590`
- `0x180001b80`

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
0x180001590  cmp     rcx, cs:__security_cookie
0x180001597  jnz     short ReportFailure
0x180001599  rol     rcx, 10h
0x18000159d  test    cx, 0FFFFh
0x1800015a2  jnz     short RestoreRcx
0x1800015a4  retn
0x1800015a5  ror     rcx, 10h; StackCookie
0x1800015a9  jmp     __report_gsfailure
```
