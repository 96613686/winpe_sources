# __security_check_cookie

- ea: `0x1400016f0`
- end: `0x14000170e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001a30`
- `0x140002a74`
- `0x140002d10`
- `0x140003a78`
- `0x140003e1c`
- `0x1400041ec`
- `0x140004d14`
- `0x140005090`
- `0x1400060fc`
- `0x140006208`
- `0x140006c1c`
- `0x14000823c`
- `0x140008d20`
- `0x140008e48`
- `0x140009118`
- `0x140009a40`

## callees

- `0x1400016f0`
- `0x140002030`

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
0x1400016f0  cmp     rcx, cs:__security_cookie
0x1400016f7  jnz     short loc_140001709
0x1400016f9  rol     rcx, 10h
0x1400016fd  test    cx, 0FFFFh
0x140001702  jnz     short loc_140001705
0x140001704  retn
0x140001705  ror     rcx, 10h; StackCookie
0x140001709  jmp     __report_gsfailure
```
