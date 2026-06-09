# __security_check_cookie

- ea: `0x180001e60`
- end: `0x180001e7e`
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
- `0x180002e60`
- `0x1800030f4`
- `0x1800038e8`
- `0x180004020`
- `0x180004850`
- `0x180005204`
- `0x180005580`
- `0x1800061fc`
- `0x1800066bc`
- `0x18000680c`
- `0x18000699c`
- `0x180006b7c`
- `0x180007f90`
- `0x1800081ac`
- `0x180008444`
- `0x180008950`
- `0x180008c4c`
- `0x180008f00`
- `0x180009fb0`
- `0x18000a980`
- `0x18000b2ac`

## callees

- `0x180001e60`
- `0x180001e90`

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
0x180001e60  cmp     rcx, cs:__security_cookie
0x180001e67  jnz     short ReportFailure
0x180001e69  rol     rcx, 10h
0x180001e6d  test    cx, 0FFFFh
0x180001e72  jnz     short RestoreRcx
0x180001e74  retn
0x180001e75  ror     rcx, 10h; StackCookie
0x180001e79  jmp     __report_gsfailure
```
