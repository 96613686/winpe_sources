# __security_check_cookie

- ea: `0x180008a80`
- end: `0x180008a9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001514`
- `0x180001a00`
- `0x180002580`
- `0x180003280`
- `0x180003490`
- `0x180003924`
- `0x180004f04`
- `0x1800053e4`
- `0x180005b00`
- `0x180006670`
- `0x1800070c0`
- `0x180007708`
- `0x180007830`
- `0x180007f2c`
- `0x180009748`

## callees

- `0x180008a80`
- `0x180009040`

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
0x180008a80  cmp     rcx, cs:__security_cookie
0x180008a87  jnz     short ReportFailure
0x180008a89  rol     rcx, 10h
0x180008a8d  test    cx, 0FFFFh
0x180008a92  jnz     short RestoreRcx
0x180008a94  retn
0x180008a95  ror     rcx, 10h; StackCookie
0x180008a99  jmp     __report_gsfailure
```
