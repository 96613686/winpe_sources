# __security_check_cookie

- ea: `0x180001ef0`
- end: `0x180001f0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x180002ef0`
- `0x180003184`
- `0x180003978`
- `0x1800040b0`
- `0x1800048e0`
- `0x180005294`
- `0x180005610`
- `0x18000628c`
- `0x18000674c`
- `0x18000689c`
- `0x180006a2c`
- `0x180006c0c`
- `0x180008020`
- `0x18000823c`
- `0x1800084d4`
- `0x1800089e0`
- `0x180008cdc`
- `0x180008f90`
- `0x18000a040`
- `0x18000c604`
- `0x18000caf0`
- `0x18000e7b0`

## callees

- `0x180001ef0`
- `0x180001f20`

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
0x180001ef0  cmp     rcx, cs:__security_cookie
0x180001ef7  jnz     short ReportFailure
0x180001ef9  rol     rcx, 10h
0x180001efd  test    cx, 0FFFFh
0x180001f02  jnz     short RestoreRcx
0x180001f04  retn
0x180001f05  ror     rcx, 10h; StackCookie
0x180001f09  jmp     __report_gsfailure
```
