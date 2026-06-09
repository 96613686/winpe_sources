# __security_check_cookie

- ea: `0x180001d60`
- end: `0x180001d7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001124`
- `0x1800013d8`
- `0x1800016d0`
- `0x180002f58`
- `0x180003640`
- `0x1800038d4`
- `0x1800049b4`
- `0x1800069a0`
- `0x180007bc0`
- `0x180008b68`
- `0x1800092a8`
- `0x180009af8`
- `0x180009d80`
- `0x180009fc0`
- `0x18000a158`
- `0x18000a1b8`
- `0x18000a730`

## callees

- `0x180001d60`
- `0x180002350`

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
0x180001d60  cmp     rcx, cs:__security_cookie
0x180001d67  jnz     short ReportFailure
0x180001d69  rol     rcx, 10h
0x180001d6d  test    cx, 0FFFFh
0x180001d72  jnz     short RestoreRcx
0x180001d74  retn
0x180001d75  ror     rcx, 10h; StackCookie
0x180001d79  jmp     __report_gsfailure
```
