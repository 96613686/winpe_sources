# __security_check_cookie

- ea: `0x14000ba20`
- end: `0x14000ba3e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010ac`
- `0x1400020b4`
- `0x1400025f4`
- `0x140004160`
- `0x14000500c`
- `0x140005cf4`
- `0x140005e8c`
- `0x1400063fc`
- `0x140006570`
- `0x1400066a4`
- `0x140007694`
- `0x140007990`
- `0x1400080e4`
- `0x140009a00`
- `0x140009a44`
- `0x140009aa4`
- `0x140009d20`
- `0x14000a374`
- `0x14000a934`
- `0x14000b204`
- `0x14000b92c`
- `0x1400217a4`
- `0x140021c5c`
- `0x1400220d0`
- `0x140023470`
- `0x140024758`
- `0x140024b24`
- `0x140028b30`
- `0x140028d9c`
- `0x140029f60`
- `0x14002aecc`
- `0x14002d12c`
- `0x14002e374`
- `0x14002f204`
- `0x14002fe60`
- `0x14003005c`
- `0x1400306f8`
- `0x1400333c4`
- `0x140033de8`
- `0x1400346f0`
- `0x140035238`
- `0x140035f3c`
- `0x1400370c0`
- `0x140037250`
- `0x140037418`
- `0x140037b8c`
- `0x14003875c`
- `0x140038f1c`
- `0x140039de8`
- `0x14003ac68`

## callees

- `0x1400014e0`
- `0x14000ba20`

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
0x14000ba20  cmp     rcx, cs:__security_cookie
0x14000ba27  jnz     short ReportFailure
0x14000ba29  rol     rcx, 10h
0x14000ba2d  test    cx, 0FFFFh
0x14000ba32  jnz     short RestoreRcx
0x14000ba34  retn
0x14000ba35  ror     rcx, 10h; StackCookie
0x14000ba39  jmp     __report_gsfailure
```
