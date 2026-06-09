# __security_check_cookie

- ea: `0x1400015d0`
- end: `0x1400015ee`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `27`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140002f00`
- `0x140004174`
- `0x140005778`
- `0x140005a0c`
- `0x140005b60`
- `0x140006714`
- `0x140008718`
- `0x140008ae8`
- `0x140008ee0`
- `0x14000997c`
- `0x14000a228`
- `0x14000ab00`
- `0x14000bf1c`
- `0x14000c770`
- `0x14000c898`
- `0x14000d15c`
- `0x14000ea5c`
- `0x14000f194`
- `0x14000f8f0`
- `0x1400102f0`
- `0x1400104e4`
- `0x1400108f8`
- `0x140010b20`
- `0x140011540`
- `0x140011730`
- `0x140011ac0`
- `0x140012098`

## callees

- `0x1400015d0`
- `0x140001b80`

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
0x1400015d0  cmp     rcx, cs:__security_cookie
0x1400015d7  jnz     short loc_1400015E9
0x1400015d9  rol     rcx, 10h
0x1400015dd  test    cx, 0FFFFh
0x1400015e2  jnz     short loc_1400015E5
0x1400015e4  retn
0x1400015e5  ror     rcx, 10h; StackCookie
0x1400015e9  jmp     __report_gsfailure
```
