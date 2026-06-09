# __security_check_cookie

- ea: `0x180002650`
- end: `0x18000266e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `39`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001304`
- `0x1800013c0`
- `0x1800017e4`
- `0x180001b70`
- `0x180001d60`
- `0x1800020e0`
- `0x180002c38`
- `0x180003a08`
- `0x180003cb4`
- `0x1800042e8`
- `0x180004694`
- `0x180004994`
- `0x180004d84`
- `0x180005140`
- `0x180005428`
- `0x180005a78`
- `0x180005b10`
- `0x180006bb0`
- `0x180006dbc`
- `0x180007270`
- `0x1800073f0`
- `0x1800075b0`
- `0x1800077c0`
- `0x1800078a8`
- `0x180007adc`
- `0x180007c2c`
- `0x18000868c`
- `0x180008ea0`
- `0x180009110`
- `0x180009414`
- `0x180009a30`
- `0x180009f00`
- `0x18000a320`
- `0x18000a9d0`
- `0x18000ab80`
- `0x18000ad10`
- `0x18000b018`
- `0x18000b5b0`

## callees

- `0x180002650`
- `0x1800030f0`

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
0x180002650  cmp     rcx, cs:__security_cookie
0x180002657  jnz     short ReportFailure
0x180002659  rol     rcx, 10h
0x18000265d  test    cx, 0FFFFh
0x180002662  jnz     short RestoreRcx
0x180002664  retn
0x180002665  ror     rcx, 10h; StackCookie
0x180002669  jmp     __report_gsfailure
```
