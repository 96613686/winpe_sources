# __security_check_cookie

- ea: `0x180001520`
- end: `0x18000153e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `36`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001b54`
- `0x180009c0c`
- `0x180009d80`
- `0x18000add0`
- `0x18000b434`
- `0x18000b73c`
- `0x18000b870`
- `0x18000b960`
- `0x18000bb40`
- `0x18000bc30`
- `0x18000c768`
- `0x18000cba4`
- `0x18000d2d0`
- `0x18000d750`
- `0x18000db20`
- `0x18000e190`
- `0x18000e59c`
- `0x18000e614`
- `0x18000ea74`
- `0x18000ecb0`
- `0x180013670`
- `0x1800159b0`
- `0x18001c788`
- `0x18001de8c`
- `0x1800221c0`
- `0x180023a68`
- `0x180023cf0`
- `0x180028c44`
- `0x18002a948`
- `0x18002baa0`
- `0x180031854`
- `0x180038c28`
- `0x180038ed8`
- `0x180038fa8`
- `0x1800391fc`
- `0x180039558`

## callees

- `0x180001520`
- `0x180001b20`

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
