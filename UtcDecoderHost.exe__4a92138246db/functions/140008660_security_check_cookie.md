# __security_check_cookie

- ea: `0x140008660`
- end: `0x14000867e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `37`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010a8`
- `0x140001380`
- `0x140001444`
- `0x1400016f8`
- `0x140001cf0`
- `0x140001db0`
- `0x140001e50`
- `0x140001f20`
- `0x140001fc0`
- `0x140002060`
- `0x140002110`
- `0x140007f20`
- `0x1400094a4`
- `0x140009624`
- `0x140009c40`
- `0x140009eec`
- `0x14000aac8`
- `0x14000aea4`
- `0x14000b4c4`
- `0x14000b840`
- `0x14000cefc`
- `0x14000d4e0`
- `0x14000d958`
- `0x14000e5cc`
- `0x14000e864`
- `0x14000fccc`
- `0x14001071c`
- `0x140010c3c`
- `0x14001131c`
- `0x140011ea4`
- `0x140012104`
- `0x140013110`
- `0x14001373c`
- `0x140013cd0`
- `0x140014984`
- `0x140015230`
- `0x14001638c`

## callees

- `0x140008660`
- `0x140008c40`

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
0x140008660  cmp     rcx, cs:__security_cookie
0x140008667  jnz     short loc_140008679
0x140008669  rol     rcx, 10h
0x14000866d  test    cx, 0FFFFh
0x140008672  jnz     short loc_140008675
0x140008674  retn
0x140008675  ror     rcx, 10h; StackCookie
0x140008679  jmp     __report_gsfailure
```
