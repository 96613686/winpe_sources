# __security_check_cookie

- ea: `0x140002390`
- end: `0x1400023ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140002390`
- `0x140002790`

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
0x140002390  cmp     rcx, cs:__security_cookie
0x140002397  jnz     short loc_1400023A9
0x140002399  rol     rcx, 10h
0x14000239d  test    cx, 0FFFFh
0x1400023a2  jnz     short loc_1400023A5
0x1400023a4  retn
0x1400023a5  ror     rcx, 10h
0x1400023a9  jmp     __report_gsfailure
```
