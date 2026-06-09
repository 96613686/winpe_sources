# __security_check_cookie

- ea: `0x1800018e0`
- end: `0x1800018fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `22`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002bd8`
- `0x180002e74`
- `0x1800036f4`
- `0x180003a98`
- `0x180003e68`
- `0x1800048c4`
- `0x180004c3c`
- `0x180005b1c`
- `0x180006434`
- `0x180007348`
- `0x180007c94`
- `0x1800083d8`
- `0x180008740`
- `0x180008f10`
- `0x180009560`
- `0x1800096e8`
- `0x180009978`
- `0x18000a510`
- `0x18000b0a0`
- `0x18000b49c`
- `0x18001d310`
- `0x18002656c`

## callees

- `0x1800018e0`
- `0x180001ef0`

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
0x1800018e0  cmp     rcx, cs:__security_cookie
0x1800018e7  jnz     short ReportFailure
0x1800018e9  rol     rcx, 10h
0x1800018ed  test    cx, 0FFFFh
0x1800018f2  jnz     short RestoreRcx
0x1800018f4  retn
0x1800018f5  ror     rcx, 10h; StackCookie
0x1800018f9  jmp     __report_gsfailure
```
