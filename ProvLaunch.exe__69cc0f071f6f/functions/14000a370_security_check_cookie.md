# __security_check_cookie

- ea: `0x14000a370`
- end: `0x14000a38e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `26`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x140001518`
- `0x1400015a8`
- `0x140002438`
- `0x140002d10`
- `0x140002fbc`
- `0x140003830`
- `0x140003e60`
- `0x1400042f4`
- `0x140004670`
- `0x140005e2c`
- `0x140006820`
- `0x14000693c`
- `0x140006e18`
- `0x140007e3c`
- `0x140008628`
- `0x1400088ac`
- `0x140008ce4`
- `0x140008f54`
- `0x1400090ec`
- `0x140009c08`
- `0x140009ecc`
- `0x14000a24c`

## callees

- `0x140002030`
- `0x14000a370`

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
0x14000a370  cmp     rcx, cs:__security_cookie
0x14000a377  jnz     short loc_14000A389
0x14000a379  rol     rcx, 10h
0x14000a37d  test    cx, 0FFFFh
0x14000a382  jnz     short loc_14000A385
0x14000a384  retn
0x14000a385  ror     rcx, 10h
0x14000a389  jmp     __report_gsfailure
```
