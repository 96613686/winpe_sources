# __security_check_cookie

- ea: `0x180002350`
- end: `0x18000236e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `55`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x1800012bc`
- `0x1800015b4`
- `0x18000178c`
- `0x180001a64`
- `0x180001b28`
- `0x180003dbc`
- `0x180004068`
- `0x180004e58`
- `0x18000522c`
- `0x18000568c`
- `0x180006304`
- `0x180006680`
- `0x180007804`
- `0x180007910`
- `0x18000831c`
- `0x180009bac`
- `0x18000a6c0`
- `0x18000a7e8`
- `0x18000aab8`
- `0x18000ae0c`
- `0x18000b3dc`
- `0x18000b940`
- `0x18000dcec`
- `0x18000e180`
- `0x18000fd88`
- `0x18000fed8`
- `0x1800101b8`
- `0x180013c78`
- `0x180015510`
- `0x180016bd0`
- `0x180016ea0`
- `0x1800171a0`
- `0x1800177a0`
- `0x180017de0`
- `0x180018550`
- `0x180018bd4`
- `0x180019c60`
- `0x180019fb0`
- `0x18001a3c0`
- `0x18001c1f8`
- `0x18001fe30`
- `0x180020370`
- `0x180021a30`
- `0x180021c68`
- `0x180022720`
- `0x180023ae0`
- `0x1800240b8`
- `0x1800265b4`
- `0x18002718c`

## callees

- `0x180002350`
- `0x180002870`

## pseudocode

```c
void __cdecl _security_check_cookie(uintptr_t StackCookie)
{
  __int64 v1; // rcx

  if ( StackCookie != _security_cookie )
ReportFailure:
    _report_gsfailure(StackCookie);
  v1 = __ROL8__(StackCookie, 16);
  if ( (_WORD)v1 )
  {
    StackCookie = __ROR8__(v1, 16);
    goto ReportFailure;
  }
}

```

## disassembly

```asm
0x180002350  cmp     rcx, cs:__security_cookie
0x180002357  jnz     short ReportFailure
0x180002359  rol     rcx, 10h
0x18000235d  test    cx, 0FFFFh
0x180002362  jnz     short RestoreRcx
0x180002364  retn
0x180002365  ror     rcx, 10h; StackCookie
0x180002369  jmp     __report_gsfailure
```
