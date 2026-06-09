# __security_check_cookie

- ea: `0x180003c80`
- end: `0x180003c9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000152c`
- `0x1800017e0`
- `0x180001ad8`
- `0x180005fdc`
- `0x1800064d0`
- `0x18000677c`
- `0x180007778`
- `0x180007940`
- `0x180007cc4`
- `0x18000801c`
- `0x18000989c`
- `0x180009f40`
- `0x18000a0f0`
- `0x18000ad60`
- `0x18000b040`

## callees

- `0x180003c80`
- `0x180004210`

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
0x180003c80  cmp     rcx, cs:__security_cookie
0x180003c87  jnz     short ReportFailure
0x180003c89  rol     rcx, 10h
0x180003c8d  test    cx, 0FFFFh
0x180003c92  jnz     short RestoreRcx
0x180003c94  retn
0x180003c95  ror     rcx, 10h; StackCookie
0x180003c99  jmp     __report_gsfailure
```
