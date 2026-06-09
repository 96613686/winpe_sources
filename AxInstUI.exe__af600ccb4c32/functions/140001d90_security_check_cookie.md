# __security_check_cookie

- ea: `0x140001d90`
- end: `0x140001dae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001a08`
- `0x140001af0`
- `0x140001d04`

## callees

- `0x140001730`
- `0x140001d90`

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
0x140001d90  cmp     rcx, cs:__security_cookie
0x140001d97  jnz     short loc_140001DA9
0x140001d99  rol     rcx, 10h
0x140001d9d  test    cx, 0FFFFh
0x140001da2  jnz     short loc_140001DA5
0x140001da4  retn
0x140001da5  ror     rcx, 10h
0x140001da9  jmp     __report_gsfailure
```
