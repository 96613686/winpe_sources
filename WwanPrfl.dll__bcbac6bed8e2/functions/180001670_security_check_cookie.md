# __security_check_cookie

- ea: `0x180001670`
- end: `0x18000168e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `33`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002aa0`
- `0x180002d3c`
- `0x180003b08`
- `0x180003eac`
- `0x18000427c`
- `0x180004f64`
- `0x1800052e0`
- `0x180006508`
- `0x180006614`
- `0x18000701c`
- `0x1800088bc`
- `0x180009f74`
- `0x18000b060`
- `0x18000ba90`
- `0x18000c050`
- `0x18000c280`
- `0x18000d6e0`
- `0x18000d808`
- `0x18000dd90`
- `0x18000e2f0`
- `0x18000e520`
- `0x18000e704`
- `0x18000ec80`
- `0x18000f05c`
- `0x18000f26c`
- `0x18000f510`
- `0x18000f854`
- `0x1800103ac`
- `0x180010820`
- `0x180010c60`
- `0x180011ba0`
- `0x1800134f8`
- `0x1800135b4`

## callees

- `0x180001670`
- `0x180001a80`

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
0x180001670  cmp     rcx, cs:__security_cookie
0x180001677  jnz     short ReportFailure
0x180001679  rol     rcx, 10h
0x18000167d  test    cx, 0FFFFh
0x180001682  jnz     short RestoreRcx
0x180001684  retn
0x180001685  ror     rcx, 10h; StackCookie
0x180001689  jmp     __report_gsfailure
```
