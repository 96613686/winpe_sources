# __security_check_cookie

- ea: `0x140001600`
- end: `0x14000161e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140002364`
- `0x140002600`
- `0x1400029f4`
- `0x140002bc0`
- `0x140002f54`
- `0x140003308`
- `0x14000415c`
- `0x140004694`
- `0x1400054fc`
- `0x1400059b4`

## callees

- `0x140001600`
- `0x140001bc0`

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
0x140001600  cmp     rcx, cs:__security_cookie
0x140001607  jnz     short loc_140001619
0x140001609  rol     rcx, 10h
0x14000160d  test    cx, 0FFFFh
0x140001612  jnz     short loc_140001615
0x140001614  retn
0x140001615  ror     rcx, 10h; StackCookie
0x140001619  jmp     __report_gsfailure
```
