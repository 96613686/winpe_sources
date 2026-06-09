# __security_check_cookie

- ea: `0x140009d00`
- end: `0x140009d1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000104c`
- `0x14000110c`
- `0x1400021bc`
- `0x140002338`
- `0x14000289c`
- `0x140002b44`
- `0x140003874`
- `0x140003b00`
- `0x1400044e4`
- `0x1400048b8`
- `0x140004d3c`
- `0x140005e44`
- `0x140006e34`
- `0x140008480`
- `0x140008694`
- `0x140009938`
- `0x140009bec`

## callees

- `0x140001c10`
- `0x140009d00`

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
0x140009d00  cmp     rcx, cs:__security_cookie
0x140009d07  jnz     short loc_140009D19
0x140009d09  rol     rcx, 10h
0x140009d0d  test    cx, 0FFFFh
0x140009d12  jnz     short loc_140009D15
0x140009d14  retn
0x140009d15  ror     rcx, 10h
0x140009d19  jmp     __report_gsfailure
```
