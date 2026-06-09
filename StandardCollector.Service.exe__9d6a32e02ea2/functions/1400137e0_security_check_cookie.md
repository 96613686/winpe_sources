# __security_check_cookie

- ea: `0x1400137e0`
- end: `0x1400137fe`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `57`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001230`
- `0x140001388`
- `0x140003158`
- `0x140003220`
- `0x14000356c`
- `0x140003760`
- `0x14000385c`
- `0x14000395c`
- `0x140003b50`
- `0x140003c40`
- `0x140003f34`
- `0x1400041b4`
- `0x140004520`
- `0x140005400`
- `0x140005b70`
- `0x140006370`
- `0x140006530`
- `0x140006620`
- `0x140007c28`
- `0x140007f38`
- `0x140008434`
- `0x1400086fc`
- `0x140008b94`
- `0x140008ca8`
- `0x140008e80`
- `0x14000918c`
- `0x1400094c0`
- `0x140009ce4`
- `0x140009f90`
- `0x14000a42c`
- `0x14000bbb0`
- `0x14000bc90`
- `0x14000bdc0`
- `0x14000c290`
- `0x14000d304`
- `0x14000d50c`
- `0x14000e5d4`
- `0x14000e7fc`
- `0x14000eaec`
- `0x14000ec38`
- `0x14000f484`
- `0x14000f510`
- `0x14000f9d4`
- `0x14000fcfc`
- `0x14001008c`
- `0x140010a70`
- `0x140010d8c`
- `0x140010ffc`
- `0x140011b04`
- `0x140011cb0`

## callees

- `0x1400137e0`
- `0x140013f20`

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
0x1400137e0  cmp     rcx, cs:__security_cookie
0x1400137e7  jnz     short ReportFailure
0x1400137e9  rol     rcx, 10h
0x1400137ed  test    cx, 0FFFFh
0x1400137f2  jnz     short RestoreRcx
0x1400137f4  retn
0x1400137f5  ror     rcx, 10h
0x1400137f9  jmp     __report_gsfailure
```
