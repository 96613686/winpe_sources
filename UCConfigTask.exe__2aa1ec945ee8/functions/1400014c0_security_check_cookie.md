# __security_check_cookie

- ea: `0x1400014c0`
- end: `0x1400014de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002594`
- `0x140002828`
- `0x140003478`
- `0x1400035e4`
- `0x1400037b0`
- `0x140003ea4`
- `0x140004258`
- `0x140005548`
- `0x140005c24`
- `0x140006b7c`
- `0x140007610`
- `0x140007818`
- `0x140007d10`
- `0x140007d90`
- `0x140007ef4`
- `0x1400081bc`
- `0x140008668`

## callees

- `0x1400014c0`
- `0x140001a60`

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
0x1400014c0  cmp     rcx, cs:__security_cookie
0x1400014c7  jnz     short loc_1400014D9
0x1400014c9  rol     rcx, 10h
0x1400014cd  test    cx, 0FFFFh
0x1400014d2  jnz     short loc_1400014D5
0x1400014d4  retn
0x1400014d5  ror     rcx, 10h; StackCookie
0x1400014d9  jmp     __report_gsfailure
```
