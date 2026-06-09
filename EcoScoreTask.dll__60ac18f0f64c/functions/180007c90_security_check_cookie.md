# __security_check_cookie

- ea: `0x180007c90`
- end: `0x180007cae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001560`
- `0x1800024d8`
- `0x180002b24`
- `0x180002db8`
- `0x180002f5c`
- `0x1800031fc`
- `0x180003648`
- `0x180003a54`
- `0x180003ee0`
- `0x180004334`
- `0x180004750`
- `0x180006654`
- `0x180006858`
- `0x180006a60`
- `0x180006f5c`
- `0x1800073f0`
- `0x180007a20`
- `0x180007bec`

## callees

- `0x180002280`
- `0x180007c90`

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
0x180007c90  cmp     rcx, cs:__security_cookie
0x180007c97  jnz     short ReportFailure
0x180007c99  rol     rcx, 10h
0x180007c9d  test    cx, 0FFFFh
0x180007ca2  jnz     short RestoreRcx
0x180007ca4  retn
0x180007ca5  ror     rcx, 10h
0x180007ca9  jmp     __report_gsfailure
```
