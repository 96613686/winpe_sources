# __security_check_cookie

- ea: `0x180001540`
- end: `0x18000155e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x1800014d0`

## callees

- `0x180001540`
- `0x180001ba0`

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
0x180001540  cmp     rcx, cs:__security_cookie
0x180001547  jnz     short ReportFailure
0x180001549  rol     rcx, 10h
0x18000154d  test    cx, 0FFFFh
0x180001552  jnz     short RestoreRcx
0x180001554  retn
0x180001555  ror     rcx, 10h
0x180001559  jmp     __report_gsfailure
```
