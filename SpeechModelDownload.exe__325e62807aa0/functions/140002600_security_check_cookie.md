# __security_check_cookie

- ea: `0x140002600`
- end: `0x14000261e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `90`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001360`
- `0x1400013ec`
- `0x14000180c`
- `0x140001968`
- `0x140001c2c`
- `0x1400036e8`
- `0x140003840`
- `0x140003954`
- `0x140003b10`
- `0x14000438c`
- `0x140004620`
- `0x140005150`
- `0x140005668`
- `0x140005740`
- `0x1400059c4`
- `0x140005bfc`
- `0x140005ea0`
- `0x140006464`
- `0x140006994`
- `0x14000732c`
- `0x1400078fc`
- `0x140008f5c`
- `0x1400094e0`
- `0x14000985c`
- `0x140009fec`
- `0x14000a84c`
- `0x14000a930`
- `0x14000aa08`
- `0x14000aaec`
- `0x14000ad94`
- `0x14000ae78`
- `0x14000b964`
- `0x14000be9c`
- `0x14000bf74`
- `0x14000c04c`
- `0x14000c124`
- `0x14000c1fc`
- `0x14000c2d4`
- `0x14000c5f0`
- `0x14000c948`
- `0x14000cd18`
- `0x14000d5a4`
- `0x14000d890`
- `0x14000dd4c`
- `0x14000df48`
- `0x14000e144`
- `0x14000e8d8`
- `0x14000ea08`

## callees

- `0x140002600`
- `0x140002bf0`

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
0x140002600  cmp     rcx, cs:__security_cookie
0x140002607  jnz     short loc_140002619
0x140002609  rol     rcx, 10h
0x14000260d  test    cx, 0FFFFh
0x140002612  jnz     short loc_140002615
0x140002614  retn
0x140002615  ror     rcx, 10h; StackCookie
0x140002619  jmp     __report_gsfailure
```
