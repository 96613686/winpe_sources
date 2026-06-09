# __security_check_cookie

- ea: `0x18000db40`
- end: `0x18000db5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180002180`
- `0x180002240`
- `0x1800029b0`
- `0x180002f10`
- `0x1800041f0`
- `0x180004d70`
- `0x180005200`
- `0x180006990`
- `0x180006e30`
- `0x180008220`
- `0x18000b984`
- `0x18000ba74`
- `0x18000bcf8`
- `0x18000c9f8`
- `0x18000cfa0`
- `0x18000d164`
- `0x18000d748`
- `0x18000d898`
- `0x18000da2c`

## callees

- `0x180007880`
- `0x18000db40`

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
0x18000db40  cmp     rcx, cs:__security_cookie
0x18000db47  jnz     short loc_18000DB59
0x18000db49  rol     rcx, 10h
0x18000db4d  test    cx, 0FFFFh
0x18000db52  jnz     short loc_18000DB55
0x18000db54  retn
0x18000db55  ror     rcx, 10h
0x18000db59  jmp     __report_gsfailure
```
