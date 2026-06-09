# __security_check_cookie

- ea: `0x180001560`
- end: `0x18000157e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800026d4`
- `0x180002968`
- `0x180002f08`
- `0x1800032d8`
- `0x180003844`
- `0x180003bc0`
- `0x18000536c`
- `0x180005830`
- `0x1800071e0`
- `0x180007e24`

## callees

- `0x180001560`
- `0x180001b20`

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
0x180001560  cmp     rcx, cs:__security_cookie
0x180001567  jnz     short ReportFailure
0x180001569  rol     rcx, 10h
0x18000156d  test    cx, 0FFFFh
0x180001572  jnz     short RestoreRcx
0x180001574  retn
0x180001575  ror     rcx, 10h; StackCookie
0x180001579  jmp     __report_gsfailure
```
