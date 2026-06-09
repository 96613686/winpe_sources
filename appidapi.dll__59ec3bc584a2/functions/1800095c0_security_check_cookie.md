# __security_check_cookie

- ea: `0x1800095c0`
- end: `0x1800095de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `14`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022c4`
- `0x180002ce0`
- `0x180003210`
- `0x180003330`
- `0x180003b90`
- `0x180003d30`
- `0x18000423c`
- `0x180004980`
- `0x180005740`
- `0x1800061c8`
- `0x180007274`
- `0x180007ccc`
- `0x180007d68`
- `0x180008be4`

## callees

- `0x180001f90`
- `0x1800095c0`

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
0x1800095c0  cmp     rcx, cs:__security_cookie
0x1800095c7  jnz     short ReportFailure
0x1800095c9  rol     rcx, 10h
0x1800095cd  test    cx, 0FFFFh
0x1800095d2  jnz     short RestoreRcx
0x1800095d4  retn
0x1800095d5  ror     rcx, 10h
0x1800095d9  jmp     __report_gsfailure
```
