# __security_check_cookie

- ea: `0x14000ddc0`
- end: `0x14000ddde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000115c`
- `0x140001304`
- `0x1400015ec`
- `0x140001a68`
- `0x140001f44`
- `0x1400085b4`
- `0x14000a290`
- `0x14000b14c`
- `0x14000ca2c`
- `0x14000dc8c`
- `0x1400179ac`
- `0x140017c68`
- `0x140018560`
- `0x140019008`
- `0x14001accc`
- `0x14001c478`
- `0x14001d71c`

## callees

- `0x1400014d0`
- `0x14000ddc0`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x14000ddc0  cmp     rcx, cs:__security_cookie
0x14000ddc7  jnz     short ReportFailure
0x14000ddc9  rol     rcx, 10h
0x14000ddcd  test    cx, 0FFFFh
0x14000ddd2  jnz     short RestoreRcx
0x14000ddd4  retn
0x14000ddd5  ror     rcx, 10h; StackCookie
0x14000ddd9  jmp     __report_gsfailure
```
