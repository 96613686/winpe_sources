# __security_check_cookie

- ea: `0x14000a640`
- end: `0x14000a65e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `101`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001000`
- `0x1400011fc`
- `0x140001334`
- `0x1400013e0`
- `0x1400016ac`
- `0x140001840`
- `0x1400018c4`
- `0x140001c40`
- `0x140001d70`
- `0x1400020f0`
- `0x140002410`
- `0x140002550`
- `0x140002a34`
- `0x1400034b0`
- `0x14000361c`
- `0x1400038dc`
- `0x140003a30`
- `0x140003aec`
- `0x140003cd0`
- `0x140003fe8`
- `0x140004708`
- `0x14000487c`
- `0x140004ab4`
- `0x140004b04`
- `0x140004b7c`
- `0x140004cdc`
- `0x140005064`
- `0x140005294`
- `0x1400052f4`
- `0x1400053cc`
- `0x14000553c`
- `0x140005668`
- `0x1400056fc`
- `0x140005844`
- `0x1400059fc`
- `0x140005ff0`
- `0x140006140`
- `0x1400062e8`
- `0x140006330`
- `0x140006aac`
- `0x140006d9c`
- `0x140006f30`
- `0x140007730`
- `0x140007810`
- `0x1400079e0`
- `0x140007b34`
- `0x140007d10`
- `0x140007f1c`
- `0x1400084dc`
- `0x1400087cc`

## callees

- `0x14000a640`
- `0x14000ad70`

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
0x14000a640  cmp     rcx, cs:__security_cookie
0x14000a647  jnz     short ReportFailure
0x14000a649  rol     rcx, 10h
0x14000a64d  test    cx, 0FFFFh
0x14000a652  jnz     short RestoreRcx
0x14000a654  retn
0x14000a655  ror     rcx, 10h; StackCookie
0x14000a659  jmp     __report_gsfailure
```
