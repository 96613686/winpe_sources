# __security_check_cookie

- ea: `0x18000b710`
- end: `0x18000b72e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800012dc`
- `0x1800015d4`
- `0x1800034f8`
- `0x180003a18`
- `0x1800045d4`
- `0x180004870`
- `0x180004d48`
- `0x180004fb0`
- `0x1800053f4`
- `0x1800057a8`
- `0x180005d88`
- `0x180006ce0`
- `0x1800078f4`
- `0x180007c4c`
- `0x180008100`
- `0x180008b20`
- `0x180009d30`
- `0x18000a278`
- `0x18000b0c0`
- `0x18000b650`

## callees

- `0x180001f60`
- `0x18000b710`

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
0x18000b710  cmp     rcx, cs:__security_cookie
0x18000b717  jnz     short ReportFailure
0x18000b719  rol     rcx, 10h
0x18000b71d  test    cx, 0FFFFh
0x18000b722  jnz     short RestoreRcx
0x18000b724  retn
0x18000b725  ror     rcx, 10h
0x18000b729  jmp     __report_gsfailure
```
