# __security_check_cookie

- ea: `0x1400019f0`
- end: `0x140001a0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1400019f0`
- `0x140001e80`

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
0x1400019f0  cmp     rcx, cs:__security_cookie
0x1400019f7  jnz     short loc_140001A09
0x1400019f9  rol     rcx, 10h
0x1400019fd  test    cx, 0FFFFh
0x140001a02  jnz     short loc_140001A05
0x140001a04  retn
0x140001a05  ror     rcx, 10h; StackCookie
0x140001a09  jmp     __report_gsfailure
```
