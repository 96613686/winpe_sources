# __security_check_cookie

- ea: `0x18009e300`
- end: `0x18009e31e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `172`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800010c0`
- `0x180001374`
- `0x1800013ec`
- `0x180001dd0`
- `0x180001e90`
- `0x180005b50`
- `0x180007a20`
- `0x1800088e0`
- `0x180009030`
- `0x18000b770`
- `0x18000dd64`
- `0x180010a2c`
- `0x180011e90`
- `0x1800141b4`
- `0x1800146f0`
- `0x180014bec`
- `0x180015784`
- `0x180016540`
- `0x18001681c`
- `0x180016a1c`
- `0x180016bf4`
- `0x180023940`
- `0x180028d3c`
- `0x1800295c8`
- `0x180029a04`
- `0x18002e1b0`
- `0x180031a20`
- `0x180034a60`
- `0x180034d20`
- `0x180035f30`
- `0x180037860`
- `0x1800380d4`
- `0x180038660`
- `0x1800388ec`
- `0x180038adc`
- `0x18003916c`
- `0x1800398d8`
- `0x180039c64`
- `0x18003a6c4`
- `0x18003ad90`
- `0x18003ae80`
- `0x18003bcec`
- `0x18003bd7c`
- `0x18003c174`
- `0x18003c460`
- `0x18003ce34`
- `0x18003cf80`
- `0x18003d2fc`
- `0x18003dcd0`

## callees

- `0x18003e920`
- `0x18009e300`

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
0x18009e300  cmp     rcx, cs:__security_cookie
0x18009e307  jnz     short ReportFailure
0x18009e309  rol     rcx, 10h
0x18009e30d  test    cx, 0FFFFh
0x18009e312  jnz     short RestoreRcx
0x18009e314  retn
0x18009e315  ror     rcx, 10h
0x18009e319  jmp     __report_gsfailure
```
