# __security_check_cookie

- ea: `0x1400134a0`
- end: `0x1400134be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000108c`
- `0x140001150`
- `0x1400011e8`
- `0x1400012b0`
- `0x140001348`
- `0x1400013c4`
- `0x140002b9c`
- `0x140002e38`
- `0x1400030b0`
- `0x140003474`
- `0x140003b24`
- `0x140003e9c`
- `0x140004780`
- `0x140005138`
- `0x140005524`
- `0x140005b30`
- `0x1400063bc`
- `0x140007dcc`
- `0x14000fc18`
- `0x14001004c`
- `0x140010158`
- `0x140010a9c`
- `0x1400120a8`
- `0x1400122e8`
- `0x140012a38`
- `0x1400133e0`

## callees

- `0x140002070`
- `0x1400134a0`

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
0x1400134a0  cmp     rcx, cs:__security_cookie
0x1400134a7  jnz     short loc_1400134B9
0x1400134a9  rol     rcx, 10h
0x1400134ad  test    cx, 0FFFFh
0x1400134b2  jnz     short loc_1400134B5
0x1400134b4  retn
0x1400134b5  ror     rcx, 10h
0x1400134b9  jmp     __report_gsfailure
```
