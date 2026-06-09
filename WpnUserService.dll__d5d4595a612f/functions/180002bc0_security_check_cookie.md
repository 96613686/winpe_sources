# __security_check_cookie

- ea: `0x180002bc0`
- end: `0x180002bde`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `41`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x180001098`
- `0x180001144`
- `0x18000120c`
- `0x1800014e4`
- `0x1800015a8`
- `0x18000185c`
- `0x180001c7c`
- `0x180001d58`
- `0x180001e50`
- `0x18000214c`
- `0x18000221c`
- `0x180003d68`
- `0x180004014`
- `0x1800045b8`
- `0x180004988`
- `0x180004fb4`
- `0x1800053d4`
- `0x180006d0c`
- `0x180007290`
- `0x1800077ec`
- `0x180007a10`
- `0x180007acc`
- `0x18000896c`
- `0x180009040`
- `0x18000a450`
- `0x18000a598`
- `0x18000a9ac`
- `0x18000b264`
- `0x18000b644`
- `0x18000cfcc`
- `0x18000d928`
- `0x18000e9e8`
- `0x18000edbc`
- `0x18000f094`
- `0x18000f28c`
- `0x18000f4b0`
- `0x18000fbf0`
- `0x18000fee0`
- `0x180010444`
- `0x180010ac0`

## callees

- `0x180002bc0`
- `0x180003180`

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
0x180002bc0  cmp     rcx, cs:__security_cookie
0x180002bc7  jnz     short ReportFailure
0x180002bc9  rol     rcx, 10h
0x180002bcd  test    cx, 0FFFFh
0x180002bd2  jnz     short RestoreRcx
0x180002bd4  retn
0x180002bd5  ror     rcx, 10h; StackCookie
0x180002bd9  jmp     __report_gsfailure
```
