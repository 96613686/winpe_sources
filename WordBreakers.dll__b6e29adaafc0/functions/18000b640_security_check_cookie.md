# __security_check_cookie

- ea: `0x18000b640`
- end: `0x18000b65e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012e0`
- `0x1800013a4`
- `0x180001658`
- `0x180001950`
- `0x180002e3c`
- `0x180003548`
- `0x1800037e4`
- `0x180003f90`
- `0x180004334`
- `0x180004874`
- `0x180004bf0`
- `0x1800061bc`
- `0x180007150`
- `0x180007dd8`
- `0x180008340`
- `0x1800094b0`
- `0x180009730`
- `0x180009f90`
- `0x18000b0a0`
- `0x18000b530`

## callees

- `0x1800029f0`
- `0x18000b640`

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
0x18000b640  cmp     rcx, cs:__security_cookie
0x18000b647  jnz     short ReportFailure
0x18000b649  rol     rcx, 10h
0x18000b64d  test    cx, 0FFFFh
0x18000b652  jnz     short RestoreRcx
0x18000b654  retn
0x18000b655  ror     rcx, 10h
0x18000b659  jmp     __report_gsfailure
```
