# __security_check_cookie

- ea: `0x1800135c0`
- end: `0x1800135de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `68`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000202c`
- `0x1800021b0`
- `0x180002460`
- `0x180002814`
- `0x180002be0`
- `0x180002d24`
- `0x180003010`
- `0x180003240`
- `0x180003390`
- `0x180003580`
- `0x180003a10`
- `0x180003d00`
- `0x180003f68`
- `0x180004170`
- `0x1800042a0`
- `0x1800046bc`
- `0x1800049d0`
- `0x180004b00`
- `0x1800050b8`
- `0x180005284`
- `0x180005578`
- `0x180005750`
- `0x1800057f0`
- `0x180005884`
- `0x180005ce8`
- `0x18000634c`
- `0x1800067f0`
- `0x180006860`
- `0x180006934`
- `0x180006cbc`
- `0x180006eb8`
- `0x180006f40`
- `0x180007170`
- `0x180007210`
- `0x180007470`
- `0x180007624`
- `0x180007730`
- `0x180007ec8`
- `0x180008020`
- `0x1800081bc`
- `0x1800086f8`
- `0x180008ca0`
- `0x180008e4c`
- `0x180009000`
- `0x1800093e0`
- `0x18000d084`
- `0x18000d29c`
- `0x18000dac8`
- `0x18000dbc0`
- `0x18000ddf0`

## callees

- `0x180001630`
- `0x1800135c0`

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
0x1800135c0  cmp     rcx, cs:__security_cookie
0x1800135c7  jnz     short ReportFailure
0x1800135c9  rol     rcx, 10h
0x1800135cd  test    cx, 0FFFFh
0x1800135d2  jnz     short RestoreRcx
0x1800135d4  retn
0x1800135d5  ror     rcx, 10h
0x1800135d9  jmp     __report_gsfailure
```
