# __security_check_cookie

- ea: `0x18000e990`
- end: `0x18000e9ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800019a0`
- `0x180003040`
- `0x180003184`
- `0x180003b30`
- `0x180003ddc`
- `0x1800042fc`
- `0x180004b10`
- `0x1800051cc`
- `0x180005778`
- `0x180005b40`
- `0x180008080`
- `0x18000845c`
- `0x18000888c`
- `0x18000986c`
- `0x18000a2c0`
- `0x18000a510`
- `0x18000ace8`
- `0x18000b328`
- `0x18000b4d4`
- `0x18000b840`
- `0x18000dbf0`
- `0x18000dd40`
- `0x18000e468`
- `0x18000e880`

## callees

- `0x1800027b0`
- `0x18000e990`

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
0x18000e990  cmp     rcx, cs:__security_cookie
0x18000e997  jnz     short ReportFailure
0x18000e999  rol     rcx, 10h
0x18000e99d  test    cx, 0FFFFh
0x18000e9a2  jnz     short RestoreRcx
0x18000e9a4  retn
0x18000e9a5  ror     rcx, 10h
0x18000e9a9  jmp     __report_gsfailure
```
