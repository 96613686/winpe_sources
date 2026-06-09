# __security_check_cookie

- ea: `0x180003a60`
- end: `0x180003a7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `100`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001158`
- `0x18000140c`
- `0x180001704`
- `0x180001928`
- `0x180001a40`
- `0x180001ee0`
- `0x1800020b0`
- `0x180002450`
- `0x180002bc0`
- `0x180002dc0`
- `0x180002f30`
- `0x1800031b0`
- `0x180003520`
- `0x180003f40`
- `0x180004f50`
- `0x1800061b0`
- `0x18000645c`
- `0x180008118`
- `0x180008284`
- `0x18000862c`
- `0x180008f84`
- `0x1800092ec`
- `0x180009730`
- `0x1800098d8`
- `0x18000a338`
- `0x18000a41c`
- `0x18000b4c4`
- `0x18000bb98`
- `0x18000d3cc`
- `0x18000df7c`
- `0x18000e940`
- `0x18000eb48`
- `0x18000ed30`
- `0x18000eed0`
- `0x18000f1c0`
- `0x18000fe10`
- `0x18000fea8`
- `0x1800103c4`
- `0x1800104f8`
- `0x1800120a0`
- `0x1800122f0`
- `0x18001309c`
- `0x1800133e8`
- `0x18001364c`
- `0x1800137ac`
- `0x180013a2c`
- `0x1800142f0`
- `0x1800146b8`
- `0x180014de4`

## callees

- `0x180003a60`
- `0x180003a90`

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
0x180003a60  cmp     rcx, cs:__security_cookie
0x180003a67  jnz     short ReportFailure
0x180003a69  rol     rcx, 10h
0x180003a6d  test    cx, 0FFFFh
0x180003a72  jnz     short RestoreRcx
0x180003a74  retn
0x180003a75  ror     rcx, 10h; StackCookie
0x180003a79  jmp     __report_gsfailure
```
