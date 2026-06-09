# __security_check_cookie

- ea: `0x180021850`
- end: `0x18002186e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `45`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800030c8`
- `0x180003374`
- `0x180003758`
- `0x180003ad0`
- `0x180003ea0`
- `0x180004694`
- `0x180004a50`
- `0x1800066cc`
- `0x180007260`
- `0x1800079a0`
- `0x180008f1c`
- `0x18000a7f0`
- `0x18000aa70`
- `0x18000b2dc`
- `0x18000be34`
- `0x18000d824`
- `0x18000dd08`
- `0x18000f1d8`
- `0x18001094c`
- `0x180011770`
- `0x180011824`
- `0x1800119c8`
- `0x18001347c`
- `0x1800136c0`
- `0x180013d40`
- `0x1800140b0`
- `0x180014c20`
- `0x1800153f0`
- `0x1800154f0`
- `0x180015a6c`
- `0x180015c0c`
- `0x1800167a4`
- `0x180017840`
- `0x180018030`
- `0x180018f00`
- `0x180019d80`
- `0x18001b2b8`
- `0x18001c238`
- `0x18001cbc0`
- `0x18001d280`
- `0x18001e060`
- `0x180020810`
- `0x180021740`

## callees

- `0x180002570`
- `0x180021850`

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
0x180021850  cmp     rcx, cs:__security_cookie
0x180021857  jnz     short ReportFailure
0x180021859  rol     rcx, 10h
0x18002185d  test    cx, 0FFFFh
0x180021862  jnz     short RestoreRcx
0x180021864  retn
0x180021865  ror     rcx, 10h
0x180021869  jmp     __report_gsfailure
```
