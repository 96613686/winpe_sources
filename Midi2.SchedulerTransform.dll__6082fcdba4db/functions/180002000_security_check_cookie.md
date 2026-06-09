# __security_check_cookie

- ea: `0x180002000`
- end: `0x18000201e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `24`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800017f4`
- `0x180003000`
- `0x180003294`
- `0x180003a88`
- `0x1800041c0`
- `0x1800049f0`
- `0x1800053a4`
- `0x180005720`
- `0x18000639c`
- `0x18000685c`
- `0x1800069ac`
- `0x180006b3c`
- `0x180006d1c`
- `0x180008140`
- `0x18000835c`
- `0x1800085f4`
- `0x180008b00`
- `0x180008dfc`
- `0x1800090b0`
- `0x18000c780`
- `0x18000cb14`

## callees

- `0x180002000`
- `0x180002030`

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
0x180002000  cmp     rcx, cs:__security_cookie
0x180002007  jnz     short ReportFailure
0x180002009  rol     rcx, 10h
0x18000200d  test    cx, 0FFFFh
0x180002012  jnz     short RestoreRcx
0x180002014  retn
0x180002015  ror     rcx, 10h; StackCookie
0x180002019  jmp     __report_gsfailure
```
