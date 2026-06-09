# __security_check_cookie

- ea: `0x140002930`
- end: `0x14000294e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `65`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140001010`
- `0x14000132c`
- `0x140001374`
- `0x140001628`
- `0x140001698`
- `0x140001728`
- `0x140001824`
- `0x140001ac8`
- `0x140001dc0`
- `0x140001fe8`
- `0x1400020c8`
- `0x14000216c`
- `0x140002258`
- `0x14000231c`
- `0x140003994`
- `0x140003e04`
- `0x1400040b0`
- `0x140004d88`
- `0x140004fe4`
- `0x1400053a4`
- `0x1400057a0`
- `0x140005888`
- `0x140006ec0`
- `0x140007560`
- `0x140007c90`
- `0x140007f34`
- `0x140009414`
- `0x1400096dc`
- `0x140009d3c`
- `0x140009f10`
- `0x14000b5a0`
- `0x14000b754`
- `0x14000b894`
- `0x14000bdc4`
- `0x14000c89c`
- `0x14000ce98`
- `0x14000d0fc`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e530`
- `0x14000ee6c`
- `0x14000ef04`
- `0x14000f1f8`
- `0x14000f56c`
- `0x14000fe10`
- `0x14000ff08`
- `0x1400104c0`
- `0x140010a68`
- `0x14001162c`
- `0x140011850`

## callees

- `0x140002930`
- `0x140002d20`

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
0x140002930  cmp     rcx, cs:__security_cookie
0x140002937  jnz     short loc_140002949
0x140002939  rol     rcx, 10h
0x14000293d  test    cx, 0FFFFh
0x140002942  jnz     short loc_140002945
0x140002944  retn
0x140002945  ror     rcx, 10h; StackCookie
0x140002949  jmp     __report_gsfailure
```
