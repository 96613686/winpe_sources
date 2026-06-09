# __security_check_cookie

- ea: `0x1400023e0`
- end: `0x1400023fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `218`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001304`
- `0x1400013d8`
- `0x14000149c`
- `0x140001750`
- `0x140001a48`
- `0x140001aec`
- `0x140001c88`
- `0x140003760`
- `0x1400039f4`
- `0x140003e24`
- `0x140003fbc`
- `0x140004384`
- `0x140004738`
- `0x140004a0c`
- `0x14000503c`
- `0x1400050a8`
- `0x140005220`
- `0x140005844`
- `0x140005a88`
- `0x1400062b0`
- `0x140006ccc`
- `0x1400071ac`
- `0x140007210`
- `0x14000745c`
- `0x140007770`
- `0x1400079b4`
- `0x140007b40`
- `0x140007c98`
- `0x140007d68`
- `0x1400081f4`
- `0x1400082e8`
- `0x1400083f0`
- `0x1400086b0`
- `0x140008704`
- `0x14000875c`
- `0x1400087dc`
- `0x1400088ec`
- `0x140008af8`
- `0x140008e48`
- `0x14000912c`
- `0x140009438`
- `0x140009650`
- `0x140009b2c`
- `0x14000a3f8`
- `0x14000b03c`
- `0x14000b290`
- `0x14000b3bc`
- `0x14000b5a0`
- `0x14000b79c`

## callees

- `0x1400023e0`
- `0x140002940`

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
0x1400023e0  cmp     rcx, cs:__security_cookie
0x1400023e7  jnz     short loc_1400023F9
0x1400023e9  rol     rcx, 10h
0x1400023ed  test    cx, 0FFFFh
0x1400023f2  jnz     short loc_1400023F5
0x1400023f4  retn
0x1400023f5  ror     rcx, 10h; StackCookie
0x1400023f9  jmp     __report_gsfailure
```
