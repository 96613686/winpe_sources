# __security_check_cookie

- ea: `0x180013840`
- end: `0x18001385e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `38`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800022f4`
- `0x180002440`
- `0x180002cec`
- `0x180002f88`
- `0x1800034b8`
- `0x180003a78`
- `0x180003e1c`
- `0x1800041ec`
- `0x180004350`
- `0x180004e44`
- `0x1800051bc`
- `0x18000604c`
- `0x1800062cc`
- `0x180006b98`
- `0x1800079e0`
- `0x18000847c`
- `0x1800094c8`
- `0x180009f44`
- `0x18000a270`
- `0x18000a508`
- `0x18000a588`
- `0x18000aa58`
- `0x18000b310`
- `0x18000b520`
- `0x18000bb80`
- `0x18000bde0`
- `0x18000c218`
- `0x18000c9ac`
- `0x18000cc24`
- `0x18000d39c`
- `0x18000d978`
- `0x18000f190`
- `0x18000fc50`
- `0x180010120`
- `0x180012110`
- `0x18001378c`

## callees

- `0x1800020d0`
- `0x180013840`

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
0x180013840  cmp     rcx, cs:__security_cookie
0x180013847  jnz     short ReportFailure
0x180013849  rol     rcx, 10h
0x18001384d  test    cx, 0FFFFh
0x180013852  jnz     short RestoreRcx
0x180013854  retn
0x180013855  ror     rcx, 10h
0x180013859  jmp     __report_gsfailure
```
