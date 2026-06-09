# __security_check_cookie

- ea: `0x1800017c0`
- end: `0x1800017de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `16`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001c60`
- `0x180002cdc`
- `0x180002f78`
- `0x180003be4`
- `0x180004340`
- `0x180005ad8`
- `0x180005e7c`
- `0x1800062e0`
- `0x180006e6c`
- `0x180007e54`
- `0x1800081d0`
- `0x1800092e0`
- `0x180009bfc`
- `0x18000b39c`
- `0x18000c030`
- `0x18000c158`

## callees

- `0x1800017c0`
- `0x180002110`

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
