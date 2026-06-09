# __security_check_cookie

- ea: `0x180001880`
- end: `0x18000189e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022e4`
- `0x180002634`
- `0x18000324c`
- `0x1800033c0`
- `0x180004750`
- `0x180005570`
- `0x180005680`
- `0x1800058d0`
- `0x1800059e0`
- `0x1800066ac`
- `0x180007800`
- `0x180008350`
- `0x180008748`
- `0x180008e60`
- `0x180013480`
- `0x18001d630`
- `0x18001d710`
- `0x18001d7f0`
- `0x18001d8c0`
- `0x18001d990`
- `0x18001da70`
- `0x18001dc60`
- `0x18001ddb0`
- `0x18001f170`
- `0x180020ed0`

## callees

- `0x180001880`
- `0x180001db0`

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
0x180001880  cmp     rcx, cs:__security_cookie
0x180001887  jnz     short ReportFailure
0x180001889  rol     rcx, 10h
0x18000188d  test    cx, 0FFFFh
0x180001892  jnz     short RestoreRcx
0x180001894  retn
0x180001895  ror     rcx, 10h; StackCookie
0x180001899  jmp     __report_gsfailure
```
