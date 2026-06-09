# __security_check_cookie

- ea: `0x140003620`
- end: `0x14000363e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `63`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x140001304`
- `0x14000134c`
- `0x1400013f8`
- `0x1400014c0`
- `0x14000156c`
- `0x140001640`
- `0x140001704`
- `0x14000177c`
- `0x140001a30`
- `0x140001d70`
- `0x14000205c`
- `0x140002370`
- `0x1400023e0`
- `0x140002470`
- `0x140002554`
- `0x140002614`
- `0x1400026f4`
- `0x140002998`
- `0x140002c90`
- `0x140002d54`
- `0x140002e28`
- `0x140004a78`
- `0x140005128`
- `0x1400053dc`
- `0x140006028`
- `0x140006ac8`
- `0x140006d5c`
- `0x1400099a8`
- `0x14000a67c`
- `0x14000a7e8`
- `0x14000abf8`
- `0x14000b0d8`
- `0x14000c730`
- `0x14000d4d8`
- `0x14000db40`
- `0x14000e370`
- `0x14000e680`
- `0x14000f14c`
- `0x140010da0`
- `0x140010f10`
- `0x1400111ac`
- `0x1400115c4`
- `0x140012068`
- `0x140012754`
- `0x1400137d4`
- `0x140016940`
- `0x140016a54`
- `0x140016ea0`
- `0x140017060`

## callees

- `0x140003620`
- `0x140003c00`

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
0x140003620  cmp     rcx, cs:__security_cookie
0x140003627  jnz     short loc_140003639
0x140003629  rol     rcx, 10h
0x14000362d  test    cx, 0FFFFh
0x140003632  jnz     short loc_140003635
0x140003634  retn
0x140003635  ror     rcx, 10h; StackCookie
0x140003639  jmp     __report_gsfailure
```
