# __security_check_cookie

- ea: `0x1800326d0`
- end: `0x1800326ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800011f8`
- `0x1800012a8`
- `0x1800013c8`
- `0x18000142c`
- `0x1800022b0`
- `0x1800027f4`
- `0x1800029c8`
- `0x1800039e0`
- `0x180004980`
- `0x180005090`
- `0x180006d30`
- `0x18000c870`
- `0x18000dca0`
- `0x180010bac`
- `0x180011c5c`
- `0x1800128a0`
- `0x180012aa0`
- `0x180013740`
- `0x1800141c0`
- `0x18001672c`
- `0x180017768`
- `0x180017db0`
- `0x180017f44`
- `0x180018278`
- `0x18001859c`
- `0x1800188fc`
- `0x180019140`
- `0x180019220`
- `0x180019bc4`
- `0x180019c1c`
- `0x180019dd8`
- `0x18001a390`
- `0x18001a748`
- `0x18001af40`
- `0x18001b5cc`
- `0x18001b974`
- `0x18001f680`
- `0x180022430`
- `0x1800232b4`
- `0x180023810`
- `0x180023aa4`
- `0x180024438`
- `0x1800245a4`
- `0x180024b78`
- `0x180025284`
- `0x18002559c`
- `0x1800264a8`
- `0x18002668c`
- `0x180026a94`

## callees

- `0x18001c8a0`
- `0x1800326d0`

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
0x1800326d0  cmp     rcx, cs:__security_cookie
0x1800326d7  jnz     short ReportFailure
0x1800326d9  rol     rcx, 10h
0x1800326dd  test    cx, 0FFFFh
0x1800326e2  jnz     short RestoreRcx
0x1800326e4  retn
0x1800326e5  ror     rcx, 10h
0x1800326e9  jmp     __report_gsfailure
```
