# __security_check_cookie

- ea: `0x1400016a0`
- end: `0x1400016be`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `31`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002a18`
- `0x140002cb4`
- `0x140003258`
- `0x1400035fc`
- `0x140003b54`
- `0x140003ed0`
- `0x1400057fc`
- `0x140005cb0`
- `0x14000641c`
- `0x140007210`
- `0x140007778`
- `0x140008784`
- `0x1400097c0`
- `0x140009dd8`
- `0x140009e94`
- `0x14000a388`
- `0x14000a75c`
- `0x14000b5b4`
- `0x14000bf30`
- `0x14000ded8`
- `0x14000e510`
- `0x14000e62c`
- `0x14000eb60`
- `0x14000f280`
- `0x14000f54c`
- `0x140010a68`
- `0x140010c90`
- `0x140010fe0`
- `0x1400110b8`
- `0x14001126c`
- `0x1400113e4`

## callees

- `0x1400016a0`
- `0x140001f90`

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
0x1400016a0  cmp     rcx, cs:__security_cookie
0x1400016a7  jnz     short loc_1400016B9
0x1400016a9  rol     rcx, 10h
0x1400016ad  test    cx, 0FFFFh
0x1400016b2  jnz     short loc_1400016B5
0x1400016b4  retn
0x1400016b5  ror     rcx, 10h; StackCookie
0x1400016b9  jmp     __report_gsfailure
```
