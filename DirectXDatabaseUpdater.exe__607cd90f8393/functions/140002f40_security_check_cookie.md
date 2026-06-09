# __security_check_cookie

- ea: `0x140002f40`
- end: `0x140002f5e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `54`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400012cc`
- `0x140001590`
- `0x14000187c`
- `0x1400018ec`
- `0x14000197c`
- `0x140001a3c`
- `0x140001ce0`
- `0x140001fd8`
- `0x14000209c`
- `0x140002194`
- `0x1400026d0`
- `0x140002950`
- `0x14000329c`
- `0x140004264`
- `0x140004828`
- `0x140004ad4`
- `0x1400050c8`
- `0x1400066d8`
- `0x140006844`
- `0x140006a40`
- `0x140006c80`
- `0x140007224`
- `0x140007620`
- `0x140007ad8`
- `0x1400082e8`
- `0x1400083ac`
- `0x140009660`
- `0x140009d04`
- `0x14000b0cc`
- `0x14000bb94`
- `0x14000d0bc`
- `0x14000d384`
- `0x14000d940`
- `0x14000eb60`
- `0x14000ed68`
- `0x14000f2a4`
- `0x14000f654`
- `0x14000fa90`
- `0x1400100e0`
- `0x140010ac0`
- `0x140010ce8`
- `0x140011418`
- `0x140011804`
- `0x1400120b0`
- `0x1400122f8`
- `0x140012aa8`
- `0x140012e40`
- `0x140013310`
- `0x140014900`

## callees

- `0x140002f40`
- `0x140003260`

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
0x140002f40  cmp     rcx, cs:__security_cookie
0x140002f47  jnz     short loc_140002F59
0x140002f49  rol     rcx, 10h
0x140002f4d  test    cx, 0FFFFh
0x140002f52  jnz     short loc_140002F55
0x140002f54  retn
0x140002f55  ror     rcx, 10h; StackCookie
0x140002f59  jmp     __report_gsfailure
```
