# __security_check_cookie

- ea: `0x180003ef0`
- end: `0x180003f0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ad8`
- `0x180003a60`
- `0x180003e60`

## callees

- `0x180001790`
- `0x180003ef0`

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
0x180003ef0  cmp     rcx, cs:__security_cookie
0x180003ef7  jnz     short ReportFailure
0x180003ef9  rol     rcx, 10h
0x180003efd  test    cx, 0FFFFh
0x180003f02  jnz     short RestoreRcx
0x180003f04  retn
0x180003f05  ror     rcx, 10h
0x180003f09  jmp     __report_gsfailure
```
