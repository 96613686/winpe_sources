# __security_check_cookie

- ea: `0x140006b90`
- end: `0x140006bae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001c40`
- `0x1400044c4`
- `0x140004758`
- `0x1400049d0`
- `0x140004da0`
- `0x140005374`
- `0x1400056ec`
- `0x140006700`
- `0x140006b0c`

## callees

- `0x1400019b0`
- `0x140006b90`

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
0x140006b90  cmp     rcx, cs:__security_cookie
0x140006b97  jnz     short loc_140006BA9
0x140006b99  rol     rcx, 10h
0x140006b9d  test    cx, 0FFFFh
0x140006ba2  jnz     short loc_140006BA5
0x140006ba4  retn
0x140006ba5  ror     rcx, 10h
0x140006ba9  jmp     __report_gsfailure
```
