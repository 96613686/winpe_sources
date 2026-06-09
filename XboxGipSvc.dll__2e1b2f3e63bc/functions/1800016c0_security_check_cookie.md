# __security_check_cookie

- ea: `0x1800016c0`
- end: `0x1800016de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `20`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002d20`
- `0x180003f18`
- `0x1800041ac`
- `0x180005088`
- `0x180006240`
- `0x1800073b8`
- `0x180007790`
- `0x180007d3c`
- `0x180008f3c`
- `0x180009350`
- `0x180009e38`
- `0x18000a36c`
- `0x18000ae98`
- `0x18000b11c`
- `0x18000b460`
- `0x18000c118`
- `0x18000e90c`
- `0x18000f5d4`
- `0x180010768`
- `0x180011354`

## callees

- `0x1800016c0`
- `0x180001d30`

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
0x1800016c0  cmp     rcx, cs:__security_cookie
0x1800016c7  jnz     short ReportFailure
0x1800016c9  rol     rcx, 10h
0x1800016cd  test    cx, 0FFFFh
0x1800016d2  jnz     short RestoreRcx
0x1800016d4  retn
0x1800016d5  ror     rcx, 10h; StackCookie
0x1800016d9  jmp     __report_gsfailure
```
