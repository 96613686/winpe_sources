# __security_check_cookie

- ea: `0x140010980`
- end: `0x14001099e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001dec`
- `0x140002670`
- `0x140002ae8`
- `0x1400047e4`
- `0x140004a70`
- `0x140005eb0`
- `0x140006018`
- `0x140006334`
- `0x1400066e0`
- `0x1400068d4`
- `0x140007030`
- `0x14000771c`
- `0x140008188`
- `0x140008424`
- `0x140008c5c`
- `0x140009000`
- `0x1400093d0`
- `0x140009e34`
- `0x14000a1ac`
- `0x14000ad48`
- `0x14000afc8`
- `0x14000b888`
- `0x14000c5cc`
- `0x14000ce3c`
- `0x14000d688`
- `0x14000e0f0`
- `0x14000e674`
- `0x14000e820`
- `0x14000f24c`
- `0x140010574`
- `0x1400108c8`

## callees

- `0x140001950`
- `0x140010980`

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
0x140010980  cmp     rcx, cs:__security_cookie
0x140010987  jnz     short loc_140010999
0x140010989  rol     rcx, 10h
0x14001098d  test    cx, 0FFFFh
0x140010992  jnz     short loc_140010995
0x140010994  retn
0x140010995  ror     rcx, 10h
0x140010999  jmp     __report_gsfailure
```
