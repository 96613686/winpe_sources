# __security_check_cookie

- ea: `0x180013700`
- end: `0x18001371e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001f9c`
- `0x1800033c0`
- `0x180003514`
- `0x1800038c8`
- `0x180003a80`
- `0x180003fc0`
- `0x1800047c4`
- `0x1800049bc`
- `0x180005198`
- `0x180005388`
- `0x180005660`
- `0x180005758`
- `0x180005a38`
- `0x180006004`
- `0x1800060d0`
- `0x180006714`
- `0x180006904`
- `0x180007380`
- `0x18000768c`
- `0x180007c14`
- `0x180007ff0`
- `0x180008544`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000b02c`
- `0x18000b3fc`
- `0x18000b7a0`
- `0x18000b96c`
- `0x18000bd60`
- `0x18000bdec`
- `0x18000beac`
- `0x18000d060`
- `0x18000d3e0`
- `0x18000d728`
- `0x18000d9f4`
- `0x18000dabc`
- `0x18000ea18`
- `0x18000f6bc`
- `0x18000f94c`
- `0x18001031c`
- `0x180010eac`
- `0x180011878`
- `0x180011df0`
- `0x180011fb0`

## callees

- `0x180001aa0`
- `0x180013700`

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
0x180013700  cmp     rcx, cs:__security_cookie
0x180013707  jnz     short ReportFailure
0x180013709  rol     rcx, 10h
0x18001370d  test    cx, 0FFFFh
0x180013712  jnz     short RestoreRcx
0x180013714  retn
0x180013715  ror     rcx, 10h
0x180013719  jmp     __report_gsfailure
```
