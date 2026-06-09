# __security_check_cookie

- ea: `0x1400033b0`
- end: `0x1400033ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012cc`
- `0x1400013e8`
- `0x1400014b4`
- `0x1400017e8`
- `0x140001b5c`
- `0x140001bcc`
- `0x140001c5c`
- `0x140001d50`
- `0x140001e94`
- `0x140002138`
- `0x140002430`
- `0x1400028f0`
- `0x140002c00`
- `0x140002e00`
- `0x140002f70`
- `0x140003738`
- `0x140004be4`
- `0x140004e90`
- `0x140005508`
- `0x1400056e8`
- `0x140005a74`
- `0x140006334`
- `0x140007338`
- `0x140007990`
- `0x140007ebc`
- `0x14000811c`
- `0x140008758`
- `0x140008bc4`
- `0x140009448`
- `0x1400095e4`
- `0x140009758`
- `0x14000a4f0`
- `0x14000a8a8`
- `0x14000bbbc`
- `0x14000be3c`
- `0x14000cc40`
- `0x14000ccb0`
- `0x14000d2f0`
- `0x14000d75c`
- `0x14000d884`
- `0x14000e0e8`

## callees

- `0x1400033b0`
- `0x140003d40`

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
0x1400033b0  cmp     rcx, cs:__security_cookie
0x1400033b7  jnz     short loc_1400033C9
0x1400033b9  rol     rcx, 10h
0x1400033bd  test    cx, 0FFFFh
0x1400033c2  jnz     short loc_1400033C5
0x1400033c4  retn
0x1400033c5  ror     rcx, 10h; StackCookie
0x1400033c9  jmp     __report_gsfailure
```
