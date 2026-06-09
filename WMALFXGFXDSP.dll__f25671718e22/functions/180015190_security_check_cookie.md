# __security_check_cookie

- ea: `0x180015190`
- end: `0x1800151ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `34`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x180001358`
- `0x180001650`
- `0x180002bd0`
- `0x18000631c`
- `0x1800063dc`
- `0x18000662c`
- `0x180006970`
- `0x180006ca0`
- `0x180007030`
- `0x18000a388`
- `0x18000bc20`
- `0x18000c5d8`
- `0x18000fdb4`
- `0x180010e2c`
- `0x180013990`
- `0x180014e94`
- `0x1800168c8`
- `0x180016a4c`
- `0x180016e08`
- `0x180060df8`
- `0x180075d04`
- `0x180075f44`
- `0x1800763d4`
- `0x180076668`
- `0x1800770c8`
- `0x18007732c`
- `0x1800774dc`
- `0x180077a80`
- `0x180077e54`
- `0x1800794d0`
- `0x18008488c`
- `0x180084d64`

## callees

- `0x180015190`
- `0x180015520`

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
0x180015190  cmp     rcx, cs:__security_cookie
0x180015197  jnz     short loc_1800151A9
0x180015199  rol     rcx, 10h
0x18001519d  test    cx, 0FFFFh
0x1800151a2  jnz     short loc_1800151A5
0x1800151a4  retn
0x1800151a5  ror     rcx, 10h; StackCookie
0x1800151a9  jmp     __report_gsfailure
```
