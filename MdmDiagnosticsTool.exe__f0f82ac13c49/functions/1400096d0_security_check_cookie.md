# __security_check_cookie

- ea: `0x1400096d0`
- end: `0x1400096ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000104c`
- `0x14000110c`
- `0x140002168`
- `0x1400022e4`
- `0x140002840`
- `0x140002ad4`
- `0x1400037d0`
- `0x1400039ac`
- `0x140004274`
- `0x140004628`
- `0x140004a60`
- `0x140005b1c`
- `0x140006a1c`
- `0x140007fa0`
- `0x140008130`
- `0x14000930c`
- `0x1400095b4`

## callees

- `0x140001be0`
- `0x1400096d0`

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
0x1400096d0  cmp     rcx, cs:__security_cookie
0x1400096d7  jnz     short loc_1400096E9
0x1400096d9  rol     rcx, 10h
0x1400096dd  test    cx, 0FFFFh
0x1400096e2  jnz     short loc_1400096E5
0x1400096e4  retn
0x1400096e5  ror     rcx, 10h
0x1400096e9  jmp     __report_gsfailure
```
