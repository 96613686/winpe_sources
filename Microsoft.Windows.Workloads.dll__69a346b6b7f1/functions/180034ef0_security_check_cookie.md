# __security_check_cookie

- ea: `0x180034ef0`
- end: `0x180034f0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `211`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001000`
- `0x1800011f0`
- `0x180001540`
- `0x1800018f0`
- `0x180001a10`
- `0x180001b90`
- `0x180001ca0`
- `0x1800025f0`
- `0x180002bd0`
- `0x180002cb0`
- `0x180002f70`
- `0x180003db0`
- `0x180004190`
- `0x180004480`
- `0x180004590`
- `0x180004c70`
- `0x180004e40`
- `0x1800052e0`
- `0x1800056e0`
- `0x1800058e0`
- `0x180006110`
- `0x1800068a0`
- `0x180006940`
- `0x180006b70`
- `0x180007150`
- `0x180007820`
- `0x180007a20`
- `0x180008700`
- `0x180008a50`
- `0x180008c60`
- `0x1800098d0`
- `0x180009a40`
- `0x18000a0f0`
- `0x18000a510`
- `0x18000a550`
- `0x18000a7b0`
- `0x18000bd90`
- `0x18000be70`
- `0x18000c010`
- `0x18000c120`
- `0x18000c1f0`
- `0x18000c2d0`
- `0x18000c5b0`
- `0x18000d0c0`
- `0x18000d7a0`
- `0x18000d9a0`
- `0x18000e150`
- `0x18000e370`
- `0x18000eaa0`
- `0x18000f670`

## callees

- `0x180034ef0`
- `0x180035d20`

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
0x180034ef0  cmp     rcx, cs:__security_cookie
0x180034ef7  jnz     short ReportFailure
0x180034ef9  rol     rcx, 10h
0x180034efd  test    cx, 0FFFFh
0x180034f02  jnz     short RestoreRcx
0x180034f04  retn
0x180034f05  ror     rcx, 10h
0x180034f09  jmp     __report_gsfailure
```
