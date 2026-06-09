# __security_check_cookie

- ea: `0x18000fc30`
- end: `0x18000fc4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027ac`
- `0x1800028fc`
- `0x180003f3c`
- `0x180006f6c`
- `0x18000738c`
- `0x1800074dc`
- `0x18000766c`
- `0x18000784c`
- `0x180008440`
- `0x1800088e0`
- `0x180008a98`
- `0x180008b64`
- `0x180008c84`
- `0x180009250`
- `0x1800093f8`
- `0x1800098c0`
- `0x18000a690`
- `0x18000b0d0`
- `0x18000e594`
- `0x18000ea24`
- `0x18000eb74`

## callees

- `0x180002190`
- `0x18000fc30`

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
0x18000fc30  cmp     rcx, cs:__security_cookie
0x18000fc37  jnz     short ReportFailure
0x18000fc39  rol     rcx, 10h
0x18000fc3d  test    cx, 0FFFFh
0x18000fc42  jnz     short RestoreRcx
0x18000fc44  retn
0x18000fc45  ror     rcx, 10h
0x18000fc49  jmp     __report_gsfailure
```
