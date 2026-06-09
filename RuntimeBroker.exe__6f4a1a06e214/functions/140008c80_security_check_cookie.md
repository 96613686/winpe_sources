# __security_check_cookie

- ea: `0x140008c80`
- end: `0x140008c9e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `35`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010b8`
- `0x140001210`
- `0x1400014c4`
- `0x1400017bc`
- `0x140001ad0`
- `0x140001d90`
- `0x140002260`
- `0x140002590`
- `0x1400027d0`
- `0x140002d70`
- `0x1400048e4`
- `0x1400049f0`
- `0x140005a30`
- `0x140005b48`
- `0x140006580`
- `0x140006e40`
- `0x140007a90`
- `0x140007db0`
- `0x14000a648`
- `0x14000a8dc`
- `0x14000aef0`
- `0x14000b018`
- `0x14000b1a4`
- `0x14000b4d4`
- `0x14000b874`
- `0x14000bb9c`
- `0x14000cf50`
- `0x14000d154`
- `0x14000d440`
- `0x14000dd14`
- `0x14000e884`
- `0x14000eb14`
- `0x14000f00c`
- `0x14000f084`
- `0x14000f1e0`

## callees

- `0x140008c80`
- `0x140009240`

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
0x140008c80  cmp     rcx, cs:__security_cookie
0x140008c87  jnz     short loc_140008C99
0x140008c89  rol     rcx, 10h
0x140008c8d  test    cx, 0FFFFh
0x140008c92  jnz     short loc_140008C95
0x140008c94  retn
0x140008c95  ror     rcx, 10h; StackCookie
0x140008c99  jmp     __report_gsfailure
```
