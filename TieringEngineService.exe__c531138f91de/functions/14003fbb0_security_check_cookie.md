# __security_check_cookie

- ea: `0x14003fbb0`
- end: `0x14003fbce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `85`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000112c`
- `0x140001244`
- `0x14000136c`
- `0x14000148c`
- `0x1400015d8`
- `0x140001714`
- `0x14000256c`
- `0x140003e38`
- `0x140004b94`
- `0x140005954`
- `0x140005db4`
- `0x140006720`
- `0x14000761c`
- `0x140007954`
- `0x140007c90`
- `0x140008c04`
- `0x140008e04`
- `0x14000a03c`
- `0x14000a560`
- `0x14000a700`
- `0x14000aae8`
- `0x14000acac`
- `0x14000b0d0`
- `0x14000d804`
- `0x14000e6c0`
- `0x14000ea7c`
- `0x1400100a0`
- `0x140011b70`
- `0x1400127dc`
- `0x140014fe4`
- `0x140015ff0`
- `0x140016d18`
- `0x1400188e8`
- `0x140019ad8`
- `0x140019e70`
- `0x14001a270`
- `0x14001b328`
- `0x14001c094`
- `0x14001d058`
- `0x14001d960`
- `0x14001e2e0`
- `0x14001effc`
- `0x14001f744`
- `0x14001f874`
- `0x14001fca0`
- `0x140020390`
- `0x140020c6c`
- `0x1400211a4`
- `0x140021a28`
- `0x140022878`

## callees

- `0x140002370`
- `0x14003fbb0`

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
0x14003fbb0  cmp     rcx, cs:__security_cookie
0x14003fbb7  jnz     short loc_14003FBC9
0x14003fbb9  rol     rcx, 10h
0x14003fbbd  test    cx, 0FFFFh
0x14003fbc2  jnz     short loc_14003FBC5
0x14003fbc4  retn
0x14003fbc5  ror     rcx, 10h
0x14003fbc9  jmp     __report_gsfailure
```
