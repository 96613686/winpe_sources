# __security_check_cookie

- ea: `0x140013730`
- end: `0x14001374e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400010c0`
- `0x140001460`
- `0x140001870`
- `0x140001be0`
- `0x140001fb0`
- `0x140002760`
- `0x140002a30`
- `0x140003210`
- `0x140003640`
- `0x1400039dc`
- `0x140003d14`
- `0x140003e40`
- `0x14000411c`
- `0x140004364`
- `0x140004998`
- `0x140004dd4`
- `0x140004fc0`
- `0x140005138`
- `0x140005424`
- `0x1400055d8`
- `0x140005d4c`
- `0x1400061a0`
- `0x140006630`
- `0x140006810`
- `0x140007044`
- `0x140007250`
- `0x14000748c`
- `0x140007890`
- `0x140007b60`
- `0x140007e5c`
- `0x140008598`
- `0x140008d3c`
- `0x140009390`
- `0x140009530`
- `0x14000995c`
- `0x140009b9c`
- `0x14000a3a0`
- `0x14000a4bc`
- `0x14000a7a0`
- `0x14000aa50`
- `0x14000accc`
- `0x14000af40`
- `0x14000b4c4`
- `0x14000b7bc`
- `0x14000bf64`
- `0x14000c434`
- `0x14000c658`
- `0x14000c9a4`
- `0x14000cd20`
- `0x14000d140`

## callees

- `0x1400035f0`
- `0x140013730`

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
0x140013730  cmp     rcx, cs:__security_cookie
0x140013737  jnz     short ReportFailure
0x140013739  rol     rcx, 10h
0x14001373d  test    cx, 0FFFFh
0x140013742  jnz     short RestoreRcx
0x140013744  retn
0x140013745  ror     rcx, 10h; StackCookie
0x140013749  jmp     __report_gsfailure
```
