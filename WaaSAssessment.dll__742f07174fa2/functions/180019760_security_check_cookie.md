# __security_check_cookie

- ea: `0x180019760`
- end: `0x18001977e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `66`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180001950`
- `0x180001b2c`
- `0x180001bbc`
- `0x180001d00`
- `0x180002d9c`
- `0x180002eec`
- `0x18000369c`
- `0x180003ef0`
- `0x180004098`
- `0x18000455c`
- `0x18000509c`
- `0x1800053d8`
- `0x180005528`
- `0x1800056b8`
- `0x18000589c`
- `0x180006164`
- `0x18000637c`
- `0x18000669c`
- `0x180007670`
- `0x180007900`
- `0x180007aa0`
- `0x180007b50`
- `0x180008220`
- `0x180008310`
- `0x1800083c0`
- `0x1800086e0`
- `0x1800087d0`
- `0x1800088d0`
- `0x1800089d0`
- `0x18000a684`
- `0x18000a940`
- `0x18000b810`
- `0x18000be48`
- `0x18000c0dc`
- `0x18000c450`
- `0x18000cfac`
- `0x18000f36c`
- `0x18000f728`
- `0x180010100`
- `0x1800114d8`
- `0x180011b50`
- `0x180012e08`
- `0x180012fc8`
- `0x1800138d0`
- `0x180013e70`
- `0x18001428c`

## callees

- `0x180002730`
- `0x180019760`

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
0x180019760  cmp     rcx, cs:__security_cookie
0x180019767  jnz     short ReportFailure
0x180019769  rol     rcx, 10h
0x18001976d  test    cx, 0FFFFh
0x180019772  jnz     short RestoreRcx
0x180019774  retn
0x180019775  ror     rcx, 10h
0x180019779  jmp     __report_gsfailure
```
