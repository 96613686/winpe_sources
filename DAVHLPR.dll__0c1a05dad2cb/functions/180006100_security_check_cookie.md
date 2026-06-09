# __security_check_cookie

- ea: `0x180006100`
- end: `0x18000611e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001ba0`
- `0x180003180`
- `0x180003300`
- `0x180005a70`
- `0x180006064`

## callees

- `0x180005020`
- `0x180006100`

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
0x180006100  cmp     rcx, cs:__security_cookie
0x180006107  jnz     short ReportFailure
0x180006109  rol     rcx, 10h
0x18000610d  test    cx, 0FFFFh
0x180006112  jnz     short RestoreRcx
0x180006114  retn
0x180006115  ror     rcx, 10h
0x180006119  jmp     __report_gsfailure
```
