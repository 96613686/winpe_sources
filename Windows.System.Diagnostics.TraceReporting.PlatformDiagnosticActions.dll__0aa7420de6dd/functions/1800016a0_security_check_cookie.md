# __security_check_cookie

- ea: `0x1800016a0`
- end: `0x1800016be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800027d4`
- `0x180002a80`
- `0x180003018`
- `0x1800033e8`
- `0x180003954`
- `0x180003cd0`
- `0x18000560c`
- `0x180005ad0`
- `0x180005f30`
- `0x1800062c0`
- `0x180006580`
- `0x180006730`
- `0x1800068f8`
- `0x180006b50`
- `0x180007780`
- `0x180008de0`
- `0x180009e3c`

## callees

- `0x1800016a0`
- `0x180001c60`

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
0x1800016a0  cmp     rcx, cs:__security_cookie
0x1800016a7  jnz     short ReportFailure
0x1800016a9  rol     rcx, 10h
0x1800016ad  test    cx, 0FFFFh
0x1800016b2  jnz     short RestoreRcx
0x1800016b4  retn
0x1800016b5  ror     rcx, 10h; StackCookie
0x1800016b9  jmp     __report_gsfailure
```
