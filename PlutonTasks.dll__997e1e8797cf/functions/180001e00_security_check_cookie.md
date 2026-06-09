# __security_check_cookie

- ea: `0x180001e00`
- end: `0x180001e1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010a8`
- `0x18000135c`
- `0x180001654`
- `0x180002d90`
- `0x180002e84`
- `0x180003d18`
- `0x180003e80`
- `0x180004084`
- `0x1800044f8`
- `0x1800046e4`
- `0x180004d74`
- `0x180005170`
- `0x18000622c`
- `0x1800066bc`
- `0x180006d98`
- `0x180007354`
- `0x180008284`
- `0x180008ef0`
- `0x1800090f8`
- `0x1800095f8`

## callees

- `0x180001e00`
- `0x180002400`

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
0x180001e00  cmp     rcx, cs:__security_cookie
0x180001e07  jnz     short ReportFailure
0x180001e09  rol     rcx, 10h
0x180001e0d  test    cx, 0FFFFh
0x180001e12  jnz     short RestoreRcx
0x180001e14  retn
0x180001e15  ror     rcx, 10h; StackCookie
0x180001e19  jmp     __report_gsfailure
```
