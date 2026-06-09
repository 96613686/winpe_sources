# __security_check_cookie

- ea: `0x180001b90`
- end: `0x180001bae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `118`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001090`
- `0x1800011ac`
- `0x180001258`
- `0x180001320`
- `0x180002ca4`
- `0x180002eb8`
- `0x18000392c`
- `0x180003bd4`
- `0x18000422c`
- `0x1800047a4`
- `0x180004b40`
- `0x180005508`
- `0x18000655c`
- `0x180006b40`
- `0x180008270`
- `0x180008ff0`
- `0x18000936c`
- `0x1800094c8`
- `0x180009ca0`
- `0x18000aa50`
- `0x18000ab50`
- `0x18000ad70`
- `0x18000ba80`
- `0x18000bb30`
- `0x18000bf10`
- `0x18000ce20`
- `0x18000d194`
- `0x18000d344`
- `0x18000d6e4`
- `0x18000d8f8`
- `0x18000da68`
- `0x18000e09c`
- `0x18000e470`
- `0x18000e558`
- `0x18000e744`
- `0x18000e858`
- `0x18000ebe8`
- `0x18000ef14`
- `0x18000f170`
- `0x18000f228`
- `0x18000f478`
- `0x18000f648`
- `0x18000f818`
- `0x18000f9fc`
- `0x18000facc`
- `0x18000fc24`
- `0x18000fecc`
- `0x18000ff68`
- `0x180010118`
- `0x180010a7c`

## callees

- `0x180001b90`
- `0x180002170`

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
0x180001b90  cmp     rcx, cs:__security_cookie
0x180001b97  jnz     short ReportFailure
0x180001b99  rol     rcx, 10h
0x180001b9d  test    cx, 0FFFFh
0x180001ba2  jnz     short RestoreRcx
0x180001ba4  retn
0x180001ba5  ror     rcx, 10h; StackCookie
0x180001ba9  jmp     __report_gsfailure
```
