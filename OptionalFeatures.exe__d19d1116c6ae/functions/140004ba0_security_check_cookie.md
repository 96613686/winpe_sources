# __security_check_cookie

- ea: `0x140004ba0`
- end: `0x140004bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001fe0`
- `0x14000227c`
- `0x1400024f4`
- `0x140002898`
- `0x140002de4`
- `0x14000315c`
- `0x140004280`
- `0x140004570`
- `0x140004b14`

## callees

- `0x1400018d0`
- `0x140004ba0`

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
0x140004ba0  cmp     rcx, cs:__security_cookie
0x140004ba7  jnz     short loc_140004BB9
0x140004ba9  rol     rcx, 10h
0x140004bad  test    cx, 0FFFFh
0x140004bb2  jnz     short loc_140004BB5
0x140004bb4  retn
0x140004bb5  ror     rcx, 10h
0x140004bb9  jmp     __report_gsfailure
```
