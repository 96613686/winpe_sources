# __security_check_cookie

- ea: `0x180020c30`
- end: `0x180020c4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `121`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001260`
- `0x180001360`
- `0x180001cd0`
- `0x180002150`
- `0x1800025b0`
- `0x180003100`
- `0x180003fa0`
- `0x180004b30`
- `0x180005440`
- `0x180005c30`
- `0x180005e40`
- `0x180006380`
- `0x180006410`
- `0x1800068b0`
- `0x180006db0`
- `0x180007410`
- `0x1800074e0`
- `0x180009740`
- `0x18000a160`
- `0x18000ab70`
- `0x18000b740`
- `0x18000bea0`
- `0x18000c450`
- `0x18000c770`
- `0x18000c8b0`
- `0x18000ce80`
- `0x18000d840`
- `0x18000d8c0`
- `0x18000dca0`
- `0x18000de40`
- `0x18000e454`
- `0x18000e970`
- `0x18000e9c8`
- `0x18000f570`
- `0x18000f634`
- `0x18000f7cc`
- `0x180010d84`
- `0x180011020`
- `0x180011c30`
- `0x180011d98`
- `0x180011f60`
- `0x180012644`
- `0x180012a54`
- `0x180013b08`
- `0x180013cf0`
- `0x180014390`
- `0x1800153a0`
- `0x180015544`
- `0x180015b08`
- `0x180016120`

## callees

- `0x1800104b0`
- `0x180020c30`

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
0x180020c30  cmp     rcx, cs:__security_cookie
0x180020c37  jnz     short ReportFailure
0x180020c39  rol     rcx, 10h
0x180020c3d  test    cx, 0FFFFh
0x180020c42  jnz     short RestoreRcx
0x180020c44  retn
0x180020c45  ror     rcx, 10h
0x180020c49  jmp     __report_gsfailure
```
