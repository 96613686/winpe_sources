# __security_check_cookie

- ea: `0x18000c0e0`
- end: `0x18000c0fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `18`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002994`
- `0x180002d5c`
- `0x180003c80`
- `0x180004b10`
- `0x180005154`
- `0x1800053c0`
- `0x180005990`
- `0x180005d5c`
- `0x180006860`
- `0x180008894`
- `0x180008de0`
- `0x180008f00`
- `0x1800090a0`
- `0x180009fa8`
- `0x18000a0f8`
- `0x18000b098`
- `0x18000b300`
- `0x18000bf54`

## callees

- `0x1800019e0`
- `0x18000c0e0`

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
0x18000c0e0  cmp     rcx, cs:__security_cookie
0x18000c0e7  jnz     short ReportFailure
0x18000c0e9  rol     rcx, 10h
0x18000c0ed  test    cx, 0FFFFh
0x18000c0f2  jnz     short RestoreRcx
0x18000c0f4  retn
0x18000c0f5  ror     rcx, 10h
0x18000c0f9  jmp     __report_gsfailure
```
