# __security_check_cookie

- ea: `0x140013860`
- end: `0x14001387e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010c0`
- `0x140001460`
- `0x1400017d0`
- `0x140001ba0`
- `0x140002350`
- `0x140002620`
- `0x140002d30`
- `0x140003340`
- `0x140003770`
- `0x140003b0c`
- `0x140003e44`
- `0x140003f70`
- `0x14000424c`
- `0x140004494`
- `0x140004b68`
- `0x140004f6c`
- `0x140005150`
- `0x1400052c8`
- `0x1400055b4`
- `0x140005768`
- `0x140005edc`
- `0x140006330`
- `0x1400067c0`
- `0x1400069a0`
- `0x1400071d4`
- `0x1400073e0`
- `0x14000761c`
- `0x140007a20`
- `0x140007cf0`
- `0x140007fec`
- `0x140008728`
- `0x140008ecc`
- `0x140009520`
- `0x1400096c0`
- `0x140009aec`
- `0x140009d2c`
- `0x14000a530`
- `0x14000a64c`
- `0x14000a930`
- `0x14000abe0`
- `0x14000ae5c`
- `0x14000b0d0`
- `0x14000b654`
- `0x14000b94c`
- `0x14000c0f4`
- `0x14000c5c4`
- `0x14000c7e8`
- `0x14000cb34`
- `0x14000ceb4`
- `0x14000d2d4`

## callees

- `0x140003720`
- `0x140013860`

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
0x140013860  cmp     rcx, cs:__security_cookie
0x140013867  jnz     short ReportFailure
0x140013869  rol     rcx, 10h
0x14001386d  test    cx, 0FFFFh
0x140013872  jnz     short RestoreRcx
0x140013874  retn
0x140013875  ror     rcx, 10h; StackCookie
0x140013879  jmp     __report_gsfailure
```
