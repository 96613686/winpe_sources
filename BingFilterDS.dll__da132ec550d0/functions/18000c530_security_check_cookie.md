# __security_check_cookie

- ea: `0x18000c530`
- end: `0x18000c54e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `25`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x18000178c`
- `0x1800034a0`
- `0x18000374c`
- `0x180003df0`
- `0x18000421c`
- `0x180004994`
- `0x180004d50`
- `0x180006c2c`
- `0x180007780`
- `0x180007a18`
- `0x180007b68`
- `0x180007cbc`
- `0x180008974`
- `0x180008ce0`
- `0x180008e50`
- `0x18000904c`
- `0x180009250`
- `0x180009898`
- `0x180009a78`
- `0x180009b54`
- `0x18000bb9c`
- `0x18000c408`

## callees

- `0x1800029b0`
- `0x18000c530`

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
0x18000c530  cmp     rcx, cs:__security_cookie
0x18000c537  jnz     short ReportFailure
0x18000c539  rol     rcx, 10h
0x18000c53d  test    cx, 0FFFFh
0x18000c542  jnz     short RestoreRcx
0x18000c544  retn
0x18000c545  ror     rcx, 10h
0x18000c549  jmp     __report_gsfailure
```
