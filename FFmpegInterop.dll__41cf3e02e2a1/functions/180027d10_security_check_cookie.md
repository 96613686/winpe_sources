# __security_check_cookie

- ea: `0x180027d10`
- end: `0x180027d2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `208`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001084`
- `0x180001138`
- `0x180001444`
- `0x1800014cc`
- `0x180001778`
- `0x180001a68`
- `0x1800028a0`
- `0x180002c98`
- `0x180002d20`
- `0x180002dc8`
- `0x180002f94`
- `0x180003134`
- `0x1800035f0`
- `0x18000413c`
- `0x180004474`
- `0x180004580`
- `0x180004a20`
- `0x180004d00`
- `0x18000523c`
- `0x180005f70`
- `0x180006950`
- `0x180006b98`
- `0x180006c2c`
- `0x180006cbc`
- `0x1800070e4`
- `0x180007294`
- `0x1800079a8`
- `0x180007a38`
- `0x180007a78`
- `0x180007ab8`
- `0x180007c30`
- `0x180007ca0`
- `0x180007ce0`
- `0x180007d50`
- `0x180007d90`
- `0x180007e00`
- `0x180007f3c`
- `0x180008170`
- `0x180008574`
- `0x1800086cc`
- `0x180008d80`
- `0x180009210`
- `0x18000972c`
- `0x180009864`
- `0x180009900`
- `0x180009c30`
- `0x180009ed0`
- `0x18000a3e0`
- `0x18000b4b0`
- `0x18000b5dc`

## callees

- `0x180027d10`
- `0x1800285a0`

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
0x180027d10  cmp     rcx, cs:__security_cookie
0x180027d17  jnz     short ReportFailure
0x180027d19  rol     rcx, 10h
0x180027d1d  test    cx, 0FFFFh
0x180027d22  jnz     short RestoreRcx
0x180027d24  retn
0x180027d25  ror     rcx, 10h; StackCookie
0x180027d29  jmp     __report_gsfailure
```
