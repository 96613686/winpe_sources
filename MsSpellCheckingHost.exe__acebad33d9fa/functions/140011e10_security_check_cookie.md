# __security_check_cookie

- ea: `0x140011e10`
- end: `0x140011e2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000243c`
- `0x14000255c`
- `0x140002bec`
- `0x140003334`
- `0x1400034dc`
- `0x1400039a4`
- `0x140003f34`
- `0x140004210`
- `0x1400048d0`
- `0x140004bd8`
- `0x140004d28`
- `0x140004eb8`
- `0x140005098`
- `0x140005af0`
- `0x140005f04`
- `0x1400073ac`
- `0x140007648`
- `0x140009088`
- `0x14000942c`
- `0x14000992c`
- `0x14000a4a4`
- `0x14000a820`
- `0x14000afe0`
- `0x14000bde8`
- `0x14000c068`
- `0x14000c174`
- `0x14000cb30`
- `0x14000e0ac`
- `0x14000f170`
- `0x14000f660`
- `0x14000f770`
- `0x14000fa08`
- `0x14000fef0`
- `0x140010050`
- `0x140010c50`
- `0x140010d08`
- `0x140011110`
- `0x140011770`
- `0x140011894`

## callees

- `0x140001d90`
- `0x140011e10`

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
0x140011e10  cmp     rcx, cs:__security_cookie
0x140011e17  jnz     short loc_140011E29
0x140011e19  rol     rcx, 10h
0x140011e1d  test    cx, 0FFFFh
0x140011e22  jnz     short loc_140011E25
0x140011e24  retn
0x140011e25  ror     rcx, 10h
0x140011e29  jmp     __report_gsfailure
```
