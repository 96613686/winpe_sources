# __security_check_cookie

- ea: `0x18000b630`
- end: `0x18000b64e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001090`
- `0x180001320`
- `0x180002610`
- `0x180003930`
- `0x180004710`
- `0x1800048e0`
- `0x180004cd0`
- `0x180004fb8`
- `0x18000662c`
- `0x180006890`
- `0x18000787c`
- `0x1800079cc`
- `0x180007f20`
- `0x180008ad8`
- `0x180008d88`
- `0x180008e9c`
- `0x1800091d4`
- `0x180009f00`
- `0x18000aaa0`
- `0x18000adb4`
- `0x18000af88`

## callees

- `0x180007110`
- `0x18000b630`

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
0x18000b630  cmp     rcx, cs:__security_cookie
0x18000b637  jnz     short ReportFailure
0x18000b639  rol     rcx, 10h
0x18000b63d  test    cx, 0FFFFh
0x18000b642  jnz     short RestoreRcx
0x18000b644  retn
0x18000b645  ror     rcx, 10h
0x18000b649  jmp     __report_gsfailure
```
