# __security_check_cookie

- ea: `0x18000a190`
- end: `0x18000a1ae`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `7`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001cfc`
- `0x1800059e0`
- `0x180005bf0`
- `0x180005d90`
- `0x1800068f0`
- `0x180006d60`
- `0x180008540`

## callees

- `0x180001b00`
- `0x18000a190`

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
0x18000a190  cmp     rcx, cs:__security_cookie
0x18000a197  jnz     short ReportFailure
0x18000a199  rol     rcx, 10h
0x18000a19d  test    cx, 0FFFFh
0x18000a1a2  jnz     short RestoreRcx
0x18000a1a4  retn
0x18000a1a5  ror     rcx, 10h
0x18000a1a9  jmp     __report_gsfailure
```
