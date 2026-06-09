# __security_check_cookie

- ea: `0x18000b640`
- end: `0x18000b65e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002010`
- `0x18000215c`
- `0x180002b10`
- `0x180002cc8`
- `0x180002e4c`
- `0x180003f7c`
- `0x180004a4c`
- `0x180004df8`
- `0x180004f3c`
- `0x1800050c0`
- `0x180005408`
- `0x180005d94`
- `0x180005eb0`
- `0x1800060d0`
- `0x1800061ec`
- `0x18000640c`
- `0x18000672c`
- `0x180006b14`
- `0x180007034`
- `0x1800076e8`
- `0x180007a70`
- `0x1800081b0`
- `0x1800085c0`
- `0x180008940`
- `0x180008bc4`
- `0x180008fa8`
- `0x18000a8ac`
- `0x18000b3fc`

## callees

- `0x1800018c0`
- `0x18000b640`

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
0x18000b640  cmp     rcx, cs:__security_cookie
0x18000b647  jnz     short ReportFailure
0x18000b649  rol     rcx, 10h
0x18000b64d  test    cx, 0FFFFh
0x18000b652  jnz     short RestoreRcx
0x18000b654  retn
0x18000b655  ror     rcx, 10h
0x18000b659  jmp     __report_gsfailure
```
