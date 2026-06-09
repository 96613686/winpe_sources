# __security_check_cookie

- ea: `0x140002d60`
- end: `0x140002d7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001920`
- `0x140001fa0`
- `0x1400024e8`
- `0x140002b48`
- `0x140002cd0`

## callees

- `0x140001660`
- `0x140002d60`

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
0x140002d60  cmp     rcx, cs:__security_cookie
0x140002d67  jnz     short loc_140002D79
0x140002d69  rol     rcx, 10h
0x140002d6d  test    cx, 0FFFFh
0x140002d72  jnz     short loc_140002D75
0x140002d74  retn
0x140002d75  ror     rcx, 10h
0x140002d79  jmp     __report_gsfailure
```
