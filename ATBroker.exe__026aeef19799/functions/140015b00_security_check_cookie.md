# __security_check_cookie

- ea: `0x140015b00`
- end: `0x140015b1e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `47`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012e0`
- `0x1400013a4`
- `0x140001658`
- `0x140001950`
- `0x14000278c`
- `0x1400032a4`
- `0x140003538`
- `0x1400040c8`
- `0x140004498`
- `0x1400048b8`
- `0x140004974`
- `0x140004ee0`
- `0x140005c44`
- `0x140005f00`
- `0x1400061e4`
- `0x1400069b0`
- `0x140006a78`
- `0x1400071dc`
- `0x1400077a0`
- `0x140007c10`
- `0x140007d1c`
- `0x1400086cc`
- `0x140009264`
- `0x1400097a0`
- `0x140009918`
- `0x140009e9c`
- `0x14000a958`
- `0x14000acd4`
- `0x14000b250`
- `0x14000bf04`
- `0x14000d3a0`
- `0x14000d498`
- `0x14000d778`
- `0x14000ddb0`
- `0x14000e538`
- `0x14000ee8c`
- `0x14000fe74`
- `0x140011518`
- `0x140011a40`
- `0x140011c60`
- `0x140012cbc`
- `0x14001317c`
- `0x1400143ac`
- `0x140015644`
- `0x140015830`
- `0x1400158e4`

## callees

- `0x1400021a0`
- `0x140015b00`

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
0x140015b00  cmp     rcx, cs:__security_cookie
0x140015b07  jnz     short loc_140015B19
0x140015b09  rol     rcx, 10h
0x140015b0d  test    cx, 0FFFFh
0x140015b12  jnz     short loc_140015B15
0x140015b14  retn
0x140015b15  ror     rcx, 10h
0x140015b19  jmp     __report_gsfailure
```
