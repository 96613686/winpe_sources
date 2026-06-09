# __security_check_cookie

- ea: `0x180091140`
- end: `0x18009115e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `238`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c50`
- `0x180006e50`
- `0x18000a0b0`
- `0x18000b920`
- `0x18000c070`
- `0x18000cf50`
- `0x18000d670`
- `0x18000e200`
- `0x18000feb0`
- `0x180011950`
- `0x180011ae0`
- `0x1800124f0`
- `0x180014d20`
- `0x180015a10`
- `0x180017040`
- `0x18001b57c`
- `0x18001bc20`
- `0x18001cc3c`
- `0x18001dc00`
- `0x18001e1e0`
- `0x18001ebcc`
- `0x18001f0c0`
- `0x18001fc90`
- `0x180021160`
- `0x18002195c`
- `0x180021ef0`
- `0x180022474`
- `0x1800227dc`
- `0x180022d48`
- `0x180023208`
- `0x1800233dc`
- `0x180026e40`
- `0x180028e88`
- `0x180029a40`
- `0x18002cb28`
- `0x18002cc44`
- `0x18002cfd0`
- `0x180030e10`
- `0x180031010`
- `0x1800333d0`
- `0x180033b90`
- `0x1800341f8`
- `0x1800344b0`
- `0x180035980`
- `0x180035ee0`
- `0x180037bd0`
- `0x180038400`
- `0x1800385d0`
- `0x18003a3b4`
- `0x18003a6e0`

## callees

- `0x18004c1a0`
- `0x180091140`

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
0x180091140  cmp     rcx, cs:__security_cookie
0x180091147  jnz     short ReportFailure
0x180091149  rol     rcx, 10h
0x18009114d  test    cx, 0FFFFh
0x180091152  jnz     short RestoreRcx
0x180091154  retn
0x180091155  ror     rcx, 10h
0x180091159  jmp     __report_gsfailure
```
