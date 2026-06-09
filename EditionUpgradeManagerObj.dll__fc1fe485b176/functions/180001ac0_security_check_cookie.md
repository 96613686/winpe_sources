# __security_check_cookie

- ea: `0x180001ac0`
- end: `0x180001ade`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `44`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800010a8`
- `0x180002f64`
- `0x1800031f8`
- `0x180003bc4`
- `0x180003f94`
- `0x18000438c`
- `0x180004ed4`
- `0x18000524c`
- `0x180006288`
- `0x180006394`
- `0x180006d88`
- `0x180007e20`
- `0x180008854`
- `0x180008b24`
- `0x180009300`
- `0x180009480`
- `0x180009f30`
- `0x18000b0b0`
- `0x18000bb10`
- `0x18000c870`
- `0x18000d2ac`
- `0x18000d7b4`
- `0x18000d95c`
- `0x18000ec9c`
- `0x18000ed14`
- `0x18000f264`
- `0x1800117b0`
- `0x180011fac`
- `0x1800128c4`
- `0x180012af4`
- `0x1800131a4`
- `0x18001324c`
- `0x1800133e0`
- `0x180013674`
- `0x180013780`
- `0x180013b8c`
- `0x1800142f8`
- `0x180014a1c`
- `0x1800170b0`
- `0x180017ef8`
- `0x180018cec`
- `0x180022088`
- `0x180022348`
- `0x18002287c`

## callees

- `0x180001ac0`
- `0x1800020d0`

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
0x180001ac0  cmp     rcx, cs:__security_cookie
0x180001ac7  jnz     short ReportFailure
0x180001ac9  rol     rcx, 10h
0x180001acd  test    cx, 0FFFFh
0x180001ad2  jnz     short RestoreRcx
0x180001ad4  retn
0x180001ad5  ror     rcx, 10h; StackCookie
0x180001ad9  jmp     __report_gsfailure
```
