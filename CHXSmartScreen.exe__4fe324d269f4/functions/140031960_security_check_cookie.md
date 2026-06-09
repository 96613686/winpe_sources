# __security_check_cookie

- ea: `0x140031960`
- end: `0x14003197e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `257`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000108c`
- `0x140001290`
- `0x1400033c4`
- `0x140003ebc`
- `0x140003fc8`
- `0x1400040e0`
- `0x1400041f8`
- `0x140004518`
- `0x140004970`
- `0x1400049dc`
- `0x140004d44`
- `0x1400054a4`
- `0x140005944`
- `0x1400059cc`
- `0x140005bb0`
- `0x140005d24`
- `0x140005fa4`
- `0x1400061e0`
- `0x140006240`
- `0x1400062a0`
- `0x140006300`
- `0x140006360`
- `0x1400063c0`
- `0x140006420`
- `0x140006480`
- `0x140006848`
- `0x140006950`
- `0x14000719c`
- `0x140007360`
- `0x140007a90`
- `0x140007b20`
- `0x140007bb0`
- `0x140007c40`
- `0x140007cd0`
- `0x140007d60`
- `0x140007df0`
- `0x140007e80`
- `0x140007f10`
- `0x140007fb0`
- `0x140008470`
- `0x14000883c`
- `0x140008900`
- `0x140009160`
- `0x1400091c0`
- `0x140009260`
- `0x140009320`
- `0x1400093e0`
- `0x1400095a0`
- `0x140009750`
- `0x140009800`

## callees

- `0x1400034a0`
- `0x140031960`

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
0x140031960  cmp     rcx, cs:__security_cookie
0x140031967  jnz     short loc_140031979
0x140031969  rol     rcx, 10h
0x14003196d  test    cx, 0FFFFh
0x140031972  jnz     short loc_140031975
0x140031974  retn
0x140031975  ror     rcx, 10h
0x140031979  jmp     __report_gsfailure
```
