# __security_check_cookie

- ea: `0x140026650`
- end: `0x14002666e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `91`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010ac`
- `0x140001bc8`
- `0x140002a00`
- `0x140002f14`
- `0x140003690`
- `0x140003a48`
- `0x140003d30`
- `0x140004080`
- `0x140004e98`
- `0x140004f9c`
- `0x1400052bc`
- `0x1400058e4`
- `0x140005e18`
- `0x1400065a0`
- `0x140006844`
- `0x140006cd8`
- `0x140007c10`
- `0x140007cdc`
- `0x140008400`
- `0x140008694`
- `0x140008844`
- `0x140009658`
- `0x140009bdc`
- `0x140009fd4`
- `0x14000b57c`
- `0x14000bd28`
- `0x14000c5e0`
- `0x14000c7bc`
- `0x14000c82c`
- `0x14000cc78`
- `0x14000d494`
- `0x14000e26c`
- `0x14000e628`
- `0x14000efc8`
- `0x14000f838`
- `0x14000fa8c`
- `0x140010088`
- `0x140010bac`
- `0x140010e28`
- `0x140011b18`
- `0x140012810`
- `0x1400133e4`
- `0x1400135c0`
- `0x140013ee8`
- `0x140014130`
- `0x140014448`
- `0x140014510`
- `0x14001474c`
- `0x140016e08`
- `0x140017658`

## callees

- `0x140001590`
- `0x140026650`

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
0x140026650  cmp     rcx, cs:__security_cookie
0x140026657  jnz     short loc_140026669
0x140026659  rol     rcx, 10h
0x14002665d  test    cx, 0FFFFh
0x140026662  jnz     short loc_140026665
0x140026664  retn
0x140026665  ror     rcx, 10h
0x140026669  jmp     __report_gsfailure
```
