# __security_check_cookie

- ea: `0x180001c60`
- end: `0x180001c7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `74`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001180`
- `0x180001224`
- `0x180001310`
- `0x1800013d4`
- `0x180003350`
- `0x180003480`
- `0x180003be4`
- `0x180003eb0`
- `0x180004168`
- `0x180005750`
- `0x18000620c`
- `0x180006b38`
- `0x180006ddc`
- `0x180007b34`
- `0x180007cb0`
- `0x180007f4c`
- `0x180008730`
- `0x180008904`
- `0x180008a2c`
- `0x18000a464`
- `0x18000a718`
- `0x18000a864`
- `0x18000bcec`
- `0x18000c3e0`
- `0x18000c980`
- `0x18000d590`
- `0x18000db20`
- `0x18000de68`
- `0x18000e7f0`
- `0x18000e888`
- `0x18000eb90`
- `0x18000ef24`
- `0x18000fa24`
- `0x18000fb24`
- `0x180010340`
- `0x180010804`
- `0x180010b5c`
- `0x180011980`
- `0x180011bb0`
- `0x180011c10`
- `0x180011ce4`
- `0x180011d68`
- `0x180011e0c`
- `0x180011eb4`
- `0x180011f74`
- `0x1800120f8`
- `0x1800127c4`
- `0x180014f14`
- `0x180014fe8`

## callees

- `0x180001c60`
- `0x180001d20`

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
0x180001c60  cmp     rcx, cs:__security_cookie
0x180001c67  jnz     short ReportFailure
0x180001c69  rol     rcx, 10h
0x180001c6d  test    cx, 0FFFFh
0x180001c72  jnz     short RestoreRcx
0x180001c74  retn
0x180001c75  ror     rcx, 10h; StackCookie
0x180001c79  jmp     __report_gsfailure
```
