# __security_check_cookie

- ea: `0x140004360`
- end: `0x14000437e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140003ab8`
- `0x1400042d0`

## callees

- `0x140002220`
- `0x140004360`

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
0x140004360  cmp     rcx, cs:__security_cookie
0x140004367  jnz     short loc_140004379
0x140004369  rol     rcx, 10h
0x14000436d  test    cx, 0FFFFh
0x140004372  jnz     short loc_140004375
0x140004374  retn
0x140004375  ror     rcx, 10h
0x140004379  jmp     __report_gsfailure
```
