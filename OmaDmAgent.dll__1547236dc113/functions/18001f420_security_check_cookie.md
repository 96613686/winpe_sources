# __security_check_cookie

- ea: `0x18001f420`
- end: `0x18001f43e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `108`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001188`
- `0x18000121c`
- `0x18000135c`
- `0x18000253c`
- `0x1800027ec`
- `0x180002e64`
- `0x1800030d8`
- `0x1800032a8`
- `0x180003310`
- `0x180003378`
- `0x180003874`
- `0x180003c48`
- `0x180004870`
- `0x180004950`
- `0x180005b78`
- `0x180006bb0`
- `0x180006df0`
- `0x180007110`
- `0x180007240`
- `0x1800076a0`
- `0x1800078f4`
- `0x180007a3c`
- `0x180007b5c`
- `0x180007c00`
- `0x180007edc`
- `0x180008830`
- `0x180008cec`
- `0x180009304`
- `0x18000be18`
- `0x18000bfd4`
- `0x18000c354`
- `0x18000c588`
- `0x18000c734`
- `0x18000cb4c`
- `0x18000ccb4`
- `0x18000d2cc`
- `0x18000da10`
- `0x18000dcb4`
- `0x18000e0a8`
- `0x18000e524`
- `0x18000e980`
- `0x18000ea88`
- `0x18000f704`
- `0x18000f7d4`
- `0x18000f924`
- `0x18000fa44`
- `0x18000fe4c`
- `0x1800100a4`
- `0x1800102b8`

## callees

- `0x180001e70`
- `0x18001f420`

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
0x18001f420  cmp     rcx, cs:__security_cookie
0x18001f427  jnz     short ReportFailure
0x18001f429  rol     rcx, 10h
0x18001f42d  test    cx, 0FFFFh
0x18001f432  jnz     short RestoreRcx
0x18001f434  retn
0x18001f435  ror     rcx, 10h
0x18001f439  jmp     __report_gsfailure
```
