# __security_check_cookie

- ea: `0x180002880`
- end: `0x18000289e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e8`
- `0x1800013b0`
- `0x180001668`
- `0x180002018`
- `0x180002d38`
- `0x180005330`
- `0x180005690`
- `0x180006fb0`
- `0x180007ec0`
- `0x180008010`
- `0x180008170`
- `0x1800084e0`
- `0x18000959c`
- `0x18000984c`
- `0x180009d7c`
- `0x18000a82c`
- `0x18000abf0`
- `0x18000afc8`
- `0x18000b430`
- `0x18000be84`
- `0x18000c214`
- `0x18000d53c`
- `0x18000d64c`
- `0x18000e094`
- `0x18000fb7c`
- `0x180010890`
- `0x1800109bc`
- `0x180010c4c`
- `0x180014464`
- `0x180019118`
- `0x18001d150`
- `0x18001e9d0`
- `0x1800214e8`
- `0x180021a6c`
- `0x180022830`
- `0x180022b04`
- `0x180023118`
- `0x180023334`
- `0x180023728`
- `0x180023838`
- `0x180024160`
- `0x180024600`
- `0x18002485c`
- `0x18002499c`
- `0x18002664c`
- `0x180027c04`

## callees

- `0x180002880`
- `0x180003130`

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
0x180002880  cmp     rcx, cs:__security_cookie
0x180002887  jnz     short ReportFailure
0x180002889  rol     rcx, 10h
0x18000288d  test    cx, 0FFFFh
0x180002892  jnz     short RestoreRcx
0x180002894  retn
0x180002895  ror     rcx, 10h
0x180002899  jmp     __report_gsfailure
```
