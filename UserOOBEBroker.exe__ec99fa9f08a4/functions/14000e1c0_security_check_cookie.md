# __security_check_cookie

- ea: `0x14000e1c0`
- end: `0x14000e1de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013a4`
- `0x140001658`
- `0x1400030f4`
- `0x1400033a0`
- `0x140003960`
- `0x140003d30`
- `0x140004284`
- `0x140004600`
- `0x140005d7c`
- `0x1400068d0`
- `0x140006d90`
- `0x140007690`
- `0x140008710`
- `0x140009900`
- `0x14000a54c`
- `0x14000aba0`
- `0x14000afbc`
- `0x14000b0c8`
- `0x14000ba10`
- `0x14000bdf0`
- `0x14000d8b0`
- `0x14000db08`
- `0x14000e0b4`

## callees

- `0x1400029b0`
- `0x14000e1c0`

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
0x14000e1c0  cmp     rcx, cs:__security_cookie
0x14000e1c7  jnz     short loc_14000E1D9
0x14000e1c9  rol     rcx, 10h
0x14000e1cd  test    cx, 0FFFFh
0x14000e1d2  jnz     short loc_14000E1D5
0x14000e1d4  retn
0x14000e1d5  ror     rcx, 10h
0x14000e1d9  jmp     __report_gsfailure
```
