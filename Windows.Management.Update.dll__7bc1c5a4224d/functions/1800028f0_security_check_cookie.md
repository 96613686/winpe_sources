# __security_check_cookie

- ea: `0x1800028f0`
- end: `0x18000290e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x18000207c`
- `0x180002d88`
- `0x180004ce0`
- `0x1800050b0`
- `0x180006b10`
- `0x1800079a0`
- `0x180007b00`
- `0x180007c70`
- `0x180007fa0`
- `0x18000903c`
- `0x1800092d8`
- `0x180009858`
- `0x18000a1f8`
- `0x18000a59c`
- `0x18000a96c`
- `0x18000aeb0`
- `0x18000b974`
- `0x18000bcf0`
- `0x18000cea4`
- `0x18000cfb0`
- `0x18000d9bc`
- `0x18000f2cc`
- `0x18000fda0`
- `0x18000fec8`
- `0x180010198`
- `0x180013854`
- `0x180018440`
- `0x18001bf00`
- `0x18001d738`
- `0x1800201f0`
- `0x18002113c`
- `0x180021398`
- `0x1800215a0`
- `0x180021874`
- `0x180021e90`
- `0x1800220ac`
- `0x180022478`
- `0x180022590`
- `0x180022dc4`
- `0x18002333c`
- `0x1800235a4`
- `0x1800236ec`
- `0x180025290`
- `0x180026778`

## callees

- `0x1800028f0`
- `0x180002fe0`

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
0x1800028f0  cmp     rcx, cs:__security_cookie
0x1800028f7  jnz     short ReportFailure
0x1800028f9  rol     rcx, 10h
0x1800028fd  test    cx, 0FFFFh
0x180002902  jnz     short RestoreRcx
0x180002904  retn
0x180002905  ror     rcx, 10h; StackCookie
0x180002909  jmp     __report_gsfailure
```
