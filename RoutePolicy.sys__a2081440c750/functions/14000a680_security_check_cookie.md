# __security_check_cookie

- ea: `0x14000a680`
- end: `0x14000a69e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `48`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010b0`
- `0x14000116c`
- `0x140001244`
- `0x1400012f0`
- `0x1400013b0`
- `0x140001440`
- `0x140001bfc`
- `0x140001d94`
- `0x140002590`
- `0x140002618`
- `0x140002e68`
- `0x140002ff0`
- `0x140003340`
- `0x1400037a4`
- `0x140003dac`
- `0x140003f18`
- `0x140004330`
- `0x140004800`
- `0x140004a84`
- `0x140004f20`
- `0x140005034`
- `0x140005610`
- `0x140005874`
- `0x140005b60`
- `0x140005efc`
- `0x14000607c`
- `0x14000646c`
- `0x140006570`
- `0x14000664c`
- `0x140006afc`
- `0x140006cc4`
- `0x140006e28`
- `0x140007110`
- `0x140007280`
- `0x140007da0`
- `0x140008060`
- `0x14000810c`
- `0x1400081ec`
- `0x1400083a0`
- `0x14000865c`
- `0x140009390`
- `0x140009ff8`
- `0x14000a54c`
- `0x140017008`
- `0x140017e48`
- `0x1400189bc`
- `0x14001903c`

## callees

- `0x140001560`
- `0x14000a680`

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
0x14000a680  cmp     rcx, cs:__security_cookie
0x14000a687  jnz     short ReportFailure
0x14000a689  rol     rcx, 10h
0x14000a68d  test    cx, 0FFFFh
0x14000a692  jnz     short RestoreRcx
0x14000a694  retn
0x14000a695  ror     rcx, 10h; StackCookie
0x14000a699  jmp     __report_gsfailure
```
