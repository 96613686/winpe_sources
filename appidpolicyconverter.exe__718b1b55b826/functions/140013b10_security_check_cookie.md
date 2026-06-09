# __security_check_cookie

- ea: `0x140013b10`
- end: `0x140013b2e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `75`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x14000104c`
- `0x14000112c`
- `0x140001218`
- `0x140001274`
- `0x140002c74`
- `0x140002d94`
- `0x1400030a0`
- `0x140003330`
- `0x1400036fc`
- `0x140005be0`
- `0x140005ebc`
- `0x140006154`
- `0x1400064f8`
- `0x14000775c`
- `0x140007edc`
- `0x140008f74`
- `0x140009520`
- `0x140009c34`
- `0x14000a388`
- `0x14000a470`
- `0x14000a560`
- `0x14000a9ac`
- `0x14000ac40`
- `0x14000af60`
- `0x14000bd68`
- `0x14000bee4`
- `0x14000c138`
- `0x14000c308`
- `0x14000c938`
- `0x14000cba0`
- `0x14000cdf0`
- `0x14000cf50`
- `0x14000da10`
- `0x14000dc30`
- `0x14000dd60`
- `0x14000e238`
- `0x14000e340`
- `0x14000e4f0`
- `0x14000e5e0`
- `0x14000f200`
- `0x14000f44c`
- `0x14000f610`
- `0x14000f958`
- `0x14000fbd8`
- `0x14000fcec`
- `0x14000ffb8`
- `0x14001036c`
- `0x140010c78`
- `0x140010d90`

## callees

- `0x1400019f0`
- `0x140013b10`

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
0x140013b10  cmp     rcx, cs:__security_cookie
0x140013b17  jnz     short loc_140013B29
0x140013b19  rol     rcx, 10h
0x140013b1d  test    cx, 0FFFFh
0x140013b22  jnz     short loc_140013B25
0x140013b24  retn
0x140013b25  ror     rcx, 10h
0x140013b29  jmp     __report_gsfailure
```
