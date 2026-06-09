# __security_check_cookie

- ea: `0x180009c90`
- end: `0x180009cae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001df8`
- `0x180002768`
- `0x180002a28`
- `0x180003b08`
- `0x180004210`
- `0x180004cb4`
- `0x180005304`
- `0x1800056f4`
- `0x180006280`
- `0x1800063e0`
- `0x180007b2c`
- `0x180008670`
- `0x1800087a0`
- `0x180008f80`
- `0x180009670`
- `0x1800098a0`
- `0x180009b6c`

## callees

- `0x180001a50`
- `0x180009c90`

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
0x180009c90  cmp     rcx, cs:__security_cookie
0x180009c97  jnz     short ReportFailure
0x180009c99  rol     rcx, 10h
0x180009c9d  test    cx, 0FFFFh
0x180009ca2  jnz     short RestoreRcx
0x180009ca4  retn
0x180009ca5  ror     rcx, 10h
0x180009ca9  jmp     __report_gsfailure
```
