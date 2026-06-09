# __security_check_cookie

- ea: `0x180006f60`
- end: `0x180006f7e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `144`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001160`
- `0x180001280`
- `0x1800013c8`
- `0x18000167c`
- `0x180001984`
- `0x180001bc4`
- `0x180001cec`
- `0x180001df8`
- `0x180001f14`
- `0x18000203c`
- `0x180002178`
- `0x1800022f4`
- `0x180002458`
- `0x180002590`
- `0x1800027b8`
- `0x1800028f4`
- `0x180002a40`
- `0x180002b90`
- `0x180002cf4`
- `0x180002e40`
- `0x180002fa0`
- `0x180003114`
- `0x1800032f0`
- `0x180003468`
- `0x1800035f8`
- `0x180003744`
- `0x1800038a4`
- `0x180003a18`
- `0x180003bc0`
- `0x180003d80`
- `0x18000402c`
- `0x180004138`
- `0x1800041fc`
- `0x1800042d0`
- `0x1800043a4`
- `0x180004484`
- `0x180004588`
- `0x1800046c4`
- `0x180004810`
- `0x18000495c`
- `0x180004ad0`
- `0x180004c5c`
- `0x180004d68`
- `0x180004fa8`
- `0x1800050e4`
- `0x18000523c`
- `0x1800053a8`
- `0x18000551c`
- `0x180005658`

## callees

- `0x180006f60`
- `0x1800073c0`

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
0x180006f60  cmp     rcx, cs:__security_cookie
0x180006f67  jnz     short ReportFailure
0x180006f69  rol     rcx, 10h
0x180006f6d  test    cx, 0FFFFh
0x180006f72  jnz     short RestoreRcx
0x180006f74  retn
0x180006f75  ror     rcx, 10h; StackCookie
0x180006f79  jmp     __report_gsfailure
```
