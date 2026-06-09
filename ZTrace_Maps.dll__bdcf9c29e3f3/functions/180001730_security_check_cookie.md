# __security_check_cookie

- ea: `0x180001730`
- end: `0x18000174e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `10`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000108c`
- `0x180001184`
- `0x180002338`
- `0x1800024bc`
- `0x18000308c`
- `0x1800037b4`
- `0x180003854`
- `0x18000390c`
- `0x1800039d4`
- `0x180003ad4`

## callees

- `0x180001730`
- `0x180001d00`

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
0x180001730  cmp     rcx, cs:__security_cookie
0x180001737  jnz     short ReportFailure
0x180001739  rol     rcx, 10h
0x18000173d  test    cx, 0FFFFh
0x180001742  jnz     short RestoreRcx
0x180001744  retn
0x180001745  ror     rcx, 10h; StackCookie
0x180001749  jmp     __report_gsfailure
```
