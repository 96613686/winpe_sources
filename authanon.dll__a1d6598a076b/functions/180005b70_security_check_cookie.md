# __security_check_cookie

- ea: `0x180005b70`
- end: `0x180005b8e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `8`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800019d0`
- `0x180001da0`
- `0x180002530`
- `0x1800034c0`
- `0x1800043b8`
- `0x180004fa8`
- `0x180005354`
- `0x180005ad0`

## callees

- `0x1800030f0`
- `0x180005b70`

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
0x180005b70  cmp     rcx, cs:__security_cookie
0x180005b77  jnz     short ReportFailure
0x180005b79  rol     rcx, 10h
0x180005b7d  test    cx, 0FFFFh
0x180005b82  jnz     short RestoreRcx
0x180005b84  retn
0x180005b85  ror     rcx, 10h
0x180005b89  jmp     __report_gsfailure
```
