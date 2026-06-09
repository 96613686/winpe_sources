# __security_check_cookie

- ea: `0x180002170`
- end: `0x18000218e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180002efc`
- `0x180003518`
- `0x1800037c4`
- `0x180003e88`
- `0x180004258`
- `0x180004874`
- `0x180004bf0`
- `0x18000659c`
- `0x180006e10`
- `0x180007c8c`
- `0x180008220`
- `0x180008ee4`
- `0x180009790`
- `0x180009b70`
- `0x18000ab88`
- `0x18000ae9c`
- `0x18000bc28`
- `0x18000bf5c`
- `0x18000d5f0`
- `0x18000d98c`
- `0x18000dc14`

## callees

- `0x180002170`
- `0x1800027c0`

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
0x180002170  cmp     rcx, cs:__security_cookie
0x180002177  jnz     short ReportFailure
0x180002179  rol     rcx, 10h
0x18000217d  test    cx, 0FFFFh
0x180002182  jnz     short RestoreRcx
0x180002184  retn
0x180002185  ror     rcx, 10h; StackCookie
0x180002189  jmp     __report_gsfailure
```
