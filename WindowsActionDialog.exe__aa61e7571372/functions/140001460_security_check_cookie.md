# __security_check_cookie

- ea: `0x140001460`
- end: `0x14000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `28`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1400020a8`
- `0x1400027a4`
- `0x140002a48`
- `0x140002b70`
- `0x140003888`
- `0x140003c20`
- `0x1400040e4`
- `0x1400046a4`
- `0x140004a1c`
- `0x140004b48`
- `0x140004da8`
- `0x140004f6c`
- `0x140005ce8`
- `0x140005da0`
- `0x140006734`
- `0x140006f24`
- `0x140007000`
- `0x140007104`
- `0x1400078c0`
- `0x140007a78`
- `0x140008124`
- `0x140008368`
- `0x14000849c`
- `0x1400086f0`
- `0x140008790`
- `0x140008a3c`
- `0x140009080`
- `0x1400091b4`

## callees

- `0x140001460`
- `0x140001ab0`

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
0x140001460  cmp     rcx, cs:__security_cookie
0x140001467  jnz     short loc_140001479
0x140001469  rol     rcx, 10h
0x14000146d  test    cx, 0FFFFh
0x140001472  jnz     short loc_140001475
0x140001474  retn
0x140001475  ror     rcx, 10h; StackCookie
0x140001479  jmp     __report_gsfailure
```
