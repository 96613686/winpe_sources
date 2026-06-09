# __security_check_cookie

- ea: `0x1800130a0`
- end: `0x1800130be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001fac`
- `0x180002ae0`
- `0x180003ad4`
- `0x180003c20`
- `0x180003f40`
- `0x1800059b0`
- `0x1800098a0`
- `0x18000a104`
- `0x18000b230`
- `0x18000cb10`
- `0x18000cee0`
- `0x18000d6bc`
- `0x18000d9ac`
- `0x18000f110`
- `0x18000f3cc`
- `0x18000f860`
- `0x18001018c`
- `0x1800103d0`
- `0x180010e40`
- `0x1800113b0`
- `0x1800120ac`
- `0x180012458`
- `0x1800127d0`

## callees

- `0x180001a90`
- `0x1800130a0`

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
0x1800130a0  cmp     rcx, cs:__security_cookie
0x1800130a7  jnz     short ReportFailure
0x1800130a9  rol     rcx, 10h
0x1800130ad  test    cx, 0FFFFh
0x1800130b2  jnz     short RestoreRcx
0x1800130b4  retn
0x1800130b5  ror     rcx, 10h
0x1800130b9  jmp     __report_gsfailure
```
