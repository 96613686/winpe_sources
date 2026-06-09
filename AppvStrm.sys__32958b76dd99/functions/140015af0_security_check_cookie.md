# __security_check_cookie

- ea: `0x140015af0`
- end: `0x140015b0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000279c`
- `0x140003368`
- `0x14000571c`
- `0x140009d98`
- `0x14000a1ac`
- `0x14000a310`
- `0x14000bd34`
- `0x140010b08`
- `0x1400115cc`
- `0x140012b18`
- `0x140013acc`
- `0x140014760`
- `0x1400153c4`
- `0x140015898`
- `0x14001594c`
- `0x14002409c`

## callees

- `0x140001010`
- `0x140015af0`

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
0x140015af0  cmp     rcx, cs:__security_cookie
0x140015af7  jnz     short ReportFailure
0x140015af9  rol     rcx, 10h
0x140015afd  test    cx, 0FFFFh
0x140015b02  jnz     short RestoreRcx
0x140015b04  retn
0x140015b05  ror     rcx, 10h; StackCookie
0x140015b09  jmp     __report_gsfailure
```
