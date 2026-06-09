# __security_check_cookie

- ea: `0x180006570`
- end: `0x18000658e`
- name: `__security_check_cookie`
- size: `30`
- prototype: `void __cdecl(uintptr_t StackCookie)`
- caller_count: `17`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180001010`
- `0x180001270`
- `0x1800015a0`
- `0x1800019d0`
- `0x180002460`
- `0x1800028f0`
- `0x180002c80`
- `0x180002e80`
- `0x180003250`
- `0x1800034b0`
- `0x1800037f0`
- `0x180003bc0`
- `0x180003df0`
- `0x180005474`
- `0x1800058f0`
- `0x180005b70`
- `0x180006460`

## callees

- `0x180004af0`
- `0x180006570`

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
0x180006570  cmp     rcx, cs:__security_cookie
0x180006577  jnz     short ReportFailure
0x180006579  rol     rcx, 10h
0x18000657d  test    cx, 0FFFFh
0x180006582  jnz     short RestoreRcx
0x180006584  retn
0x180006585  ror     rcx, 10h
0x180006589  jmp     __report_gsfailure
```
