# __security_check_cookie

- ea: `0x14001adc0`
- end: `0x14001adde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `44`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001198`
- `0x140001248`
- `0x1400012e4`
- `0x1400013c0`
- `0x140001878`
- `0x1400018f4`
- `0x140001d64`
- `0x140001e70`
- `0x140003a80`
- `0x1400051b8`
- `0x140005644`
- `0x140005bb0`
- `0x140007dc0`
- `0x14000ae30`
- `0x14000b270`
- `0x14000b678`
- `0x14000b758`
- `0x14000d090`
- `0x14000e248`
- `0x14000ecc4`
- `0x14000f3d0`
- `0x14000f500`
- `0x1400100cc`
- `0x140011a0c`
- `0x1400126dc`
- `0x140017380`
- `0x140018b98`
- `0x140019160`
- `0x1400195d0`
- `0x140019848`
- `0x14001a288`
- `0x14001ac1c`
- `0x1400285d4`
- `0x140029918`
- `0x140029ff0`
- `0x14002a490`
- `0x14002a548`
- `0x14002ae68`
- `0x14002affc`
- `0x14002bb34`
- `0x14002c77c`
- `0x14002cb84`
- `0x14003036c`

## callees

- `0x1400019e0`
- `0x14001adc0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x14001adc0  cmp     rcx, cs:__security_cookie
0x14001adc7  jnz     short ReportFailure
0x14001adc9  rol     rcx, 10h
0x14001adcd  test    cx, 0FFFFh
0x14001add2  jnz     short RestoreRcx
0x14001add4  retn
0x14001add5  ror     rcx, 10h; StackCookie
0x14001add9  jmp     __report_gsfailure
```
