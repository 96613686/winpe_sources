# __security_check_cookie

- ea: `0x180001f70`
- end: `0x180001f8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001e3c`
- `0x180009600`
- `0x180009840`
- `0x18000d50c`
- `0x18000e770`
- `0x180013078`

## callees

- `0x180001010`
- `0x180001f70`

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
0x180001f70  cmp     rcx, cs:__security_cookie
0x180001f77  jnz     short ReportFailure
0x180001f79  rol     rcx, 10h
0x180001f7d  test    cx, 0FFFFh
0x180001f82  jnz     short RestoreRcx
0x180001f84  retn
0x180001f85  ror     rcx, 10h; StackCookie
0x180001f89  jmp     __report_gsfailure
```
