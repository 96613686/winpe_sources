# __security_check_cookie

- ea: `0x14000a390`
- end: `0x14000a3ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `87`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400012a0`
- `0x1400013a8`
- `0x14000142c`
- `0x140001930`
- `0x140002340`
- `0x140002d20`
- `0x140003124`
- `0x14000328c`
- `0x140003e98`
- `0x140004070`
- `0x140004c6c`
- `0x140004d94`
- `0x14000503c`
- `0x140005ba4`
- `0x140005e94`
- `0x14000602c`
- `0x1400060c4`
- `0x14000625c`
- `0x1400062f4`
- `0x14000648c`
- `0x140006524`
- `0x1400066bc`
- `0x140006754`
- `0x1400068ec`
- `0x140006984`
- `0x140006b1c`
- `0x140006bb4`
- `0x140006d4c`
- `0x140006de4`
- `0x140006f7c`
- `0x140007014`
- `0x1400071ac`
- `0x140007244`
- `0x1400073dc`
- `0x140007474`
- `0x14000760c`
- `0x1400076a4`
- `0x14000783c`
- `0x1400078d4`
- `0x140007a6c`
- `0x140007b04`
- `0x140007c9c`
- `0x140007d34`
- `0x140007ecc`
- `0x140007f64`
- `0x1400080fc`
- `0x140008194`
- `0x14000832c`
- `0x1400083c4`
- `0x14000855c`

## callees

- `0x14000a390`
- `0x14000a940`

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
0x14000a390  cmp     rcx, cs:__security_cookie
0x14000a397  jnz     short loc_14000A3A9
0x14000a399  rol     rcx, 10h
0x14000a39d  test    cx, 0FFFFh
0x14000a3a2  jnz     short loc_14000A3A5
0x14000a3a4  retn
0x14000a3a5  ror     rcx, 10h
0x14000a3a9  jmp     __report_gsfailure
```
