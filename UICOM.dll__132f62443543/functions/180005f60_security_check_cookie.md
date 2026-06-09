# __security_check_cookie

- ea: `0x180005f60`
- end: `0x180005f7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `15`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d0c`
- `0x180001e5c`
- `0x180001f94`
- `0x1800026a4`
- `0x180002d14`
- `0x180002ebc`
- `0x180003378`
- `0x180003a94`
- `0x180003d58`
- `0x180003ea8`
- `0x180004038`
- `0x1800041fc`
- `0x1800049ac`
- `0x180004bac`
- `0x180005a70`

## callees

- `0x1800016f0`
- `0x180005f60`

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
0x180005f60  cmp     rcx, cs:__security_cookie
0x180005f67  jnz     short ReportFailure
0x180005f69  rol     rcx, 10h
0x180005f6d  test    cx, 0FFFFh
0x180005f72  jnz     short RestoreRcx
0x180005f74  retn
0x180005f75  ror     rcx, 10h
0x180005f79  jmp     __report_gsfailure
```
