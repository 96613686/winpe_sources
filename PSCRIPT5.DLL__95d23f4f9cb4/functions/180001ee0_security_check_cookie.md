# __security_check_cookie

- ea: `0x180001ee0`
- end: `0x180001efe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `183`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000123c`
- `0x180001314`
- `0x1800015c8`
- `0x1800029c8`
- `0x180003bcc`
- `0x1800041a0`
- `0x18000540c`
- `0x180006058`
- `0x180009c38`
- `0x180009ee4`
- `0x18000a094`
- `0x18000a488`
- `0x18000a660`
- `0x18000a8a0`
- `0x18000abb0`
- `0x18000bd5c`
- `0x18000ccd4`
- `0x18000ce00`
- `0x18000e4ac`
- `0x18000ee40`
- `0x18000f998`
- `0x18000fcf4`
- `0x18000ff24`
- `0x180010344`
- `0x1800107dc`
- `0x18001265c`
- `0x180012f88`
- `0x18001313c`
- `0x180013bf8`
- `0x180013dbc`
- `0x180015d1c`
- `0x180016b18`
- `0x180016bdc`
- `0x180018328`
- `0x180018720`
- `0x1800199d4`
- `0x18001aa48`
- `0x18001c540`
- `0x18001cbc0`
- `0x18001cea0`
- `0x18001d0ac`
- `0x18001d2d4`
- `0x18001d6e8`
- `0x18001d924`
- `0x18001db1c`
- `0x180020ea0`
- `0x180021330`
- `0x180021424`
- `0x1800229c0`

## callees

- `0x180001ee0`
- `0x180001f10`

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
0x180001ee0  cmp     rcx, cs:__security_cookie
0x180001ee7  jnz     short ReportFailure
0x180001ee9  rol     rcx, 10h
0x180001eed  test    cx, 0FFFFh
0x180001ef2  jnz     short RestoreRcx
0x180001ef4  retn
0x180001ef5  ror     rcx, 10h; StackCookie
0x180001ef9  jmp     __report_gsfailure
```
