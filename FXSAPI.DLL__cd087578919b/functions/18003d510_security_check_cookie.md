# __security_check_cookie

- ea: `0x18003d510`
- end: `0x18003d52e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `64`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180002738`
- `0x1800029e8`
- `0x180003648`
- `0x1800039f4`
- `0x180003dcc`
- `0x180004394`
- `0x180005294`
- `0x180005630`
- `0x180006528`
- `0x180006790`
- `0x180006a0c`
- `0x180007350`
- `0x180008a0c`
- `0x1800098a0`
- `0x1800099bc`
- `0x18000acb0`
- `0x180016de4`
- `0x180018a10`
- `0x1800190d0`
- `0x180019d54`
- `0x18001a7a0`
- `0x18001a82c`
- `0x18001ad28`
- `0x18001ba58`
- `0x180020830`
- `0x1800240f0`
- `0x1800251c0`
- `0x1800254e0`
- `0x1800259ec`
- `0x180025df0`
- `0x180026ef0`
- `0x180027248`
- `0x180028ef0`
- `0x18002bea8`
- `0x18002c1e0`
- `0x18002c31c`
- `0x18002cb24`
- `0x18002cf00`
- `0x18002d0e4`
- `0x18002d54c`
- `0x18002dc40`
- `0x18002de00`
- `0x18002dff4`
- `0x18002e5ac`
- `0x18002ffb8`
- `0x1800309c4`
- `0x1800312c4`
- `0x180031c24`
- `0x1800321cc`
- `0x1800322bc`

## callees

- `0x1800018a0`
- `0x18003d510`

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
0x18003d510  cmp     rcx, cs:__security_cookie
0x18003d517  jnz     short ReportFailure
0x18003d519  rol     rcx, 10h
0x18003d51d  test    cx, 0FFFFh
0x18003d522  jnz     short RestoreRcx
0x18003d524  retn
0x18003d525  ror     rcx, 10h
0x18003d529  jmp     __report_gsfailure
```
