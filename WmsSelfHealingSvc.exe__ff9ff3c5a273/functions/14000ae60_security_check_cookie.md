# __security_check_cookie

- ea: `0x14000ae60`
- end: `0x14000ae7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001130`
- `0x140001e2c`
- `0x140003218`
- `0x1400036d8`
- `0x140003948`
- `0x140003ab4`
- `0x140003c2c`
- `0x14000404c`
- `0x140004224`
- `0x140004760`
- `0x140005790`
- `0x1400058e8`
- `0x140005bc0`
- `0x1400066f4`
- `0x140006e24`
- `0x140007158`
- `0x1400076e0`
- `0x140008090`
- `0x140008510`
- `0x140008710`
- `0x140008e34`
- `0x140009470`
- `0x14000988c`
- `0x140009cb0`
- `0x14000a61c`
- `0x14000ad44`

## callees

- `0x140001900`
- `0x14000ae60`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x14000ae60  cmp     rcx, cs:__security_cookie
0x14000ae67  jnz     short loc_14000AE79
0x14000ae69  rol     rcx, 10h
0x14000ae6d  test    cx, 0FFFFh
0x14000ae72  jnz     short loc_14000AE75
0x14000ae74  retn
0x14000ae75  ror     rcx, 10h
0x14000ae79  jmp     __report_gsfailure
```
