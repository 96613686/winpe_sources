# __security_check_cookie

- ea: `0x180022a80`
- end: `0x180022a9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004860`
- `0x1800059c0`
- `0x180007164`
- `0x180009948`
- `0x18000b090`
- `0x18000bd24`
- `0x18000c720`
- `0x18000fed0`
- `0x180010e30`
- `0x1800124c0`
- `0x180013db8`
- `0x180013fb4`
- `0x1800149b0`
- `0x1800153f0`
- `0x180015540`
- `0x1800158e0`
- `0x180016310`
- `0x180016b68`
- `0x180019240`
- `0x18001c530`
- `0x18001db7c`
- `0x180020ca0`
- `0x180022a0c`

## callees

- `0x180022a80`
- `0x180022b40`

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
0x180022a80  cmp     rcx, cs:__security_cookie
0x180022a87  jnz     short ReportFailure
0x180022a89  rol     rcx, 10h
0x180022a8d  test    cx, 0FFFFh
0x180022a92  jnz     short RestoreRcx
0x180022a94  retn
0x180022a95  ror     rcx, 10h; StackCookie
0x180022a99  jmp     __report_gsfailure
```
