# __security_check_cookie

- ea: `0x1400031b0`
- end: `0x1400031ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013b4`
- `0x140001478`
- `0x14000172c`
- `0x140001a24`
- `0x1400045e4`
- `0x140004878`
- `0x1400052f8`
- `0x140005464`
- `0x140005630`
- `0x1400060a4`
- `0x1400063e4`
- `0x140007600`
- `0x140007ca0`
- `0x140008e8c`
- `0x1400099c0`
- `0x140009bc8`
- `0x14000a2cc`

## callees

- `0x1400031b0`
- `0x1400037c0`

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
0x1400031b0  cmp     rcx, cs:__security_cookie
0x1400031b7  jnz     short loc_1400031C9
0x1400031b9  rol     rcx, 10h
0x1400031bd  test    cx, 0FFFFh
0x1400031c2  jnz     short loc_1400031C5
0x1400031c4  retn
0x1400031c5  ror     rcx, 10h; StackCookie
0x1400031c9  jmp     __report_gsfailure
```
