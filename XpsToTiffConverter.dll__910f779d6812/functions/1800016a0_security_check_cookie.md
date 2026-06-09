# __security_check_cookie

- ea: `0x1800016a0`
- end: `0x1800016be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023dc`
- `0x180002a00`
- `0x180002cac`
- `0x180003ab8`
- `0x180003e5c`
- `0x18000422c`
- `0x180004c84`
- `0x180005000`
- `0x180005f28`
- `0x18000683c`
- `0x180007f2c`
- `0x180008b60`
- `0x180008c88`
- `0x18000a384`
- `0x18000a870`
- `0x18000ac30`
- `0x18000c3e8`
- `0x18000ca04`

## callees

- `0x1800016a0`
- `0x180001cd0`

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
0x1800016a0  cmp     rcx, cs:__security_cookie
0x1800016a7  jnz     short ReportFailure
0x1800016a9  rol     rcx, 10h
0x1800016ad  test    cx, 0FFFFh
0x1800016b2  jnz     short RestoreRcx
0x1800016b4  retn
0x1800016b5  ror     rcx, 10h; StackCookie
0x1800016b9  jmp     __report_gsfailure
```
