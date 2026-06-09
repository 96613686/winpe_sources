# __security_check_cookie

- ea: `0x1800789c0`
- end: `0x1800789de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `111`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001980`
- `0x180005650`
- `0x180012094`
- `0x180012200`
- `0x18001e2e8`
- `0x180020bf0`
- `0x180021404`
- `0x180023094`
- `0x1800286a4`
- `0x18002edb0`
- `0x1800310f0`
- `0x180032060`
- `0x180035d1c`
- `0x180037640`
- `0x180039624`
- `0x180039ce0`
- `0x18003a0d0`
- `0x180040e00`
- `0x180041f30`
- `0x1800430d4`
- `0x180043190`
- `0x1800433e8`
- `0x180044838`
- `0x180044d28`
- `0x1800450d0`
- `0x180045440`
- `0x1800454c0`
- `0x180045874`
- `0x180045bb0`
- `0x180045c60`
- `0x180045f50`
- `0x180046160`
- `0x180046684`
- `0x180047dd0`
- `0x1800482ac`
- `0x180048b50`
- `0x18004909c`
- `0x1800497a4`
- `0x18004ad90`
- `0x18004b0a0`
- `0x18004bb30`
- `0x18004df88`
- `0x180054aa0`
- `0x180054f40`
- `0x1800551dc`
- `0x180056820`
- `0x180057ec0`
- `0x180059aa8`
- `0x18005a0d0`
- `0x180062a94`

## callees

- `0x1800789c0`
- `0x1800789f0`

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
0x1800789c0  cmp     rcx, cs:__security_cookie
0x1800789c7  jnz     short ReportFailure
0x1800789c9  rol     rcx, 10h
0x1800789cd  test    cx, 0FFFFh
0x1800789d2  jnz     short RestoreRcx
0x1800789d4  retn
0x1800789d5  ror     rcx, 10h; StackCookie
0x1800789d9  jmp     __report_gsfailure
```
