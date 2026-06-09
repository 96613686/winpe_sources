# __security_check_cookie

- ea: `0x180001440`
- end: `0x18000145e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180001440`
- `0x1800019a0`

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
0x180001440  cmp     rcx, cs:__security_cookie
0x180001447  jnz     short ReportFailure
0x180001449  rol     rcx, 10h
0x18000144d  test    cx, 0FFFFh
0x180001452  jnz     short RestoreRcx
0x180001454  retn
0x180001455  ror     rcx, 10h; StackCookie
0x180001459  jmp     __report_gsfailure
```
