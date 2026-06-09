# __security_check_cookie

- ea: `0x180001460`
- end: `0x18000147e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `84`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001d80`
- `0x180001fe0`
- `0x180002d00`
- `0x180002eb4`
- `0x180002f68`
- `0x180003050`
- `0x1800034e4`
- `0x180003968`
- `0x1800043c8`
- `0x1800044d0`
- `0x1800045ec`
- `0x180004870`
- `0x1800049d0`
- `0x180004d20`
- `0x180004f2c`
- `0x180005110`
- `0x180005470`
- `0x180005734`
- `0x1800059c0`
- `0x180005f34`
- `0x1800067a0`
- `0x180006a44`
- `0x180006d80`
- `0x1800070ec`
- `0x1800072a0`
- `0x180007890`
- `0x1800079f0`
- `0x180007c00`
- `0x180007e50`
- `0x180007fd0`
- `0x180008060`
- `0x180008110`
- `0x1800081c0`
- `0x180008350`
- `0x1800083d0`
- `0x180008470`
- `0x180008570`
- `0x1800086a0`
- `0x180008710`
- `0x1800088ac`
- `0x180009110`
- `0x180009800`
- `0x18000a060`
- `0x18000b87c`
- `0x18000bed0`
- `0x18000c410`
- `0x18000ca4c`
- `0x18000d590`
- `0x18000d86c`
- `0x18000f020`

## callees

- `0x180001460`
- `0x180001490`

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
0x180001460  cmp     rcx, cs:__security_cookie
0x180001467  jnz     short ReportFailure
0x180001469  rol     rcx, 10h
0x18000146d  test    cx, 0FFFFh
0x180001472  jnz     short RestoreRcx
0x180001474  retn
0x180001475  ror     rcx, 10h; StackCookie
0x180001479  jmp     __report_gsfailure
```
