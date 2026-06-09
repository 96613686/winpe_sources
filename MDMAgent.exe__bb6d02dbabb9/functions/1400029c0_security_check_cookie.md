# __security_check_cookie

- ea: `0x1400029c0`
- end: `0x1400029de`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001330`
- `0x140001378`
- `0x14000162c`
- `0x14000169c`
- `0x14000172c`
- `0x140001828`
- `0x140001acc`
- `0x140001dc4`
- `0x140002004`
- `0x1400020e4`
- `0x140002188`
- `0x140002274`
- `0x140002338`
- `0x140003a44`
- `0x140003eb4`
- `0x140004174`
- `0x140004e2c`
- `0x140005144`
- `0x140005534`
- `0x140005950`
- `0x140005a44`
- `0x140007160`
- `0x140007820`
- `0x140007fb0`
- `0x14000829c`
- `0x140009804`
- `0x140009ae8`
- `0x14000a1a0`
- `0x14000a374`
- `0x14000bac4`
- `0x14000bc88`
- `0x14000bdd4`
- `0x14000c314`
- `0x14000ce68`
- `0x14000d480`
- `0x14000d780`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ec7c`
- `0x14000f604`
- `0x14000f69c`
- `0x14000f9a4`
- `0x14000fd3c`
- `0x140010618`
- `0x140010718`
- `0x140010cf0`
- `0x1400112b0`
- `0x140011e28`
- `0x140012058`

## callees

- `0x1400029c0`
- `0x140002db0`

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
0x1400029c0  cmp     rcx, cs:__security_cookie
0x1400029c7  jnz     short loc_1400029D9
0x1400029c9  rol     rcx, 10h
0x1400029cd  test    cx, 0FFFFh
0x1400029d2  jnz     short loc_1400029D5
0x1400029d4  retn
0x1400029d5  ror     rcx, 10h; StackCookie
0x1400029d9  jmp     __report_gsfailure
```
