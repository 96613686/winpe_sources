# __security_check_cookie

- ea: `0x14001a8d0`
- end: `0x14001a8ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `80`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x1400010a8`
- `0x14000135c`
- `0x140001654`
- `0x1400030b0`
- `0x140003344`
- `0x140003e28`
- `0x140003fc0`
- `0x140004128`
- `0x140004564`
- `0x140004918`
- `0x140005e34`
- `0x140006a10`
- `0x140006dc8`
- `0x1400071a0`
- `0x140007c64`
- `0x1400097ac`
- `0x1400098b0`
- `0x140009964`
- `0x140009b10`
- `0x14000a034`
- `0x14000a14c`
- `0x14000a39c`
- `0x14000a5e0`
- `0x14000cb14`
- `0x14000cd78`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000e194`
- `0x14000e9bc`
- `0x14000f00c`
- `0x14000f288`
- `0x14000f8f8`
- `0x14000faf4`
- `0x140010a2c`
- `0x140012cc8`
- `0x140012e98`
- `0x140012f38`
- `0x140012fe0`
- `0x14001309c`
- `0x140013170`
- `0x14001326c`
- `0x1400133dc`
- `0x140013a90`
- `0x1400147ec`
- `0x1400149f8`
- `0x140014be4`
- `0x140014f2c`
- `0x140015464`

## callees

- `0x140002380`
- `0x14001a8d0`

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
0x14001a8d0  cmp     rcx, cs:__security_cookie
0x14001a8d7  jnz     short loc_14001A8E9
0x14001a8d9  rol     rcx, 10h
0x14001a8dd  test    cx, 0FFFFh
0x14001a8e2  jnz     short loc_14001A8E5
0x14001a8e4  retn
0x14001a8e5  ror     rcx, 10h
0x14001a8e9  jmp     __report_gsfailure
```
