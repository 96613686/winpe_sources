# __security_check_cookie

- ea: `0x18002bca0`
- end: `0x18002bcbe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `79`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800016dc`
- `0x1800019f0`
- `0x180003664`
- `0x180003910`
- `0x180003cf4`
- `0x180004010`
- `0x1800043ec`
- `0x1800049a4`
- `0x180004dc4`
- `0x18000697c`
- `0x180007590`
- `0x180008468`
- `0x180009988`
- `0x180009fb0`
- `0x18000a440`
- `0x18000aa6c`
- `0x18000ae30`
- `0x18000b0b0`
- `0x18000b91c`
- `0x18000bf20`
- `0x18000e240`
- `0x18000e888`
- `0x18000f570`
- `0x18000f964`
- `0x18001048c`
- `0x180010750`
- `0x180010e80`
- `0x180011740`
- `0x180012c90`
- `0x180013ad4`
- `0x180013b90`
- `0x180013fbc`
- `0x180014c90`
- `0x1800150a0`
- `0x180015960`
- `0x180015ce0`
- `0x180015e80`
- `0x180016430`
- `0x180016750`
- `0x180016cf0`
- `0x180017a40`
- `0x1800189d0`
- `0x180018f80`
- `0x18001a450`
- `0x18001ae00`
- `0x18001b040`
- `0x18001b19c`
- `0x18001b314`

## callees

- `0x180002bb0`
- `0x18002bca0`

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
0x18002bca0  cmp     rcx, cs:__security_cookie
0x18002bca7  jnz     short ReportFailure
0x18002bca9  rol     rcx, 10h
0x18002bcad  test    cx, 0FFFFh
0x18002bcb2  jnz     short RestoreRcx
0x18002bcb4  retn
0x18002bcb5  ror     rcx, 10h
0x18002bcb9  jmp     __report_gsfailure
```
