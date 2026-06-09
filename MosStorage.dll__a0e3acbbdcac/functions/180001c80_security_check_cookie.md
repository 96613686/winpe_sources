# __security_check_cookie

- ea: `0x180001c80`
- end: `0x180001c9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `51`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800033e4`
- `0x180003680`
- `0x180003c14`
- `0x180003fb8`
- `0x180004514`
- `0x180004890`
- `0x1800061bc`
- `0x180006670`
- `0x180006d8c`
- `0x18000733c`
- `0x18000764c`
- `0x18000771c`
- `0x1800078d4`
- `0x1800079d8`
- `0x180007ef8`
- `0x180008374`
- `0x1800083e0`
- `0x180008550`
- `0x180008920`
- `0x180008ac0`
- `0x180008c70`
- `0x180008e70`
- `0x180009010`
- `0x180009220`
- `0x180009590`
- `0x180009650`
- `0x180009790`
- `0x180009ae0`
- `0x180009be0`
- `0x180009cc0`
- `0x18000a684`
- `0x18000a750`
- `0x18000a87c`
- `0x18000a9c0`
- `0x18000af60`
- `0x18000b1d0`
- `0x18000b2dc`
- `0x18000b5a4`
- `0x18000bd8c`
- `0x18000c060`
- `0x18000c9bc`
- `0x18000ca6c`
- `0x18000cb1c`
- `0x18000cbb8`
- `0x18000d6c4`
- `0x18000d8b8`
- `0x18000db14`
- `0x18000dcc8`

## callees

- `0x180001c80`
- `0x180002090`

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
0x180001c80  cmp     rcx, cs:__security_cookie
0x180001c87  jnz     short ReportFailure
0x180001c89  rol     rcx, 10h
0x180001c8d  test    cx, 0FFFFh
0x180001c92  jnz     short RestoreRcx
0x180001c94  retn
0x180001c95  ror     rcx, 10h; StackCookie
0x180001c99  jmp     __report_gsfailure
```
