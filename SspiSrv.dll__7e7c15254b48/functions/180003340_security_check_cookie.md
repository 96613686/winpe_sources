# __security_check_cookie

- ea: `0x180003340`
- end: `0x18000335e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001470`
- `0x180001540`
- `0x1800016d0`
- `0x180001aa0`
- `0x180001bf0`
- `0x18000233c`
- `0x1800026d0`
- `0x180002ad0`
- `0x180002d60`
- `0x180002fb0`
- `0x1800030d0`
- `0x180003170`
- `0x180003244`

## callees

- `0x180002140`
- `0x180003340`

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
0x180003340  cmp     rcx, cs:__security_cookie
0x180003347  jnz     short ReportFailure
0x180003349  rol     rcx, 10h
0x18000334d  test    cx, 0FFFFh
0x180003352  jnz     short RestoreRcx
0x180003354  retn
0x180003355  ror     rcx, 10h
0x180003359  jmp     __report_gsfailure
```
