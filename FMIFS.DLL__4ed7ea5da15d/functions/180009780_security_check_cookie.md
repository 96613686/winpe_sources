# __security_check_cookie

- ea: `0x180009780`
- end: `0x18000979e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180002510`
- `0x180002a80`
- `0x180002e90`
- `0x1800033a0`
- `0x180003550`
- `0x180006940`
- `0x180006d90`
- `0x180007270`
- `0x180007610`
- `0x1800096dc`

## callees

- `0x180004600`
- `0x180009780`

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
0x180009780  cmp     rcx, cs:__security_cookie
0x180009787  jnz     short ReportFailure
0x180009789  rol     rcx, 10h
0x18000978d  test    cx, 0FFFFh
0x180009792  jnz     short RestoreRcx
0x180009794  retn
0x180009795  ror     rcx, 10h
0x180009799  jmp     __report_gsfailure
```
