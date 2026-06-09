# __security_check_cookie

- ea: `0x140002910`
- end: `0x14000292e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400037ac`
- `0x1400038a0`
- `0x140003ee4`
- `0x14000404c`
- `0x140004214`
- `0x140004884`
- `0x140004b40`
- `0x140005aac`
- `0x140005da4`
- `0x140006970`
- `0x140007314`
- `0x140007858`

## callees

- `0x140002910`
- `0x140002ec0`

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
0x140002910  cmp     rcx, cs:__security_cookie
0x140002917  jnz     short loc_140002929
0x140002919  rol     rcx, 10h
0x14000291d  test    cx, 0FFFFh
0x140002922  jnz     short loc_140002925
0x140002924  retn
0x140002925  ror     rcx, 10h; StackCookie
0x140002929  jmp     __report_gsfailure
```
