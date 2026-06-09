# __security_check_cookie

- ea: `0x140002a30`
- end: `0x140002a4e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `58`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001008`
- `0x1400012bc`
- `0x140001560`
- `0x140001858`
- `0x140001a2c`
- `0x140001abc`
- `0x140001b4c`
- `0x140001e24`
- `0x140001ee8`
- `0x140001fe0`
- `0x140002490`
- `0x14000346c`
- `0x140003e3c`
- `0x1400040f0`
- `0x1400048f8`
- `0x140004cc8`
- `0x140005304`
- `0x140005744`
- `0x140006f1c`
- `0x1400074f0`
- `0x140007728`
- `0x140007838`
- `0x1400078f4`
- `0x140007f3c`
- `0x1400087ac`
- `0x140008cac`
- `0x140008f2c`
- `0x1400090b0`
- `0x1400093c0`
- `0x1400097e0`
- `0x140009c30`
- `0x140009e60`
- `0x14000a120`
- `0x14000a314`
- `0x14000a4f0`
- `0x14000a8f0`
- `0x14000b304`
- `0x14000b470`
- `0x14000c164`
- `0x14000c6f0`
- `0x14000d408`
- `0x14000dcc4`
- `0x14000eb6c`
- `0x14000f3ec`
- `0x14000f744`
- `0x14000fa3c`
- `0x14000ffa4`
- `0x14001002c`
- `0x1400102f0`
- `0x140010a24`

## callees

- `0x140002a30`
- `0x140003170`

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
0x140002a30  cmp     rcx, cs:__security_cookie
0x140002a37  jnz     short loc_140002A49
0x140002a39  rol     rcx, 10h
0x140002a3d  test    cx, 0FFFFh
0x140002a42  jnz     short loc_140002A45
0x140002a44  retn
0x140002a45  ror     rcx, 10h; StackCookie
0x140002a49  jmp     __report_gsfailure
```
