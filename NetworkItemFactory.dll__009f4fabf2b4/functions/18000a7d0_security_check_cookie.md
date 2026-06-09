# __security_check_cookie

- ea: `0x18000a7d0`
- end: `0x18000a7ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002ab8`
- `0x180003d28`
- `0x1800069c0`
- `0x180006c28`
- `0x180008bf4`
- `0x18000a4b4`
- `0x18000a6d4`

## callees

- `0x180001b90`
- `0x18000a7d0`

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
0x18000a7d0  cmp     rcx, cs:__security_cookie
0x18000a7d7  jnz     short ReportFailure
0x18000a7d9  rol     rcx, 10h
0x18000a7dd  test    cx, 0FFFFh
0x18000a7e2  jnz     short RestoreRcx
0x18000a7e4  retn
0x18000a7e5  ror     rcx, 10h
0x18000a7e9  jmp     __report_gsfailure
```
