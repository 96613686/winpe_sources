# __security_check_cookie

- ea: `0x140002010`
- end: `0x14000202e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001950`
- `0x140001bb8`
- `0x140001da0`
- `0x140001f10`

## callees

- `0x140001660`
- `0x140002010`

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
0x140002010  cmp     rcx, cs:__security_cookie
0x140002017  jnz     short loc_140002029
0x140002019  rol     rcx, 10h
0x14000201d  test    cx, 0FFFFh
0x140002022  jnz     short loc_140002025
0x140002024  retn
0x140002025  ror     rcx, 10h
0x140002029  jmp     __report_gsfailure
```
