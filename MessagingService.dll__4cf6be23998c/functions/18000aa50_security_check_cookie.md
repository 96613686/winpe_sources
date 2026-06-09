# __security_check_cookie

- ea: `0x18000aa50`
- end: `0x18000aa6e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `42`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001148`
- `0x1800011d8`
- `0x1800012d0`
- `0x180001394`
- `0x180002b6c`
- `0x180002e70`
- `0x180003090`
- `0x180003500`
- `0x1800035d0`
- `0x180003678`
- `0x180004984`
- `0x180004ad8`
- `0x180004c48`
- `0x1800051cc`
- `0x180005364`
- `0x180005720`
- `0x1800058c8`
- `0x180005bd4`
- `0x180005d98`
- `0x180005fe8`
- `0x1800067bc`
- `0x1800068f8`
- `0x180006c30`
- `0x180006d00`
- `0x180007318`
- `0x18000740c`
- `0x18000749c`
- `0x180007594`
- `0x180007930`
- `0x180007d50`
- `0x1800080c8`
- `0x180008168`
- `0x1800088dc`
- `0x180008d68`
- `0x180008e54`
- `0x180009120`
- `0x180009524`
- `0x180009be4`
- `0x180009e58`
- `0x18000a328`
- `0x18000a78c`

## callees

- `0x180002970`
- `0x18000aa50`

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
0x18000aa50  cmp     rcx, cs:__security_cookie
0x18000aa57  jnz     short ReportFailure
0x18000aa59  rol     rcx, 10h
0x18000aa5d  test    cx, 0FFFFh
0x18000aa62  jnz     short RestoreRcx
0x18000aa64  retn
0x18000aa65  ror     rcx, 10h
0x18000aa69  jmp     __report_gsfailure
```
