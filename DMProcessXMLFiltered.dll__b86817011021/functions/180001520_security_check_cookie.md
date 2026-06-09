# __security_check_cookie

- ea: `0x180001520`
- end: `0x18000153e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000258c`
- `0x180002bb8`
- `0x180002e64`
- `0x1800034b8`
- `0x180003888`
- `0x180003ab8`
- `0x180003f94`
- `0x180004310`
- `0x180005c6c`
- `0x180006130`
- `0x180006a90`

## callees

- `0x180001520`
- `0x180001ab0`

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
0x180001520  cmp     rcx, cs:__security_cookie
0x180001527  jnz     short ReportFailure
0x180001529  rol     rcx, 10h
0x18000152d  test    cx, 0FFFFh
0x180001532  jnz     short RestoreRcx
0x180001534  retn
0x180001535  ror     rcx, 10h; StackCookie
0x180001539  jmp     __report_gsfailure
```
