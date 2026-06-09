# __security_check_cookie

- ea: `0x140038d10`
- end: `0x140038d2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `53`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400010bc`
- `0x14000111c`
- `0x140002aa4`
- `0x140004810`
- `0x14000717c`
- `0x14000726c`
- `0x140007b30`
- `0x140007c98`
- `0x1400090cc`
- `0x1400092d8`
- `0x140009a64`
- `0x140009e18`
- `0x14000a650`
- `0x14000b590`
- `0x14000bb58`
- `0x14000cba4`
- `0x14000dd10`
- `0x14000dea0`
- `0x14001260c`
- `0x140012864`
- `0x140013aec`
- `0x1400145ac`
- `0x140014a88`
- `0x140018880`
- `0x14001b264`
- `0x14001b378`
- `0x14001b45c`
- `0x14001be28`
- `0x14001c194`
- `0x14001c4a8`
- `0x14001c788`
- `0x14001ca30`
- `0x14001cd38`
- `0x14001cfcc`
- `0x14001d098`
- `0x14001d9ac`
- `0x140033b78`
- `0x140033e20`
- `0x140033e90`
- `0x140033f60`
- `0x140034450`
- `0x140034a40`
- `0x140034c60`
- `0x140034f00`
- `0x140035770`
- `0x140035980`
- `0x140035ad0`
- `0x140035c80`
- `0x140036e5c`

## callees

- `0x140003440`
- `0x140038d10`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
LABEL_4:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto LABEL_4;
  }
}

```

## disassembly

```asm
0x140038d10  cmp     rcx, cs:__security_cookie
0x140038d17  jnz     short loc_140038D29
0x140038d19  rol     rcx, 10h
0x140038d1d  test    cx, 0FFFFh
0x140038d22  jnz     short loc_140038D25
0x140038d24  retn
0x140038d25  ror     rcx, 10h
0x140038d29  jmp     __report_gsfailure
```
