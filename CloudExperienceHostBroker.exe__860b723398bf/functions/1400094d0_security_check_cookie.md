# __security_check_cookie

- ea: `0x1400094d0`
- end: `0x1400094ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012dc`
- `0x1400015d4`
- `0x140002b1c`
- `0x140002dc8`
- `0x140003440`
- `0x14000361c`
- `0x1400039a4`
- `0x140003d58`
- `0x140005440`
- `0x140006000`
- `0x140006478`
- `0x140006e78`
- `0x140008010`
- `0x1400093e0`

## callees

- `0x140002580`
- `0x1400094d0`

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
0x1400094d0  cmp     rcx, cs:__security_cookie
0x1400094d7  jnz     short loc_1400094E9
0x1400094d9  rol     rcx, 10h
0x1400094dd  test    cx, 0FFFFh
0x1400094e2  jnz     short loc_1400094E5
0x1400094e4  retn
0x1400094e5  ror     rcx, 10h
0x1400094e9  jmp     __report_gsfailure
```
