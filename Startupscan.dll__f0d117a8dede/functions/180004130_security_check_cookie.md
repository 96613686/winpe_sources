# __security_check_cookie

- ea: `0x180004130`
- end: `0x18000414e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fc4`
- `0x1800024c4`
- `0x180002780`
- `0x180002c64`
- `0x180003164`
- `0x180003610`
- `0x180003a28`
- `0x180003cfc`
- `0x180003dec`
- `0x180004084`

## callees

- `0x180001770`
- `0x180004130`

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
0x180004130  cmp     rcx, cs:__security_cookie
0x180004137  jnz     short ReportFailure
0x180004139  rol     rcx, 10h
0x18000413d  test    cx, 0FFFFh
0x180004142  jnz     short RestoreRcx
0x180004144  retn
0x180004145  ror     rcx, 10h
0x180004149  jmp     __report_gsfailure
```
