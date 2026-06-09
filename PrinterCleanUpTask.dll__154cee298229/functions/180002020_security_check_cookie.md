# __security_check_cookie

- ea: `0x180002020`
- end: `0x18000203e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x1800010c0`
- `0x1800011e4`
- `0x180001498`
- `0x180001790`
- `0x1800019b8`
- `0x180002eb0`
- `0x180003130`
- `0x180003390`
- `0x180004214`
- `0x180004510`
- `0x180005610`
- `0x180005a7c`
- `0x180005e9c`
- `0x180006148`
- `0x180008ce0`
- `0x180008f84`
- `0x18000ad4c`
- `0x18000aeb4`
- `0x18000b308`
- `0x18000bb7c`
- `0x18000bd68`
- `0x18000c534`
- `0x18000cc58`
- `0x18000d424`
- `0x18000ed40`
- `0x1800102c4`
- `0x180010470`
- `0x180010af0`
- `0x180011c24`
- `0x180011d8c`
- `0x180011ea8`
- `0x1800127ac`
- `0x180012918`
- `0x180012a58`
- `0x1800137b8`
- `0x180013dd4`
- `0x180014cc0`
- `0x180014ffc`
- `0x1800151d0`
- `0x180015400`
- `0x180015bc4`

## callees

- `0x180002020`
- `0x180002720`

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
0x180002020  cmp     rcx, cs:__security_cookie
0x180002027  jnz     short ReportFailure
0x180002029  rol     rcx, 10h
0x18000202d  test    cx, 0FFFFh
0x180002032  jnz     short RestoreRcx
0x180002034  retn
0x180002035  ror     rcx, 10h; StackCookie
0x180002039  jmp     __report_gsfailure
```
