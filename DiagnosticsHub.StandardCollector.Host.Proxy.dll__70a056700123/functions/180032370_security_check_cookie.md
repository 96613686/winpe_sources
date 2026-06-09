# __security_check_cookie

- ea: `0x180032370`
- end: `0x18003238e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `90`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007184`
- `0x180007f1c`
- `0x180008628`
- `0x180008988`
- `0x18000984c`
- `0x180009f0c`
- `0x18000a540`
- `0x18000dd70`
- `0x1800108d4`
- `0x18001094c`
- `0x180011378`
- `0x180011610`
- `0x1800119d4`
- `0x1800120c0`
- `0x1800129c0`
- `0x180012ff4`
- `0x1800131ac`
- `0x180014ab0`
- `0x180015084`
- `0x18001518c`
- `0x1800152a8`
- `0x180016d20`
- `0x180018708`
- `0x180018950`
- `0x180018c50`
- `0x180018dfc`
- `0x180019200`
- `0x180019500`
- `0x180019750`
- `0x180019ac4`
- `0x18001a41c`
- `0x18001a86c`
- `0x18001d0c0`
- `0x18001d23c`
- `0x180020d00`
- `0x1800218ac`
- `0x180021a3c`
- `0x1800232ec`
- `0x1800233f0`
- `0x180024598`
- `0x180024644`
- `0x18002c07c`
- `0x18002c524`
- `0x18002d254`
- `0x18002e9b8`
- `0x18002eebc`
- `0x18002f66c`
- `0x180030e90`
- `0x1800322f8`
- `0x1800339e4`

## callees

- `0x180032370`
- `0x1800323d0`

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
0x180032370  cmp     rcx, cs:__security_cookie
0x180032377  jnz     short ReportFailure
0x180032379  rol     rcx, 10h
0x18003237d  test    cx, 0FFFFh
0x180032382  jnz     short RestoreRcx
0x180032384  retn
0x180032385  ror     rcx, 10h
0x180032389  jmp     __report_gsfailure
```
