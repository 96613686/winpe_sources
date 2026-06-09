# __security_check_cookie

- ea: `0x180008ba0`
- end: `0x180008bbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `12`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800021f0`
- `0x180003654`
- `0x180003a10`
- `0x18000417c`
- `0x1800043dc`
- `0x1800048f0`
- `0x1800058fc`
- `0x1800068c0`
- `0x180007d34`
- `0x18000839c`
- `0x1800086d0`
- `0x180008ad0`

## callees

- `0x180001850`
- `0x180008ba0`

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
0x180008ba0  cmp     rcx, cs:__security_cookie
0x180008ba7  jnz     short ReportFailure
0x180008ba9  rol     rcx, 10h
0x180008bad  test    cx, 0FFFFh
0x180008bb2  jnz     short RestoreRcx
0x180008bb4  retn
0x180008bb5  ror     rcx, 10h
0x180008bb9  jmp     __report_gsfailure
```
