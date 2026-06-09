# __security_check_cookie

- ea: `0x180008410`
- end: `0x18000842e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `11`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003e3c`
- `0x180003f60`
- `0x18000422c`
- `0x1800045d8`
- `0x1800046d0`
- `0x1800048a4`
- `0x1800050f0`
- `0x1800070b4`
- `0x180007234`
- `0x180008254`
- `0x180008350`

## callees

- `0x180001940`
- `0x180008410`

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
0x180008410  cmp     rcx, cs:__security_cookie
0x180008417  jnz     short ReportFailure
0x180008419  rol     rcx, 10h
0x18000841d  test    cx, 0FFFFh
0x180008422  jnz     short RestoreRcx
0x180008424  retn
0x180008425  ror     rcx, 10h
0x180008429  jmp     __report_gsfailure
```
