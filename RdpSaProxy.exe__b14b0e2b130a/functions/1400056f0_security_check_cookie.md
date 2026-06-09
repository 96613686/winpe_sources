# __security_check_cookie

- ea: `0x1400056f0`
- end: `0x14000570e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002738`
- `0x140003ef4`
- `0x140005660`

## callees

- `0x1400018c0`
- `0x1400056f0`

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
0x1400056f0  cmp     rcx, cs:__security_cookie
0x1400056f7  jnz     short loc_140005709
0x1400056f9  rol     rcx, 10h
0x1400056fd  test    cx, 0FFFFh
0x140005702  jnz     short loc_140005705
0x140005704  retn
0x140005705  ror     rcx, 10h
0x140005709  jmp     __report_gsfailure
```
