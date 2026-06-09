# __security_check_cookie

- ea: `0x180007700`
- end: `0x18000771e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `52`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001270`
- `0x180001618`
- `0x180001848`
- `0x180001a38`
- `0x180001f88`
- `0x18000214c`
- `0x180002878`
- `0x180002b20`
- `0x180003988`
- `0x180003b40`
- `0x180003d1c`
- `0x18000421c`
- `0x18000483c`
- `0x1800048ec`
- `0x180004bb4`
- `0x180005394`
- `0x180005538`
- `0x18000572c`
- `0x1800060c0`
- `0x1800063a4`
- `0x1800064b8`
- `0x180006590`
- `0x180008858`
- `0x180009af4`
- `0x180009ff8`
- `0x18000aeb8`
- `0x18000bc88`
- `0x18000c07c`
- `0x18000cbfc`
- `0x1800127dc`
- `0x180012c08`
- `0x180012ff4`
- `0x1800134cc`
- `0x18001479c`
- `0x18001550c`
- `0x180016c18`
- `0x1800170d0`
- `0x180017544`
- `0x180017a54`
- `0x180017ff8`
- `0x1800184e4`
- `0x1800185e8`
- `0x180018704`
- `0x180018c4c`
- `0x18001a11c`
- `0x18001ae20`
- `0x18001b548`
- `0x18001b5f0`
- `0x18001b698`
- `0x18001b740`

## callees

- `0x180007700`
- `0x180007b00`

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
0x180007700  cmp     rcx, cs:__security_cookie
0x180007707  jnz     short ReportFailure
0x180007709  rol     rcx, 10h
0x18000770d  test    cx, 0FFFFh
0x180007712  jnz     short RestoreRcx
0x180007714  retn
0x180007715  ror     rcx, 10h
0x180007719  jmp     __report_gsfailure
```
