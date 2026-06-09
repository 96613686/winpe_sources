# __security_check_cookie

- ea: `0x140001cd0`
- end: `0x140001cee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x1400016dc`
- `0x140002c64`
- `0x140002f00`
- `0x14000323c`
- `0x1400035e0`
- `0x140003b74`
- `0x140003eec`
- `0x140004bcc`
- `0x1400054ec`
- `0x14000634c`
- `0x140006454`
- `0x1400074d0`
- `0x140007698`

## callees

- `0x140001cd0`
- `0x140002270`

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
0x140001cd0  cmp     rcx, cs:__security_cookie
0x140001cd7  jnz     short loc_140001CE9
0x140001cd9  rol     rcx, 10h
0x140001cdd  test    cx, 0FFFFh
0x140001ce2  jnz     short loc_140001CE5
0x140001ce4  retn
0x140001ce5  ror     rcx, 10h; StackCookie
0x140001ce9  jmp     __report_gsfailure
```
