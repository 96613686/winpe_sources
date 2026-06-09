# __security_check_cookie

- ea: `0x140001530`
- end: `0x14000154e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400024e4`
- `0x140002778`
- `0x140002d18`
- `0x1400030e8`
- `0x140003704`
- `0x140003a80`
- `0x14000521c`
- `0x1400056e0`
- `0x140006064`
- `0x140006c84`
- `0x140007530`
- `0x1400083b4`
- `0x1400088b0`

## callees

- `0x140001530`
- `0x140001b10`

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
0x140001530  cmp     rcx, cs:__security_cookie
0x140001537  jnz     short loc_140001549
0x140001539  rol     rcx, 10h
0x14000153d  test    cx, 0FFFFh
0x140001542  jnz     short loc_140001545
0x140001544  retn
0x140001545  ror     rcx, 10h; StackCookie
0x140001549  jmp     __report_gsfailure
```
