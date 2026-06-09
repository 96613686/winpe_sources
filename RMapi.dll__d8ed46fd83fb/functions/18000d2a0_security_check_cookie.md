# __security_check_cookie

- ea: `0x18000d2a0`
- end: `0x18000d2be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `174`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001140`
- `0x1800012cc`
- `0x180001404`
- `0x18000154c`
- `0x180001670`
- `0x180001770`
- `0x180001880`
- `0x180001954`
- `0x180001a6c`
- `0x180001b94`
- `0x180001c7c`
- `0x180001d54`
- `0x180001e6c`
- `0x180001f30`
- `0x180002000`
- `0x1800020fc`
- `0x18000219c`
- `0x180002510`
- `0x180002c10`
- `0x180002ec0`
- `0x180003180`
- `0x1800035b0`
- `0x180003920`
- `0x180003c70`
- `0x180003e84`
- `0x180003fd0`
- `0x1800042b0`
- `0x1800043fc`
- `0x1800044d0`
- `0x18000473c`
- `0x1800047e0`
- `0x180004950`
- `0x180004e60`
- `0x180005050`
- `0x18000559c`
- `0x180005750`
- `0x180005a70`
- `0x180005aec`
- `0x180005c00`
- `0x1800060b0`
- `0x180006200`
- `0x180006350`
- `0x1800063b8`
- `0x180006650`
- `0x180006750`
- `0x180006a2c`
- `0x180006c78`
- `0x180006eec`
- `0x180007248`

## callees

- `0x18000d2a0`
- `0x18000dd60`

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
0x18000d2a0  cmp     rcx, cs:__security_cookie
0x18000d2a7  jnz     short ReportFailure
0x18000d2a9  rol     rcx, 10h
0x18000d2ad  test    cx, 0FFFFh
0x18000d2b2  jnz     short RestoreRcx
0x18000d2b4  retn
0x18000d2b5  ror     rcx, 10h; StackCookie
0x18000d2b9  jmp     __report_gsfailure
```
