# __security_check_cookie

- ea: `0x1800017c0`
- end: `0x1800017de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d44`
- `0x180002fd8`
- `0x180003bf8`
- `0x180003f9c`
- `0x18000436c`
- `0x180004dc4`
- `0x180005140`
- `0x180006020`
- `0x18000693c`
- `0x180007e4c`
- `0x180008860`
- `0x180008988`
- `0x180009810`
- `0x180009ba0`
- `0x18000a490`
- `0x18000a584`
- `0x18000a934`
- `0x18000abe0`
- `0x18000b000`
- `0x18000b330`
- `0x18000b4c0`
- `0x18000b678`
- `0x18000c3b0`
- `0x18000ca1c`
- `0x18000d300`
- `0x18000d524`
- `0x18000e288`

## callees

- `0x1800017c0`
- `0x180002170`

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
0x1800017c0  cmp     rcx, cs:__security_cookie
0x1800017c7  jnz     short ReportFailure
0x1800017c9  rol     rcx, 10h
0x1800017cd  test    cx, 0FFFFh
0x1800017d2  jnz     short RestoreRcx
0x1800017d4  retn
0x1800017d5  ror     rcx, 10h; StackCookie
0x1800017d9  jmp     __report_gsfailure
```
