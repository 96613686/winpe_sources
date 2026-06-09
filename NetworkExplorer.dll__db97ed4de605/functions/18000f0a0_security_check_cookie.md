# __security_check_cookie

- ea: `0x18000f0a0`
- end: `0x18000f0be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `29`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010a8`
- `0x18000135c`
- `0x1800013ec`
- `0x180001690`
- `0x180001c80`
- `0x180002d2c`
- `0x180002dc0`
- `0x180003c90`
- `0x180006030`
- `0x180006808`
- `0x180006aa8`
- `0x1800082cc`
- `0x180008560`
- `0x180008798`
- `0x180008f7c`
- `0x180009280`
- `0x1800097dc`
- `0x180009ca4`
- `0x18000b8c4`
- `0x18000c150`
- `0x18000c984`
- `0x18000cb58`
- `0x18000d980`
- `0x18000db98`
- `0x18000dc60`
- `0x18000e4b4`
- `0x18000eb90`
- `0x18000ed98`
- `0x18000ef30`

## callees

- `0x180007a90`
- `0x18000f0a0`

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
0x18000f0a0  cmp     rcx, cs:__security_cookie
0x18000f0a7  jnz     short ReportFailure
0x18000f0a9  rol     rcx, 10h
0x18000f0ad  test    cx, 0FFFFh
0x18000f0b2  jnz     short RestoreRcx
0x18000f0b4  retn
0x18000f0b5  ror     rcx, 10h
0x18000f0b9  jmp     __report_gsfailure
```
