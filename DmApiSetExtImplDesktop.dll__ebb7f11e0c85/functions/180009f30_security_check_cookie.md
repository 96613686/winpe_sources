# __security_check_cookie

- ea: `0x180009f30`
- end: `0x180009f4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `19`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800022f4`
- `0x180002758`
- `0x180002a18`
- `0x1800031e4`
- `0x180003470`
- `0x1800035b4`
- `0x1800038f4`
- `0x180003cc8`
- `0x180005548`
- `0x180006600`
- `0x180006840`
- `0x1800072c4`
- `0x1800073a0`
- `0x180008680`
- `0x180008830`
- `0x180008bc0`
- `0x180008e10`
- `0x1800093a0`
- `0x180009e0c`

## callees

- `0x1800016e0`
- `0x180009f30`

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
0x180009f30  cmp     rcx, cs:__security_cookie
0x180009f37  jnz     short ReportFailure
0x180009f39  rol     rcx, 10h
0x180009f3d  test    cx, 0FFFFh
0x180009f42  jnz     short RestoreRcx
0x180009f44  retn
0x180009f45  ror     rcx, 10h
0x180009f49  jmp     __report_gsfailure
```
