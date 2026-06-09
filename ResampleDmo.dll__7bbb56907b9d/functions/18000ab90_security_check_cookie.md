# __security_check_cookie

- ea: `0x18000ab90`
- end: `0x18000abae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `30`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002110`
- `0x180005110`
- `0x180005200`
- `0x180005440`
- `0x180005610`
- `0x180008310`
- `0x180008450`
- `0x180008ad4`
- `0x18000971c`
- `0x18000b8f8`
- `0x180041b54`
- `0x180046ed4`
- `0x18006b4c0`
- `0x18006bbf0`
- `0x18006bdf0`
- `0x18006bec8`
- `0x18006bf54`
- `0x18006bfcc`
- `0x18006c224`
- `0x18006c4e0`
- `0x18006cdd0`
- `0x18006d08c`
- `0x18007ff40`
- `0x180080ef0`
- `0x1800810b0`
- `0x180081bb0`
- `0x180081d60`
- `0x180081ec0`
- `0x1800828d4`
- `0x180084164`

## callees

- `0x18000ab90`
- `0x18000b1a0`

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
0x18000ab90  cmp     rcx, cs:__security_cookie
0x18000ab97  jnz     short ReportFailure
0x18000ab99  rol     rcx, 10h
0x18000ab9d  test    cx, 0FFFFh
0x18000aba2  jnz     short RestoreRcx
0x18000aba4  retn
0x18000aba5  ror     rcx, 10h; StackCookie
0x18000aba9  jmp     __report_gsfailure
```
