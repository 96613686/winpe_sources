# __security_check_cookie

- ea: `0x180001520`
- end: `0x18000153e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `81`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003010`
- `0x1800030c0`
- `0x1800034c0`
- `0x1800035e0`
- `0x1800036d0`
- `0x180003940`
- `0x180003a30`
- `0x180003d50`
- `0x180003fa0`
- `0x1800040d0`
- `0x1800043e0`
- `0x180004550`
- `0x180004a10`
- `0x180004b90`
- `0x180004ca0`
- `0x1800050a0`
- `0x1800053b0`
- `0x1800054a0`
- `0x1800055a0`
- `0x1800056c0`
- `0x1800058b0`
- `0x180005a60`
- `0x180005d00`
- `0x180005ea0`
- `0x1800065c0`
- `0x180006b24`
- `0x1800074e4`
- `0x1800090bc`
- `0x180009508`
- `0x1800097c8`
- `0x180009a4c`
- `0x180009d18`
- `0x18000a528`
- `0x18000b0e4`
- `0x18000b634`
- `0x18000bd94`
- `0x18000c6e8`
- `0x18000edc0`
- `0x18000f3b8`
- `0x180010adc`
- `0x180010eb4`
- `0x18001134c`
- `0x180011800`
- `0x180011e50`
- `0x180012414`
- `0x180012954`
- `0x180012abc`
- `0x180012c24`
- `0x180012e08`
- `0x180012f70`

## callees

- `0x180001520`
- `0x180001b70`

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
0x180001520  cmp     rcx, cs:__security_cookie
0x180001527  jnz     short ReportFailure
0x180001529  rol     rcx, 10h
0x18000152d  test    cx, 0FFFFh
0x180001532  jnz     short RestoreRcx
0x180001534  retn
0x180001535  ror     rcx, 10h; StackCookie
0x180001539  jmp     __report_gsfailure
```
