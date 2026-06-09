# __security_check_cookie

- ea: `0x180009440`
- end: `0x18000945e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000211c`
- `0x180003110`
- `0x180003200`
- `0x180003380`
- `0x180003e28`
- `0x180005260`
- `0x180005490`
- `0x180005530`
- `0x180005690`
- `0x180005cd8`
- `0x180006f68`
- `0x180007858`
- `0x180008a6c`
- `0x180008bd4`

## callees

- `0x180001f20`
- `0x180009440`

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
0x180009440  cmp     rcx, cs:__security_cookie
0x180009447  jnz     short ReportFailure
0x180009449  rol     rcx, 10h
0x18000944d  test    cx, 0FFFFh
0x180009452  jnz     short RestoreRcx
0x180009454  retn
0x180009455  ror     rcx, 10h
0x180009459  jmp     __report_gsfailure
```
