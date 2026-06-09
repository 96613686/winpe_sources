# __security_check_cookie

- ea: `0x1800016b0`
- end: `0x1800016ce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800026ac`
- `0x1800029e0`
- `0x1800047f8`
- `0x180004b18`
- `0x180005298`
- `0x180005534`
- `0x1800060bc`
- `0x180006460`
- `0x180006830`
- `0x180007294`
- `0x180007610`
- `0x1800084f0`
- `0x180008e0c`
- `0x18000a31c`
- `0x18000ad30`
- `0x18000ae40`
- `0x18000bab4`

## callees

- `0x1800016b0`
- `0x180001c70`

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
0x1800016b0  cmp     rcx, cs:__security_cookie
0x1800016b7  jnz     short ReportFailure
0x1800016b9  rol     rcx, 10h
0x1800016bd  test    cx, 0FFFFh
0x1800016c2  jnz     short RestoreRcx
0x1800016c4  retn
0x1800016c5  ror     rcx, 10h; StackCookie
0x1800016c9  jmp     __report_gsfailure
```
