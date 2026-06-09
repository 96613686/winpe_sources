# __security_check_cookie

- ea: `0x18002cfa0`
- end: `0x18002cfbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `71`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010b4`
- `0x1800054d0`
- `0x180009a20`
- `0x18000a7a4`
- `0x18000a97c`
- `0x18000ae50`
- `0x18000af40`
- `0x18000c3a4`
- `0x18000c510`
- `0x18000c868`
- `0x18000cd68`
- `0x18000d904`
- `0x18000f774`
- `0x18000fa30`
- `0x18000fbcc`
- `0x180010760`
- `0x180011590`
- `0x180011da0`
- `0x180012fa0`
- `0x180013fdc`
- `0x180014d60`
- `0x180015070`
- `0x180015878`
- `0x180017544`
- `0x180019070`
- `0x180019258`
- `0x18001992c`
- `0x180019fe4`
- `0x18001c230`
- `0x18001cd44`
- `0x18001ced4`
- `0x18001d064`
- `0x18001d568`
- `0x18001dbec`
- `0x18001dd04`
- `0x18001ded8`
- `0x18001e270`
- `0x18001e66c`
- `0x18001e86c`
- `0x18001eaa8`
- `0x18001ebf4`
- `0x18001ee94`
- `0x18001efd8`
- `0x180020394`
- `0x180020638`
- `0x180020cdc`
- `0x180020e28`
- `0x1800210a0`
- `0x180021200`

## callees

- `0x180001c90`
- `0x18002cfa0`

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
0x18002cfa0  cmp     rcx, cs:__security_cookie
0x18002cfa7  jnz     short ReportFailure
0x18002cfa9  rol     rcx, 10h
0x18002cfad  test    cx, 0FFFFh
0x18002cfb2  jnz     short RestoreRcx
0x18002cfb4  retn
0x18002cfb5  ror     rcx, 10h
0x18002cfb9  jmp     __report_gsfailure
```
