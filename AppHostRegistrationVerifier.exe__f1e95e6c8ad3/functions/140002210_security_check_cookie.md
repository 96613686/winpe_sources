# __security_check_cookie

- ea: `0x140002210`
- end: `0x14000222e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `40`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012cc`
- `0x14000135c`
- `0x140001600`
- `0x1400018f8`
- `0x1400019f0`
- `0x140002560`
- `0x14000345c`
- `0x140003628`
- `0x1400038c4`
- `0x14000406c`
- `0x140004e08`
- `0x140004fd0`
- `0x1400053b4`
- `0x140005810`
- `0x140007248`
- `0x140007f10`
- `0x140008150`
- `0x1400083ac`
- `0x140008450`
- `0x1400084f4`
- `0x140008594`
- `0x140008634`
- `0x1400086d4`
- `0x140008774`
- `0x140008ae4`
- `0x1400096a4`
- `0x14000bc30`
- `0x14000be20`
- `0x14000bef8`
- `0x14000c148`
- `0x14000c2c0`
- `0x14000c848`
- `0x14000dfdc`
- `0x14000eb7c`
- `0x14000ed9c`
- `0x14000f3b8`
- `0x14000f854`
- `0x14000ff40`
- `0x140010900`

## callees

- `0x140002210`
- `0x140002240`

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
0x140002210  cmp     rcx, cs:__security_cookie
0x140002217  jnz     short loc_140002229
0x140002219  rol     rcx, 10h
0x14000221d  test    cx, 0FFFFh
0x140002222  jnz     short loc_140002225
0x140002224  retn
0x140002225  ror     rcx, 10h; StackCookie
0x140002229  jmp     __report_gsfailure
```
