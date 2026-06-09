# __security_check_cookie

- ea: `0x1800449f0`
- end: `0x180044a0e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `146`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001008`
- `0x18000137c`
- `0x180001d70`
- `0x180002870`
- `0x180003350`
- `0x180003980`
- `0x180004340`
- `0x180005a8c`
- `0x180008860`
- `0x180012050`
- `0x180012960`
- `0x180016bf4`
- `0x18001a9c0`
- `0x18001b670`
- `0x18001ed34`
- `0x18001f410`
- `0x18001fa30`
- `0x18001fbf8`
- `0x18001fd98`
- `0x180020188`
- `0x180020eb4`
- `0x180020f90`
- `0x180021040`
- `0x180021aa0`
- `0x180029240`
- `0x1800293d4`
- `0x180029a60`
- `0x180029d20`
- `0x18002a3a0`
- `0x1800329d0`
- `0x180033e08`
- `0x18003549c`
- `0x180035e80`
- `0x1800379c8`
- `0x18003c13c`
- `0x18003c904`
- `0x18003cbb8`
- `0x18003d734`
- `0x18003e330`
- `0x18003efe8`
- `0x18003f040`
- `0x18004117c`
- `0x180042520`
- `0x180042820`
- `0x180042eb0`
- `0x1800434e0`
- `0x180045d84`
- `0x180046040`
- `0x180046920`
- `0x180046d0c`

## callees

- `0x1800449f0`
- `0x180044fb0`

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
0x1800449f0  cmp     rcx, cs:__security_cookie
0x1800449f7  jnz     short ReportFailure
0x1800449f9  rol     rcx, 10h
0x1800449fd  test    cx, 0FFFFh
0x180044a02  jnz     short RestoreRcx
0x180044a04  retn
0x180044a05  ror     rcx, 10h; StackCookie
0x180044a09  jmp     __report_gsfailure
```
