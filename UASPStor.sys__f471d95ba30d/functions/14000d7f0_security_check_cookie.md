# __security_check_cookie

- ea: `0x14000d7f0`
- end: `0x14000d80e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `13`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400019d0`
- `0x140003f50`
- `0x140004d5c`
- `0x140005490`
- `0x140005eb0`
- `0x140006dc8`
- `0x14000a2b8`
- `0x14000c368`
- `0x14000cd68`
- `0x14000d188`
- `0x14000d6bc`
- `0x140015850`
- `0x1400171e0`

## callees

- `0x140001010`
- `0x14000d7f0`

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
0x14000d7f0  cmp     rcx, cs:__security_cookie
0x14000d7f7  jnz     short ReportFailure
0x14000d7f9  rol     rcx, 10h
0x14000d7fd  test    cx, 0FFFFh
0x14000d802  jnz     short RestoreRcx
0x14000d804  retn
0x14000d805  ror     rcx, 10h; StackCookie
0x14000d809  jmp     __report_gsfailure
```
