# __security_check_cookie

- ea: `0x14001bf00`
- end: `0x14001bf1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `203`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001000`
- `0x1400012c0`
- `0x140001460`
- `0x1400016e4`
- `0x140001944`
- `0x140001b1c`
- `0x140002288`
- `0x140002590`
- `0x140002750`
- `0x140002960`
- `0x140002b70`
- `0x140002dc4`
- `0x140002f48`
- `0x140003100`
- `0x1400033a8`
- `0x140003688`
- `0x140003914`
- `0x140004400`
- `0x140004a8c`
- `0x140004b48`
- `0x140007c98`
- `0x14000b120`
- `0x14000e06c`
- `0x14000e470`
- `0x14000f3f0`
- `0x14000f758`
- `0x140010590`
- `0x140013b2c`
- `0x1400140cc`
- `0x14001481c`
- `0x1400166b0`
- `0x140017a4c`
- `0x140018308`
- `0x1400191f8`
- `0x140019670`
- `0x140019778`
- `0x140019898`
- `0x14001b214`
- `0x14001c7fc`
- `0x14001d408`
- `0x14001d50c`
- `0x14001f9c8`
- `0x14001fea4`
- `0x1400205bc`
- `0x140021a80`
- `0x140023050`
- `0x140023604`
- `0x140025394`
- `0x140025ad8`
- `0x140025d90`

## callees

- `0x14001bf00`
- `0x14001bfd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14001bf00  cmp     rcx, cs:__security_cookie
0x14001bf07  jnz     short ReportFailure
0x14001bf09  rol     rcx, 10h
0x14001bf0d  test    cx, 0FFFFh
0x14001bf12  jnz     short RestoreRcx
0x14001bf14  retn
0x14001bf15  ror     rcx, 10h; StackCookie
0x14001bf19  jmp     __report_gsfailure
```
