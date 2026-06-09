# __security_check_cookie

- ea: `0x140004b90`
- end: `0x140004bae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002904`
- `0x140003668`
- `0x140003adc`
- `0x140004964`
- `0x1400049ac`
- `0x140004a9c`
- `0x140011664`
- `0x140011fb4`
- `0x1400150f0`
- `0x14001bbb4`
- `0x140022a40`
- `0x140022fcc`
- `0x140023dc8`
- `0x140027558`

## callees

- `0x140003490`
- `0x140004b90`

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
0x140004b90  cmp     rcx, cs:__security_cookie
0x140004b97  jnz     short ReportFailure
0x140004b99  rol     rcx, 10h
0x140004b9d  test    cx, 0FFFFh
0x140004ba2  jnz     short RestoreRcx
0x140004ba4  retn
0x140004ba5  ror     rcx, 10h; StackCookie
0x140004ba9  jmp     __report_gsfailure
```
