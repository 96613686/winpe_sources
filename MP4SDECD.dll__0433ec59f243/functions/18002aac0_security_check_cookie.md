# __security_check_cookie

- ea: `0x18002aac0`
- end: `0x18002aade`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `50`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012114`
- `0x180012818`
- `0x180013704`
- `0x18001385c`
- `0x180013944`
- `0x180013fa0`
- `0x180014f1c`
- `0x1800168c0`
- `0x1800193c8`
- `0x180019b90`
- `0x18001da00`
- `0x18001daf0`
- `0x18001e550`
- `0x180027d0c`
- `0x180027e08`
- `0x180027f28`
- `0x1800280ac`
- `0x180028520`
- `0x180028670`
- `0x180028c80`
- `0x180029020`
- `0x18002c2e8`
- `0x18002d190`
- `0x18002d360`
- `0x18002df70`
- `0x18002e240`
- `0x18002e4e4`
- `0x18002e7d4`
- `0x18002ea10`
- `0x180031ac0`
- `0x180031b90`
- `0x180031d2c`
- `0x180031e2c`
- `0x18003928c`
- `0x18003baf0`
- `0x18003bbc0`
- `0x18003bc90`
- `0x18003bd60`
- `0x18003be40`
- `0x18003bf20`
- `0x18003c5a0`
- `0x180043120`
- `0x1800431f0`
- `0x1800432c0`
- `0x180043390`
- `0x1800434c0`
- `0x1800435a0`
- `0x180043790`
- `0x1800438e0`
- `0x180045790`

## callees

- `0x18002aac0`
- `0x18002aff0`

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
0x18002aac0  cmp     rcx, cs:__security_cookie
0x18002aac7  jnz     short ReportFailure
0x18002aac9  rol     rcx, 10h
0x18002aacd  test    cx, 0FFFFh
0x18002aad2  jnz     short RestoreRcx
0x18002aad4  retn
0x18002aad5  ror     rcx, 10h; StackCookie
0x18002aad9  jmp     __report_gsfailure
```
