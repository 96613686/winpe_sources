# __security_check_cookie

- ea: `0x18000cdb0`
- end: `0x18000cdce`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `23`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800023d0`
- `0x180002610`
- `0x180002c24`
- `0x180003984`
- `0x180003ea0`
- `0x1800044a8`
- `0x180004550`
- `0x1800049b8`
- `0x180005454`
- `0x1800055ec`
- `0x1800057c0`
- `0x1800066dc`
- `0x180006f5c`
- `0x18000744c`
- `0x180008790`
- `0x180008ad0`
- `0x180009ae0`
- `0x180009b60`
- `0x18000a954`
- `0x18000b6b8`
- `0x18000b8bc`
- `0x18000cc9c`
- `0x18000e33c`

## callees

- `0x18000cdb0`
- `0x18000ce50`

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
0x18000cdb0  cmp     rcx, cs:__security_cookie
0x18000cdb7  jnz     short ReportFailure
0x18000cdb9  rol     rcx, 10h
0x18000cdbd  test    cx, 0FFFFh
0x18000cdc2  jnz     short RestoreRcx
0x18000cdc4  retn
0x18000cdc5  ror     rcx, 10h
0x18000cdc9  jmp     __report_gsfailure
```
