# __security_check_cookie

- ea: `0x1800018f0`
- end: `0x18000190e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010c8`
- `0x180001144`
- `0x18001b048`
- `0x18001b45c`
- `0x18001bc80`
- `0x18001bf50`
- `0x18001cce0`
- `0x18001ce80`
- `0x18001d5a0`
- `0x18001d738`
- `0x18001d860`
- `0x18001dbc0`
- `0x18001dc40`
- `0x18001dcc0`
- `0x18001dda0`
- `0x18001dfc0`
- `0x18001e360`
- `0x18001f49c`
- `0x18001fcb0`
- `0x180020b20`
- `0x180020f48`
- `0x180021098`
- `0x180021228`
- `0x18002140c`
- `0x180021de8`
- `0x180021f9c`
- `0x1800222c4`
- `0x1800227f0`
- `0x1800229c0`
- `0x180022d68`

## callees

- `0x1800018f0`
- `0x180001920`

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
0x1800018f0  cmp     rcx, cs:__security_cookie
0x1800018f7  jnz     short ReportFailure
0x1800018f9  rol     rcx, 10h
0x1800018fd  test    cx, 0FFFFh
0x180001902  jnz     short RestoreRcx
0x180001904  retn
0x180001905  ror     rcx, 10h; StackCookie
0x180001909  jmp     __report_gsfailure
```
