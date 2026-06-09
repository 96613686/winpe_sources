# __security_check_cookie

- ea: `0x140001350`
- end: `0x14000136e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a84`
- `0x140003198`
- `0x140006278`
- `0x1400069b4`
- `0x1400072c8`
- `0x14000786c`
- `0x140008e18`
- `0x14000a65c`
- `0x14000aa50`
- `0x14000ade8`
- `0x14000b67c`
- `0x14000bb10`
- `0x14000bc18`
- `0x14000bd34`
- `0x14000cd6c`

## callees

- `0x140001350`
- `0x1400019c0`

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
0x140001350  cmp     rcx, cs:__security_cookie
0x140001357  jnz     short ReportFailure
0x140001359  rol     rcx, 10h
0x14000135d  test    cx, 0FFFFh
0x140001362  jnz     short RestoreRcx
0x140001364  retn
0x140001365  ror     rcx, 10h; StackCookie
0x140001369  jmp     __report_gsfailure
```
