# __security_check_cookie

- ea: `0x180012e00`
- end: `0x180012e1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180002580`
- `0x1800026ac`
- `0x180002c38`
- `0x180002ed4`
- `0x18000314c`
- `0x1800034f0`
- `0x180003af4`
- `0x180003e6c`
- `0x180004f88`
- `0x180005b14`
- `0x1800062a8`
- `0x18000729c`
- `0x1800077a8`
- `0x1800078f8`
- `0x180007a88`
- `0x180007c4c`
- `0x180008714`
- `0x1800088fc`
- `0x180008c1c`
- `0x18000959c`
- `0x180009748`
- `0x18000a170`
- `0x18000ed14`
- `0x18001085c`
- `0x1800111a8`
- `0x180011428`
- `0x180011c80`
- `0x180012ac0`

## callees

- `0x180002070`
- `0x180012e00`

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
0x180012e00  cmp     rcx, cs:__security_cookie
0x180012e07  jnz     short ReportFailure
0x180012e09  rol     rcx, 10h
0x180012e0d  test    cx, 0FFFFh
0x180012e12  jnz     short RestoreRcx
0x180012e14  retn
0x180012e15  ror     rcx, 10h
0x180012e19  jmp     __report_gsfailure
```
